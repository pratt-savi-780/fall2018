---
layout: project-page
title: "Missed Connections"
linkname: missed-connections
author: "Albert Goncalves"
tagline: "Simple interactive web-map displaying connections between MTA subway lines responsive to keyboard input. Direct keyboard input of any given subway line will render the given subway line and its entrances (for the R-line, simply press 'r', etc.). Subsequent keyboard input will draw subway lines but narrow down the selection of subway entrances, leaving only those entrances which feature all selected subway lines... or no entrances if none match the accumulated search criteria. Mouse hovering over entrances will display the street nearest street intersection. Best viewed in Chrome."
location:
    - place: New York, NY, USA
project-link:
    - href: https://albertgoncalves.github.io/SAVI-780-final/
tags:
    - tag: subway
    - tag:  interactivity
    - tag:  nyc
    - tag:  mta
    - tag:  transit
thumbnail-path: img/missed-connections/C8Ai4eo.png
img-folder: ../../img/missed-connections/
timestamp: 10/17/2018 22:58:15
---

As opposed to being born of any sort of research or data-related question, the my project grew out of an interest in implementing some sort of novel keyboard-based interactivity. My initial concept was something along of the lines of enabling a sort of dynamic, fuzzy filtering of on-screen data via sequences of keyboard input, as if the user was directly typing into the page's HTML. Though interesting, this idea seemed to require a _very particular_ kind of dataset; one that I was unable locate.

My backup plan was had something to do with an interactive map featuring US railroads, though again early exploration seemed to provide closures instead of openings. Most of the available data I came across was _enormous_ in size, and without much specific knowledge of what I was looking for, I had a hard time justifying the various ways to refine the search space.

At some point [my unconscious](https://www.sciencedaily.com/releases/2008/04/080414145705.htm) did the work of correcting, and perhaps _concatenating_, these two ideas into something usable; from their non-inertia came the idea to use single-stroke keyboard inputs to render MTA subway lines. Soon this narrowed into the premise of using sequential keyboard input to search for station entrances featuring multiple subway lines.

---

Breaking ground on the project entailed first gathering subway data and working out some sort of _filtering_ strategy. My hope was there would be sufficient `string` data in the line and point features in order to facilitate a precise `string`-filtering approach (as opposed to using messy and [perilous](https://www.google.com/search?q=problems+with+spatial+joins&oq=problems+with+spatial+joins) spatial relationships).

Data was acquired through a dependable [old](https://data.cityofnewyork.us/Transportation/Subway-Lines/3qz8-muuu) [friend](https://data.cityofnewyork.us/Transportation/Subway-Entrances/drex-xx56), and required only some minor cleaning in order to be put to use. Early data exploration and preprocessing was done in [🐍](https://www.python.org/) with the help of the **always** useful [GeoPandas](http://geopandas.org/) library.

---

Early experiments bore fruit.

![]({{ page.img-folder }}pxnan6v.png)

---

![]({{ page.img-folder }}TxtE0GO.png)

It seemed, without too much difficulty, the exact search results I had in mind could be achieved via [simple filtering](https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.str.contains.html).

---

Given the relatively small size of the two datasets, I was able to simplify things early on; instead of hosting the data and loading it onto the page via an API call, I simply gave them variable assignments and socketed them directly into the page's HTML.

```javascript
var lines = {
"type": "FeatureCollection",
...
};
```

```javascript
var stations = {
"type": "FeatureCollection",
...
};
```

```html
...
<script src="./subway_lines_js.geojson"></script>
<script src="./subway_stations_js.geojson"></script>
...
```

---

The real labor of the project came down to plugging together a number of small functions to respond to specific set of keyboard inputs which would trigger two independent search algorithms. My thought was in order to facilitate and a near-instantaneous user experience, it would be best to keep the amount of data searched on each keyboard press to a minimum. Additionally, continually reducing the search space would reduce the need to clear overlapping map layers.

Searching the entrance data was [relatively](https://github.com/albertgoncalves/SAVI-780-final/blob/master/script.ts#L100) simple, the only requirement was organizing the data-flow in such a way that after the first input, the data searched was the previous results.

The lines required a [different](https://github.com/albertgoncalves/SAVI-780-final/blob/master/script.ts#L107) approach. As opposed to the subway entrances which are continually eliminated from the map, the subway lines persist after they are drawn. My solution was to design a simple structure that would return a nested `object`, with one `key: value` pair containing the matching data that would be rendered on the map, the other pair containing all the remaining line data. With this approach, each successive input reduced the search space by the number of rows arriving on the map. At the same time, this also addressed the need to clear the existing lines: since the same line segment was never redraw not clearing action was required and there would be no build-up of overlapping map data.

---

For the most part, getting these search functions in place was the real tricky part. I assembled a mapping of subway line names and colors which were sourced on key input, providing the correct color to the given subway line. This mapping also came into play when working out a means of displaying the subway line icons, which constituted the project's last legs.

Subway icons, rendering in an empty space above the map, were drawn via SVG. Once I worked out [a few needed functions](https://github.com/albertgoncalves/SAVI-780-final/blob/master/circles/script.js), it was `Hello, world!` as far as the eye could see.

![]({{ page.img-folder }}lY3VD9E.png)

---

A last touch was to source out a dark-background tileset in order to give contrast to the bright MTA subway color palette. [OpenWhateverMap](http://openwhatevermap.xyz) came in handy.

The SVG text uses `Helvetica` in order to best approximate [the real McCoy](https://en.wikipedia.org/wiki/The_real_McCoy).

![]({{ page.img-folder }}4wxOk74.png)

---

Left on the cutting room floor was any sort of instructions or explanatory text on the map page, though (fingers crossed) I'll find time for those elements in the <s>days</s> weeks following the classes' conclusion.

All of my development was done in Chrome; showing the page off to one of my coworkers fell a little short of the mark when they proceeded to open the page in Firefox. Of note, the `ESC` key fails to reload the page in Firefox, and the SVG text does not seem to display correctly. These issues will also be addressed at some point down the line.
