---
layout: project-page
title: "NYC Parks & Eateries"
linkname: nyc-parks-eateries
author: "Patra Jongjitirat"
tagline: "This interactive map features New York City parks and the amenities situated within the parks’ boundaries. It features interactive points and polygons that bring up corresponding details in the sidebar, options for zooming and showing/hiding layers, and a customized basemap using Mapbox."
location:
    - place: New York, NY, USA
project-link:
    - href: https://pjongjit.github.io/park-eateries-map/
tags:
    - tag: parks
    - tag:  greenspaces
    - tag:  eateries
    - tag:  park amenities
    - tag:  food trucks
    - tag:  concession stands
thumbnail-path: img/nyc-parks-eateries/Y7pYP2U.png
img-folder: ../../img/nyc-parks-eateries/
timestamp: 10/17/2018 19:11:59
---
## The Idea
I created a map of New York City parks and the amenities situated within the parks’ boundaries. Amenities were to include eateries (i.e. cafes, food trucks, concession stands) and restrooms. My original inspiration was to create a tool I could refer to when spending a day or an afternoon in one of the city’s greenspaces: What if I got hungry or thirsty and didn’t pack any food or drink with me? And with all that eating and drinking, where was the nearest restroom? It would be useful to have a map of these things so I wouldn’t have to wander aimlessly through the park trying to encounter them—or a physical map kiosk—by luck.

## The Data
Since I was focusing on New York, I searched for potential data sources on [NYC Open Data](https://opendata.cityofnewyork.us/). I found data on [Parks Properties](https://data.cityofnewyork.us/City-Government/Parks-Properties/k2ya-ucmv).

![]({{ page.img-folder }}zkmQoB6.png) 

I also came across a [Directory of Concessions](https://data.cityofnewyork.us/Housing-Development/Directory-of-Concessions/ac9y-je94) and a [Directory of Toilets in Public Parks](https://data.cityofnewyork.us/Recreation/Directory-Of-Toilets-In-Public-Parks/hjae-yuav). The latter didn’t have the locations geocoded, so, for the sake of time and wanting to begin coding and designing, I decided to move forward with the park properties and the eateries and come back to the restrooms at a later date. 

## The Map & Overall Structure
This is an initial sketch of what I wanted my map to be:

![]({{ page.img-folder }}IGnUv3B.jpg) 

This is the map I created:

![]({{ page.img-folder }}Z37G5p0.png) 

It has styled polygons and points to represent the parks and eateries, and a sidebar for displaying select details. I created the basemap in Mapbox, keeping to a minimalist color scheme. In realizing I wanted the styling of parks to be part of the interactivity, I revoked some of the initial styling I had done for the park layer. 

## Interactive Features
#### PARK POLYGONS
A stroke appears around the park polygons on hover:

![]({{ page.img-folder }}Y7pYP2U.png)

Once you click, the map zooms in to fit the bounds of that park:

![]({{ page.img-folder }}aGUitde.png) 

At the same time, clicking on the park brings up its info in the sidebar…

#### MUSTACHE TEMPLATE
The sidebar includes templates for both parks and eateries:

![]({{ page.img-folder }}yzuFjf5.png) 

Clicking on a park and/or an eatery populates the template:

![]({{ page.img-folder }}X4r1gPX.png) 

The blue color of the website means the link has been visited. When you hover over the website, a strikethrough styling is applied:

![]({{ page.img-folder }}wqpRrDs.png) 

#### TOGGLE SWITCH
You have the option to hide the layer with all the eatery points (or re-show them) with the switch. This was conceived as a way to help manage what you see as part of my original idea, where there would be multiple sets of data—eateries and restrooms. Even still, having the toggle for just the eateries is a fun function. 

![]({{ page.img-folder }}K0CufFH.png)

![]({{ page.img-folder }}1dnhlkY.png) 

#### RE-CENTER BUTTON
In the process of making the map and zooming in to different parks with each click of a polygon, it became helpful to have a quick and easy way to re-center the map. So I added a button for that, which resets the map to the starting view:

![]({{ page.img-folder }}ubrhPlN.png) 

## Some Challenges
Creating the map came with many challenges, mostly in building the interactive components and getting the events to work in Javascript. Here were some of the issues:

The data for the parks used a single-letter abbreviation for the boroughs. I wanted the sidebar/Mustache template to display the full borough name, which was possible by creating a “new Map” function (assigns values in an array with alternate values) and adding “fullnames” to the properties list.

It took some finagling to get the toggle switch to correspond to the appropriate event, eventually achieved by using the hasLayer function. Then there was a way to know what state the map was in and whether that meant the eateries had to be added or removed. 

I encountered some difficulties with getting the styling of park polygons to remain after the polygon was clicked. This was fixed by creating a variable to hold the park layer style and then using the resetStyle function on mouseout.

Regarding the data, it became evident the data needed some cleanup in certain instances:

![]({{ page.img-folder }}wJaLuzx.png) 

In addition, my two data sets don’t align exactly, since the Directory of Concessions includes locations in recreational facilities that may not be considered park properties. With more time, I could consider editing down the concessions data so that it corresponds more precisely with city parks.

## Final Thoughts
I was able to realize a map not entirely dissimilar from what I was imagining. Visually I find the map interesting in being able to see the patchwork of greenspaces throughout the city. I didn’t get everything working that I had outlined in my initial sketch (e.g. a filter by borough and a corresponding directory of parks that would appear), partly because of time and current skill level, but also some hesitancy on the usefulness of including certain features I had imagined. It makes me think that a specific focus and a degree of restraint are useful in creating interactive maps, since it is so easy to get carried away with the limitless options. Lastly, the project reiterated the formidable challenge of finding complete, accurate data and that time will always be spent on getting it into a form that is appropriate and useful. 
