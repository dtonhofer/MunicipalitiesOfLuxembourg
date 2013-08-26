MunicipalitiesOfLuxembourg
==========================

Annoted polygons describing the municipalities ("communes") of the
[Grand-Duchy of Luxembourg](http://en.wikipedia.org/wiki/Luxembourg) (after the 2012 mergers).

Additional layers for the suburbs ("quartiers") of the city of Luxembourg and the suburbs of the city of Esch-sur-Alzette have been added. 
The polygons for these are a bit inexact though (see below).

The geometry data is based on an OpenStreetMap (OSM) extract. No databases other than
OpenStreetMap have been used in the compilation.
 
The format used is [Geography Markup Language](http://en.wikipedia.org/wiki/Geography_Markup_Language), 
which can be read and processed by [OpenJUMP GIS](http://www.openjump.org/).

![Grand-Duchy of Luxembourg](https://raw.github.com/dtonhofer/MunicipalitiesOfLuxembourg/master/images/Municipalities_Screenshot.png "Grand-Duchy of Luxembourg")

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
