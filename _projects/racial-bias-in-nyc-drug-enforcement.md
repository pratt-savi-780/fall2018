---
layout: project-page
title: "Racial Bias in NYC: Drug Enforcement"
linkname: racial-bias-in-nyc-drug-enforcement
author: "Paul Jarymowycz"
tagline: "This map visually portrays drug enforcement by racial demographics in NYC. It shows that police precincts with larger Black and Hispanic populations have disproportionately higher rates of felony and misdemeanor drug offenses recorded than drug use statistics would imply, suggesting that racial bias is a factor."
location:
    - place: New York, NY, USA
project-link:
    - href: https://pjarymowycz.github.io/savi780-final-project/
tags:
    - tag: race
    - tag:  bias
    - tag:  policing
    - tag:  NYPD
    - tag:  drug enforcement
thumbnail-path: img/racial-bias-in-nyc-drug-enforcement/Pj98goK.png
img-folder: ../../img/racial-bias-in-nyc-drug-enforcement/
timestamp: 10/17/2018 23:36:41
---
Racial Bias in NYC:
Drug Enforcement

Racial bias in policing is well documented in the US, but not always visible. Although drug use is relatively equal across all racial demographics, arrests and convictions for drug related felonies and misdemeanors fall disproportionately on Black and Hispanic populations. The NYPD often claims that the racial disparity in policing, and Quality of Life (Broken Windows) policing in particular, is due to factors other than racial bias. However, these factors are often misleading and cannot fully explain patterns visible in the data, especially in the disparity between drug use and convictions.

See [Innocence Project](https://www.innocenceproject.org/racial-disparities-in-nyc-arrest-data-marijuana-possession/) and [drugpolicy.org](https://www.drugpolicy.org/sites/default/files/Race-Class-NYPD-Marijuana-Arrests-Oct-2014.pdf) for more information.

This map visually portrays drug enforcement by racial demographics in NYC. It was created from Substance Abuse and Mental Health Services Administration, American Community Survey, and historic NYPD crime data, as well as 311 and poverty data for comparison with the NYPD’s examples of crime enforcement indicators. Unfortunately, due to limited open availability of some NYPD data (specifically 911 call records and racial demographics for much of the crime data), this map can only provide estimated results. Limited data availability itself is part of the issue with documenting racial bias in policing, and this map also tries to show the difficulty in assessing police crime enforcement indicators with incomplete data.

The original datasets used in this project were analyzed using QGIS 3.0.2 and Microsoft Excel to align them to the relevant NYC police precinct polygons. Demographic and poverty data was imported at census tract and community district levels respectively. These were clipped to the precinct polygons and joined with the associated precinct number. Their attribute tables were then exported to CSV files. Excel pivot tables were used to weigh each attribute by the clipped size to the original size and sum the weighted values over each precinct. This data was re-joined to the police precinct polygons in QGIS.

![]({{ page.img-folder }}pSNHlww.png)

Other data was available as points or per precinct, and this was simply summed over each precinct in QGIS. All required attributes were then joined in a single precinct map, which was exported as a geoJSON, and this file’s geometry was simplified on mapshaper.org due to file size considerations.

![]({{ page.img-folder }}ryfZl75.png)

Ultimately, by comparing estimated drug use and drug crime statistics in NYC, this map shows that police precincts with larger Black and Hispanic populations have disproportionately higher rates of felony and misdemeanor drug offenses recorded than drug use statistics would imply, suggesting that racial bias is a factor.

Map Screenshots:
Demographics: ![]({{ page.img-folder }}BxPADQY.png)
Estimated drug use: ![]({{ page.img-folder }}q9QcbVQ.png)
Misdemeanor drug offenses: ![]({{ page.img-folder }}WVkbxJm.png)
Drug offenses by demographic: ![]({{ page.img-folder }}Pj98goK.png)
