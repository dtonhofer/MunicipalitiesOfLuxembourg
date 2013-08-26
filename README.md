MunicipalitiesOfLuxembourg
==========================

Annoted polygons describing the municipalities of the [Grand-Duchy of Luxembourg](http://en.wikipedia.org/wiki/Luxembourg), after the 2012 mergers.

Additional layers for the suburbs of the City of Luxembourg and the City of Ville d'Esch have been added. The polygons for these are a bit inexact though (see below).

The geometry data is based on an OpenStreetMap (OSM) extract. No databases other than OpenStreetMap have been used in the compilation.  
 
The format used is [Geography Markup Language](http://en.wikipedia.org/wiki/Geography_Markup_Language), which can be read and processed by [OpenJump](http://www.openjump.org/).

![Grand-Duchy of Luxembourg](https://raw.github.com/dtonhofer/MunicipalitiesOfLuxembourg/master/Municipalities_Screenshot.png "Grand-Duchy of Luxembourg")

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
