---
title       : Developing Data Products
subtitle    : Peer Assignment (Airport Demo)
author      : Kevin Scarr
job         : June 2014
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Overview

The demonstrator shows flights between airports for the countries that the user selects.  

This allows the user to choose to see national and international flights shown on a force directed graph
 (a graph showing directions).
 
The inspiration for the demo comes from wanting to use a slightly different data-set to the normal ones 
and experimenting with the *'igraph'* module.

![screenshot](screenshot.png "Screenshot")

--- .class #id 

## Instructions for use

The following instructions guide a user around the [demonstrator](https://scarrk.shinyapps.io/PeerAssignmentAirport/):-

1. Select a country (or countries) from multi-selector on the left hand side panel
2. The 'Graph' tab illustrates a visual representation of flights between the airports that exist in
 the selected countries (the airport short code is shown)
3. The 'chart summary' shows the popular airports measured by outbound flights in a bar chart

The remaining tabs provide filtered tabular views on the data with 'All Airports' allowing a user
to search through the master list of airports in the dataset.

By removing (select the country and tap the delete key) and adding countries (click on the item in the list) on the left side panel you can see which countries have international flights between them, otherwise with a single country selected you will see national only flights.

Countries with large numbers of airports and flights may take time to render in the graph view.

--- .class #id 

## Data Set

The demonstrator uses an open source dataset available from [OpenFlights.org](http://openflights.org/data.html#airport) which holds a set of airports and flights (or routes) between them and has a enough records 
to support the demo.




The airports data-set was filtered to only include those that had one or more flights available.  There are 3272 airports and 59637 flights recorded in the data-set.


```r
smoothScatter(airports[, c("Latitude", "Longitude")])
```

![plot of chunk heatmap](assets/fig/heatmap.png) 

Plot shows a heatmap of airports using Latitude and Longitude.

--- .class #id 

## Summary

### Libraries
* Shiny
* igraph
* plyr
* ggplot2

### Acknowledgements

* http://openflights.org

### Testing
 
* R version 3.1.0 / Windows 7 64bit
