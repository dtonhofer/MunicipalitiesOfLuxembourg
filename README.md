Municipalities (Communes) Of Luxembourg
=======================================

Status
------

- Released in August 2013
- Unmaintained, of historical interest only
- GIS question? Check out [gis.stackexchange.com](https://gis.stackexchange.com/)

What
----

This repository contains a dataset of annoted polygons describing the municipalities ("communes") of the
[Grand-Duchy of Luxembourg](http://en.wikipedia.org/wiki/Luxembourg) (as they are after the 2012 mergers).

Additionally, layers for polygons describing the suburbs ("quartiers") of the city of Luxembourg and the
suburbs of the city of Esch-sur-Alzette have been added.  The polygons for these are a bit inexact though (see 
below).

This repository has been created for a [Q-LEAP S.A.](http://www.q-leap.eu/) project.

Source and Licensing
--------------------

The geometry data is based on an OpenStreetMap (OSM) extract. No databases other than
OpenStreetMap have been used in the compilation. Data is therefore available under
[Open Data Commons Open Database License (ODbL) 1.0](http://opendatacommons.org/licenses/odbl/).
See also [OpenStreetMap Copyright and License](http://www.openstreetmap.org/copyright).


Format
------

The format used is [Geography Markup Language](http://en.wikipedia.org/wiki/Geography_Markup_Language) (actually OpenJump GML)
which can be read and processed by [OpenJUMP GIS](http://www.openjump.org/).

Content
-------

![Municipalities of the Grand-Duchy of Luxembourg](https://raw.github.com/dtonhofer/MunicipalitiesOfLuxembourg/master/images/Municipalities_Screenshot.png "Municipalities of the Grand-Duchy of Luxembourg")

There are 106 municipalities, but there are two polygons for "Steinfort", which is separated into [two
disjoint areas separated by a highway](http://www.openstreetmap.org/#map=15/49.6338/5.8935).

Files
-----

<table>

<tr>
<td>17 MiB</td>
<td>OpenStreetMap_Input_Geometry.jml</td>
<td>Original OSM data from BBBike.org (The "roads" in "Luxembourg.osm.gz"). Unneeded lines have been removed and some missing lines have been added</td>
</tr>

<tr>
<td>27 KiB</td>
<td>MunicipalitiesOfLuxembourg.jmp</td>
<td>The OpenJUMP GIS project master file</td>
</tr>

<tr>
<td>7.8 MiB</td>
<td>Communes_du_Luxembourg_en_Polygones.jml</td>
<td>Polygons for the country's municipalities</td>
</tr>

<tr>
<td>75 KiB</td>
<td>Quartiers_de_Esch_sur_Alzette.jml</td>
<td>Polygons for the suburbs of the city of Esch-sur-Alzette</td>
</tr>

<tr>
<td>226 KiB</td>
<td>Quartiers_de_Luxembourg.jml</td>
<td>Polygons for suburbs of the city of Luxembourg</td>
</tr>

</table>

How to use this
---------------

   * Install [OpenJUMP GIS](http://www.openjump.org/).
   * Clone the repository using `git clone https://github.com/dtonhofer/MunicipalitiesOfLuxembourg.git` ... or you can simply download the files individually.<F5>
   * Start OpenJUMP GIS.
   * Select: File > Open Project > "MunicipalitiesOfLuxembourg.jmp". Make sure you selected the "Open Project" action, not the "Open File" action.

![OpenJUMP GIS - opening the project](https://raw.github.com/dtonhofer/MunicipalitiesOfLuxembourg/master/images/Open_Project_Dialog.png "OpenJUMP GIS - opening the project")

   * (OpenJUMP might complain about its inability to find files and will ask you whether to continue. Say YES. Select the correct file corresponding to the name that OpenJUMP presents. It's a bit tiresome but not hard. This problem has been fixed in current versions of OpenJUMP)
   * The data has been loaded. The "System" category shows:
       * A layer for the suburbs of the city of Luxembourg 
       * A layer for the suburbs of the city of Esch/Alzette
       * A layer for the original geometry loaded from OpenStreetMap
       * A layer for the polygons of the municipalities

![OpenJUMP GIS in action](https://raw.github.com/dtonhofer/MunicipalitiesOfLuxembourg/master/images/Successful_Load.png "OpenJUMP GIS in action")

   * Check out the "attributes" of the layer objects for the names associated to the polygons.

![OpenJUMP GIS attribute view](https://raw.github.com/dtonhofer/MunicipalitiesOfLuxembourg/master/images/Attributes.png "OpenJUMP GIS attribute view")

   * You may want to write the loaded data to a PostGIS table. For this, you must have a properly running and configured PostgreSQL server with the PostGIS extension. Right-click on the layer you want to save, then select "Save Dataset As". Set the format to "PostGIS table (new)". Fill in the server's coordinates. Fill in the name of the target table - to avoid running into problems and having to use quotes in PostgreSQL queries, I recommend using lowercase letters only for the table name. Unfortunately there is no option to force PostGIS to lowercase column names. You can add a separate primary key column (tick the appropriate box), or alter the table afterwards by declaring column "id" as primary key, like so:
       - ALTER TABLE polygones_luxembourg DROP COLUMN gid;
       - CREATE UNIQUE INDEX pollux_idx ON polygones_luxembourg("ID"); (See [Create Index](http://www.postgresql.org/docs/9.3/static/sql-createindex.html))
       - ALTER TABLE polygones_luxembourg ADD PRIMARY KEY USING INDEX pollux_idx; (See [Alter Table](http://www.postgresql.org/docs/9.3/static/sql-altertable.html))

Fixes to and Problems with the original OSM data
------------------------------------------------

Some problems have been roughly fixed in the dataset, but not yet in OpenStreetMap.
 
   * Suburbs of City of Luxembourg ("VdL")
      * The border between the suburbs of "Weimersdorf" and "Neudorf" of VdL is missing in OSM. I added
        a VERY APPROXIMATE line to separate those quarters. The address database of "Administration du Cadastre"
        just lists "Neudorf", collecting "Weimersdorf" and "Neudorf" into a single unit.
      * The address database of "Administration du Cadastre" lists the suburb of "Bonnevoie" as listed as two entries,
      * "Bonnevoie-Nord (Verlorenkost)" and "Bonnevoie". The website of VdL lists this as a single suburb.
        One should maybe add this subdivision.
      * The southern part of the boundary between the suburbs of "Cessange" and "Gasperich" of VdL 
        does not seem correct in OSM.
      * Additional small errors in VdL suburb borders do exist when comparing to the offical maps by eye. 
        A fix in OSM is needed, the corresponding geographic boundaries should be easily discoverable.
   * Suburbs of City of Esch/Alzette ("Esch")
      * The suburb "Belval" of Esch is not defined.
      * The suburb "Lalleng" of Esch is not defined.
      * The southern border of suburb "Neiduerf" of Esch is not defined. 
      * The eastern boundary of suburb "Schlassgoard" of Esch is not defined. 
      * The southern boundary of suburb "Grenz" of Esch is plain wrong.
      * The suburb "Park" of Esch is missing.
      * The suburb "Universiteit" of Esch is missing.
      * Additional small errors in Esch suburb borders do exist and need fixing.
      * Note that the address database of "Administration du Cadastre" lists no suburbs for Esch at all.

TODOs
-----

   * Fix the problems with the suburb geometry.
   * It would also be nice to have the special sector of Findel Airport as a polygon!
   * The old, pref-merger municipalities should also be visible in a separate layer.

References for suburbs
----------------------

   * Names of the suburbs of the city of Luxembourg can be found at the
     [Website of the City of Luxembourg](http://www.vdl.lu/Environnement+et+Urbanisme/D%C3%A9veloppement+urbain/Les+24+quartiers+de+la+Ville.html)
   * Names of the suburbs of the city of Esch can be found at the Website of Ville d'Esch.
     There is a [static map](http://www.esch.lu/SiteCollectionDocuments/plans/web_planquartiers.jpg) and an
     [interactive map](http://www.topographie.esch.lu/), which are not fully consistent.

Online info about communes
--------------------------

   * http://www.luxembourg.public.lu/fr/tourisme/cartes/communes/index.html
   * http://www.geologie.lu/index.php/geolux/pubs/71-geocom

Notes on post-2000 changes
--------------------------

<table>

<tr>
<td>Bastendorf, Fouhren</td>
<td>merged into</td>
<td>Tandel</td>
</tr>

<tr>
<td>Wilwerwiltz, Kautenbach</td>
<td>merged into</td>
<td>Kiischpelt</td>
</tr>

<tr>
<td>Remerschen</td>
<td>renamed to</td>
<td>Schengen</td>
</tr>

<tr>
<td>Bettborn</td>
<td>renamed to</td>
<td>Préizerdaul</td>
</tr>

<tr>
<td>Clervaux, Heinerscheid, Munshausen</td>
<td>merged into</td>
<td>Clervaux</td>
</tr>

<tr>
<td>Ermsdorf, Medernach</td>
<td>merged into</td>
<td>Vallée de l'Ernz</td>
</tr>

<tr>
<td>Esch-sur-Sûre, Heiderscheid, Neunhausen</td>
<td>merged into</td>
<td>Esch-sur-Sûre</td>
</tr>

<tr>
<td>Bascharage, Clemency</td>
<td>merged into</td>
<td>Käerjeng</td>
</tr>

<tr>
<td>Consthum, Hoscheid, Hosingen</td>
<td>merged into</td>
<td>Parc Hosingen</td>
</tr>

<tr>
<td>Burmerange, Schengen, Wellenstein</td>
<td>merged into</td>
<td>Schengen</td>
</tr>

</table>
    

