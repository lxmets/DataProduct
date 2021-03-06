---
title       : Water Footprint Calculator
subtitle    : (calculates at a weekly granularity)
author      : WFP
job         : Data Science
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
<style>
.title-slide {
  background-color: #cce5ff; 
}
.title-slide hgroup > h1{
  font-family: 'Oswald', sans-serif;
}

.title-slide hgroup > h2{
  font-family: 'Oswald', 'Calibri', sans-serif;
}

/* Fonts and Spacing */
article p, article li, article li.build, section p, section li{
  font-family: 'Open Sans','Helvetica', 'Crimson Text', 'Garamond',  'Palatino', sans-serif;
  text-align: justify;
  font-size:22px;
  line-height: 1.5em;
  color: #444;
}

slide:not(.segue) h2{
  font-family: 'Calibri', Arial, sans-serif;
  font-size: 52px;
  font-style: normal;
  font-weight: bold;
  text-transform: normal;
  letter-spacing: -2px;
  line-height: 1.2em;
/*  color: #193441;*/
/*  color: #02574D;*/
  color: #CC2904;
}
body {
  background-color: #cce5ff;
}
</style>
<style>
em {
  font-style: italic
}
</style>
<style>
strong {
  font-weight: bold;
}
</style>

## What is a Water Footprint?

### Water footprint of a consumer - 

Is defined as the total volume of freshwater consumed and polluted for the production of the goods and services consumed by the consumer. It is calculated by adding the direct water use by people and their indirect water use. The latter can be found 
by multiplying all goods and services consumed by their respective water footprint.


(Source: *Hoekstra, A.Y., Chapagain, A.K., Aldaya, M.M. and Mekonnen, M.M. (2011) The water footprint assessment manual: Setting the global standard, Earthscan, London, UK*)

---

## Why Water Footprint?

In a world where every person and their actions are monitored, we become a sum total of numbers such as our:

1. BMI
2. Credit Score
3. Fitness Activity Record

etc.


Shouldn't we then be conscious of how much of the world's water resources we consume?

---

## How to compute the Water Footprint ?

There are several categoties of water footprint as described by the [Water Footprint Network](http://waterfootprint.org/en/water-footprint/glossary/)

1. Blue Water Footprint
2. Green Water Footprint
3. Grey Water Footprint

etc.

We calculate the water footprint for a consumer based on the amount of produce they consume in a week. We use the water footprint data  for each produce item computed by [Hoekstra](http://waterfootprint.org/media/downloads/Hoekstra-2008-WaterfootprintFood.pdf) and multiply it by the amount of produce consumed in a week to get their total water consumption. The water footprint is given in the units of **gal/lb**. 

**Note:** Depending on the type of water footprint, the units also change from *gal/lb* to *gal/hectare*, etc.

--- 

## Example Calculation

For example, let us say in one week, my family consumes: 2 lb of apples, 1.4 lb of bananas and 3.5 lb of tomatoes

Then our waterfootprint is calculated as follows:


```r
a = 2; b = 1.4; t = 3.5
wA <- 83.88 # water footprint for apples in gal/lb
wB <- 103.05 # water footprint for bananas in gal/lb
wT <- 21.57 # water footprint for tomatoes in gal/lb
         
totalWater <- a*wA + b*wB + t*wT  
totalPounds <- a + b + t
round(totalWater/totalPounds,0)
```

```
## [1] 56
```





