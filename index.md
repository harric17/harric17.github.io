---
title       : Developing Data Products Project
subtitle    : August 2014
author      : harric17
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
## Introduction

<p>My project Shiny app is hosted at <a href="http://harric17.shinyapps.io/project/">this website</a>.
</p>

<p>This is a simple app that uses "melanom" dataset form the ISwR package in R.  The app gets Kaplan-Meier survival parameter estimates based on the stratifications specified.  </p>

--- .class #id 

## Data Set

<p>More information on the "melanom" dataset can be found in the  <a href="http://cran.r-project.org/web/packages/ISwR/ISwR.pdf">ISwR package documention</a>.  Specifically see page 18.
</p>

To save you some trouble here are the variables in the dataset:

```
## [1] "no"     "status" "days"   "ulc"    "thick"  "sex"
```



---
## Dataset Continued
In this analysis only the variables "days", "status", and "sex" are used.  The Shiny app regroups "status" so that levels 2 and 3 are recoded to 0 and considered censored events.  Here a summary of the sex variable which is used for stratification:

```r
table(melanom$sex)
```

```
## 
##   1   2 
## 126  79
```

For the sex variable 1 is female and 2 is male.

---
## How to Use the Shiny App
This app is pretty straight forward to use.  As long as the user knows how to operate a pulldown menu they should have no problem with this app.

Kaplain-Meier parameter estimates are displayed for both unstratfied and stratified data.  When choosing to stratify on sex the results of the log-rank test are additionally shown.

---
## Conclusion

Though this Shiny app is pretty trivial, its usefulness is clear.  It seems like an excellent tool for facilitating both exploration of data as well as communication between programmers/statisticians and other interested parties (e.g. scientists).

---

## The End

<center><img src="http://i.imgur.com/0Y5Dy7y.jpg" height="500" width="500"></center>
