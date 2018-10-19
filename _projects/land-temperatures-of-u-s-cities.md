---
layout: project-page
title: "Land Temperatures of U.S. Cities"
linkname: land-temperatures-of-u-s-cities
author: "Jeremy Anne Herco"
tagline: "A web map created to allow users to interact with land temperature data of cities in the United States on January 1st between years 1849-2013.  "
location:
    - place: United States
project-link:
    - href: https://glitch.com/~axiomatic-haze
tags:
    - tag: temperature
    - tag:  United States
    - tag:  timeline
    - tag: 
thumbnail-path: img/land-temperatures-of-u-s-cities/YVrq35j.jpg
img-folder: ../../img/land-temperatures-of-u-s-cities/
timestamp: 10/17/2018 23:09:52
---
![]({{ page.img-folder }}YVrq35j.jpg)

The purpose of this map is to allow users to visualize the average temperature of cities in the U.S. on January 1st for every year from 1849-2013. The data is compiled by non-profit Berkeley Earth to be used as a source for climate change research. Though the data includes the average temperature of cities all over the world, for the sake of this project I filtered the data to only include data from cities in the United States. My goal was to create a map that allows users to compare the temperatures of different cities on January 1st in different years.

I downloaded the data as a .csv and used python to clean up the file. The first step was to filter for only cities located in the U.S. since the original file was too large for the web map to manage. I also had to filter for the common minimum date of all cities since the oldest dates varied for some locations. For the sake of having a dataset that would be easy to manage, I also filtered the data to only include January 1st of each year (the original dataset included the first day of each month for each year). Finally, I convert the latitude and longitude columns into usable coordinates and used QGIS to convert the data into a GeoJson file. The end result left me with the temperature in celsius of 248 cities, from years 1849-2013.

To visualize the data, each city is represented by a circle marker colored by the average temperature of the city in that year. The legend to indicate the temperature is included on the bottom left corner of the map. When you click on each marker, a popup will show the name of the city, the temperature, and the date. 

In order to compare the climate of each year, the user can toggle with the time-slider in the top right corner. The time-slider will change the markers to show the temperatures in different years, allowing the use to slide back and forth between different years. 

I also included a geocoder in order for users to get a closer look at states that have markers in different cities in different areas. 

Link to Github: https://github.com/jermyhands/Land-Temperature-in-U.S.
