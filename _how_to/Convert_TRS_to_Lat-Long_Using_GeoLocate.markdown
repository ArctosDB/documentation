---
title: How To Convert Township/Range/Section data to Latitude/Longitude Coordinates Using GeoLocate
author: Nicole Ridgwell, Teresa J. Mayfield-Meyer
date: 2019-06-01
layout: default_toc
---
[Locality Documentation](https://handbook.arctosdb.org/documentation/locality.html)

# How To Convert Township/Range/Section data to Latitude/Longitude Coordinates Using GeoLocate

**Township/Range/Section data can be converted to latitude/longitude coordinates using the following method.**

**1.**	Open [GeoLocate](https://www.geo-locate.org/web/WebGeoref.aspx)  
  
**2.**	On the upper right-hand side of the interface is a blue + symbol.  
  * Click it to open a menu of possible map base layers.  
![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/GeoLocate1.jpg)  

  * Select ESRI USGS Topo USA.  
![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/GeoLocate2.jpg)  

  * Minimize the menu.  

**3.**	Next to “Locality String” type in the coordinates in this format: T10N R33E Sec. 22. Enter the country, state and county (in this example, the state is New Mexico). Select "Georeference" 
![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/GeoLocate3.jpg)  

**4.**	Zoom in on the map until the uncertainty circle fills the screen. The center of the circle should be at the center of a square on the map. This square is the section boundary. 
![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/GeoLocate4.JPG)  

**5.**	If your TRS coordinate does not have any quarter section data:  
  * Select “Draw polygon”.  
![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/GeoLocate4a.jpg)  
  * Click on the four corners of the section square to draw a matching polygon. Double click on the last corner to release.
![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/GeoLocate5.JPG)   
  * Click on the center point of the circle and then click “Resize uncertainty to polygon”.  
![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/GeoLocate6.JPG)  
  * If the edges of the circle do not match up to the square, move the center point slightly and resize again.   
  * Use the latitude, longitude, and uncertainty of the circle for your locality.  
  ![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/GeoLocate7.JPG)  

**6.**	If your TRS coordinates do have quarter section data:  
  * How to read quarter sections, an example: If the data has a string of letters after it like this – NW SW SE – you should read it as – the northwest corner of the southwest corner of the southeast corner of section 22. Imagine the grid below is section 22, the x marks the correct quarter section:  
![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/TRS%20table.JPG)  
  * Select “Draw polygon”.    
  * Approximate the position of the quarter section within the section square. Draw a square at this position. Double click on the last corner to release.    
  * Move the center point of the circle to the center of the quarter section square.    
  * Click on the center point of the circle and then click “Resize uncertainty to polygon”.    
  * If the edges of the circle do not match up to the square, move the center point slightly and resize again.    
  * Use the latitude, longitude, and uncertainty of the circle for your locality.

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/Convert_TRS_to_Lat-Long_Using_GeoLocate.markdown" target="_blank">here</a>.
