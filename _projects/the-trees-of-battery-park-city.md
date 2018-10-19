---
layout: project-page
title: "The Trees of Battery Park City"
linkname: the-trees-of-battery-park-city
author: "Daniel Chi Cook"
tagline: "An interactive map that visualizes trees in Battery Park City’s parks and on the neighborhood’s sidewalks and also provides basic information about those trees."
location:
    - place: New York, USA
project-link:
    - href: https://dcookchi.github.io/dcc-xsavi780-trees/
tags:
    - tag: trees, street trees, parks, urban ecology, sustainability, environment
thumbnail-path: img/the-trees-of-battery-park-city/K0EEtKG.png
img-folder: ../../img/the-trees-of-battery-park-city/
timestamp: 10/17/2018 18:08:58
---
The Horticulture Department of Battery Park City Authority (BPCA) asked me to do a preliminary mapping of the trees on the streets, in the parks, and inside the gardens of the neighborhood of Battery Park City. After completing this initial effort, I thought that it would be fun to create a web map which could serve as a prototype for an interactive tool. Such an interactive tool could then either be used as an internal horticultural management or for external engagement.

![]({{ page.img-folder }}I5EQu8z.png)

From a visual design perspective, I wanted to converse with the NYC Street Tree Map. One choice I made which stands in contrast with that map is that I chose a darker theme, including a darker base map. I customized the base map using Mapbox and also included shapefiles of the building footprints in the neighborhood, which I obtained from NYC Open Data, as well as survey lines from a survey commissioned by BPCA, which I converted from a CAD file. In general, I wanted this base map to be darker and somewhat muted so that the tree points would stand out more, being the only feature on the map that is not in grayscale.

![]({{ page.img-folder }}ueVNQez.png)

Regarding the interactive elements, I created the map primarily using Leaflet and a few of its plug-ins. I restricted certain interactive elements such as zoom and extent, both in Mapbox and in the JavaScript code. I added popups using Mustache, as well as marker clusters using the Marker Cluster plug-in. 

![]({{ page.img-folder }}K0EEtKG.png)

![]({{ page.img-folder }}3nZJejf.png)

I mapped 1823 trees in Battery Park City, with assistance from gardeners working for the Horticulture Department. The most common trees were those that were also found along sidewalks, including the honey locust, the bradford pear, the zelkova, and the silver linden. Part way through creating this map, I felt like I wanted there to be a way to quickly and visually show the quantities of species of trees, so I added the feature to highlight all trees of a certain species whenever the mouse hovers over a tree of that species. The honey locust is the most common tree, with their being 373 of them in this data set (highlighted in the screenshot below).

![]({{ page.img-folder }}0RWHvrx.png)

Finally, I wanted to add an element that was both interactive and analytical, so I put in a feature to load the park maintenance shapes of the parks that BPCA maintains. The data which shows the count of trees within the boundaries of those shapes are generated in the browser using Turf.js. 

![]({{ page.img-folder }}Csk24V7.png)

Reflecting on this project as a whole, I would say that I had fun with it and that I was able to create something that could either be used at least as a proof of concept for the type of web map product which could be used for either basic management, communication, or public engagement. There are definitely further directions that I could take this. I also learned more about horticulture and urban ecology and I gained a greater respect for trees and the people who take care of them.
