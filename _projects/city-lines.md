---
layout: project-page
title: "City Lines"
linkname: city-lines
author: "Matthew Roosa"
tagline: "These are four maps of different cities around the world. Top Left is Tokyo, Top Right is Paris, Bottom Left is Shanghai, and the Bottom Right is New York.
Each have their subway lines shown to compare the density, structure length, and creation years."
location:
    - place: New York, USA
    - place:  Shanghai, China
    - place:  Paris, France
    - place:  Tokyo, Japan
project-link:
    - href: https://taikingm.github.io/city-lines/
tags:
    - tag: Subway
    - tag:  International
    - tag:  Transportation
    - tag:  
thumbnail-path: img/city-lines/cover.png
img-folder: ../../img/city-lines/
timestamp: 10/18/2018 0:37:06
---
The project started as a idea I always had of visualizing the comparison of transit lines in different cities. I’ve decided to come up with 4 large cities with similar population sizes as within different parts of the world. I thought it would also be interesting to show the base map with only lines to represent the density and structure of the city. As you can see, you are able to easily compare the 4 and guess how the city has planned to grow. 

The first step of the process was to find all the shape files of the lines for each transit systems.
Although New York has its data on OpenNYC, it would have been harder to find open data for other cities. I was able to look into Open Street Map and find a website that hosted shape files of different cities of the world. (https://www.nextzen.org/metro-extracts/index.html)

![]({{ page.img-folder }}vqGxNKs.png)

From here, I downloaded the ‘Imposm Shapefiles’ of Paris, Shanghai, Tokyo, and New York.
This shape file contains polygons, lines, boundaries, and everything else that is represented in OSM.  I opened the line shape file with QGIS which looked like this.

![]({{ page.img-folder }}5r9YmVt.png)

![]({{ page.img-folder }}jHLjtO1.png)

As you can see, this contained all lines represented within OSM from streets, waterways, to administrative boundaries.
From here, I was able to filter the data with the fields into Subways to get only the lines representing the subway system. This process took a while because these lines are broken down to segments, which merged together to represent one line. I exported the original filtered shape file into a GeoJson to edit and merge all the lines representing one metro line into one so I can store additional data into the one column instead of having multiple lines representing one metro line. 

One of the hardest part of the project was finding all the data I wanted to represent on my page. There were no set data source for the fields I wanted, so in order to find all the data, I had to search each one differently and manually enter the data into my GeoJson to create a new dataset. I eventually created a GeoJson file for each city, thinking back now it might have been easier to create one single GeoJson file with all the cities included so it would have been easier editing the data.

Next, I created my base map using Mapbox. I was thinking of first importing the original line OSM shape file into Mapbox and creating a base map from scratch. This method didn’t work because the shape file included artificial lines such as ferry routes which was too much data to go through and delete. On Mapbox I hid all other layers besides the lines and water, changed all the line width to 2 or 1 px in order to simplify the visualization.

On this project, it took a lot more time than expected on the initial data collection and creation of the subway line layers, displaying the maps as I wanted on the webpage. I was not able to spend as much time on the Javascript which was a huge setback into not being able to accomplish exactly what I wanted to.
