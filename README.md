Municipalities Of Luxembourg
============================

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
See also [http://www.openstreetmap.org/copyright](OpenStreetMap Copyright and License)


Format
------

The format used is [Geography Markup Language](http://en.wikipedia.org/wiki/Geography_Markup_Language) (actually OpenJump GML)
which can be read and processed by [OpenJUMP GIS](http://www.openjump.org/).

Content
-------

![Municipalities of the Grand-Duchy of Luxembourg](https://raw.github.com/dtonhofer/MunicipalitiesOfLuxembourg/master/images/Municipalities_Screenshot.png "Municipalities of the Grand-Duchy of Luxembourg")

There are 106 municipalities, but there are two polygons for "Steinfort", which is separated into [two
disjoint areas seprated by a highway](http://www.openstreetmap.org/#map=15/49.6338/5.8935).

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
   * Clone the rpository using `git clone https://github.com/dtonhofer/MunicipalitiesOfLuxembourg.git` ... or you can 
     simply download the files directly, as there aren't many.
   * Start OpenJUMP GIS.
   * Choose File > Open Project > "MunicipalitiesOfLuxembourg.jmp"
   * OpenJUMP will complain about its inability to find files and will ask you whether to continue. Say YES.
   * Select the file corresponding to name that OpenJUMP presents. It's a bit tiresome but not hard.
   * The data has been loaded. From this point onwards, you are on your own!
   * Check out the "attributes" of the layer objects for the names.
   
![OpenJUMP GIS in action](https://raw.github.com/dtonhofer/MunicipalitiesOfLuxembourg/master/images/Successful_Load.png "OpenJUMP GIS in action")

![OpenJUMP GIS attribute view](https://raw.github.com/dtonhofer/MunicipalitiesOfLuxembourg/master/images/Attributes.png "OpenJUMP GIS attribute view")

Fixes to and Problems with the original OSM data
------------------------------------------------

Major problems have been roughly fixed in the dataset, but not yet in OopenStreetMap.
 
   * The border between the suburbs of "Weimersdorf" and "Neudorf" of Luxembourg-City is missing in OSM; added
     a VERY APPROXIMATE line to separate those quarters. 
   * The southern part of the boundary between the suburbs of "Cessange" and "Gasperich" of Luxembourg-City 
     does not seem correct in OSM.
   * Additional small errors in Luxembourg-City suburb borders do exist when comparing to the offical maps by eye. 
     A fix in OSM is needed, the corresponding geographic boundaries should be easily discoverable.
   * The suburb "Belval" of the city of Ville d'Esch is not defined.
   * The suburb "Lalleng" of the city of Ville d'Esch is not defined.
   * The southern border of suburb "Neiduerf" of Ville d'Esch is not defined. 
   * The eastern boundary of suburb "Schlassgoard" of Ville d'Esch is not defined. 
   * The southern boundary of suburb "Grenz" of Ville d'Esch is wrong.
   * The suburb "Park" of Ville d'Esch is missing.
   * The suburb "Universiteit" of Ville d'Esch is missing.
   * Additional small errors in Ville d'Esch suburb borders do exist.

TODOs
-----

   * Fix the problems with the suburb geometry
   * It would also be nice to have the special sector of Findel Airport as a polygon
   * The old, pref-merger municipalities should also be visible in a separate layer

Notes on suburbs
----------------

   * Names of the suburbs of the city of Luxembourg can be found at the
     [Website of the City of Luxembourg](http://www.vdl.lu/Environnement+et+Urbanisme/D%C3%A9veloppement+urbain/Les+24+quartiers+de+la+Ville.html)
   * Names of the suburbs of the city of Esch can be found at the Website of Ville d'Esch.
     There is a [static map](http://www.esch.lu/SiteCollectionDocuments/plans/web_planquartiers.jpg) and an
     [interactive map](http://www.topographie.esch.lu/), which are not fully consistent.

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
    

