---
layout: project-page
title: "A Cup At Origin - Coffee Consumption Producing Countries"
linkname: a-cup-at-origin-coffee-consumption-producing-countries
author: "Angie Magnusson"
tagline: "The global trading price for green coffee is in the doldrums. On September 17, 2018, the price for one pound of coffee reached a 12-year low of 93.45 cents.

For producers, these global prices oftentimes don't even come close to covering the costs of production. So instead of marketing their crop for international export (where the price is determined by the low market), supply chain actors in producing countries look to domestic consumption for the demand needed to sell their crop."
location:
    - place: global
project-link:
    - href: https://angimarose.github.io/origin-consumption-map/
tags:
    - tag: coffee, global agricultural commodity, supply and demand, commodity prices, market access, local consumption
thumbnail-path: img/a-cup-at-origin-coffee-consumption-producing-countries/coffee-cover.png
img-folder: ../../img/a-cup-at-origin-coffee-consumption-producing-countries/
timestamp: 10/17/2018 17:29:31
---
The aim of this project was to display the important relationship that exists within coffee producing countries toward domestic consumption. While increases in domestic consumption of coffee can oftentimes point to powerful social trends in a country to consume more locally produced coffee, it can also be an important reaction to very low global coffee prices. When the global coffee markets slump, producers/exporters may choose to hold their product back from the global trade and opt for a more proximal, immediate market. In addition to representing these market dynamics, I’m also very interested in the popularity of this luxury agricultural commodity within the country it is grown. 

With this map, the change in domestic coffee consumption is displayed over time. This is calculated by using a percent change in the per capita consumption of roasted coffee between 2001-2017. To this end, both data on the domestic consumption by origin was needed, along with the population by year. The data on domestic coffee consumption is from the International Coffee Organization, and population data is sourced from the UN World Population Prospects 2017. Using these datasets, first the per capita consumption of roasted coffee was calculated (the weight loss conversion from green to roasted coffee is approximately 20%). Originally, I had been aiming to display this change over time using a time slider by the year.

![]({{ page.img-folder }}l8f4G5j.png)

![]({{ page.img-folder }}yrItLaY.png)

However, after spending a disproportionate amount of time sifting through and organizing the datasets, I was not able to put in the time I would have needed to initialize the time slider. In the end, the percent change between the years 2017 and 2001 was used as the proxy. 

To display this change in domestic coffee consumption at origin, I wanted to style the polygons as a choropleth. Using ArcMap, I loaded the geoJson I created from CARTO, and then styled these polygons based on natural jenks, 7 categories:

![]({{ page.img-folder }}AFWV0yb.png)

This gave me the breaks I needed to use in the code for the values to display in which category. I used Color Brewer to settle on some visually appealing colors and used their hex color code. 

![]({{ page.img-folder }}vFrVk5W.png)

The interactivity on this map comes from an ‘onEachFeature’ event listener for a ‘click’ on the polygon. Using Mustache, I was able to successfully display the country name and percent change in consumption in the sidebar.

![]({{ page.img-folder }}txAxb6O.png)

![]({{ page.img-folder }}bzM8Amx.png)

Challenges I faced were mainly in the JavaScript and wrapping my head around the correct order in which items needed to be loaded. I believe I spent too much time working with the data and slogging through a few datasets. I would expand on this project by creating more attractive event listeners - zoomToFeature on click, filtering data by predominant coffee species grown (Arabica vs. Robusta), and completely what I set out to do, which was to create three layers of data - total production, exports and domestic consumption - between which you could toggle.

Overall, this project turned out to have a more limited scope than I was initially expecting, but I did learn a lot along the way about project management and grappling with JavaScript. I hope to refine this project to the point where I could share it with our internal commodity research team. 
