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

<p>This is a simple app that uses "melanom" dataset form the ISwR package in R.  The app gets Kaplan-Meier survival parameter estimates based on the stratifications specified.  As long as the user knows how to operate a pulldown menu they should have no problem using this app.</p>

--- .class #id 

## Data Set

<p>More information on the "melanom" dataset can be found in the  <a href="http://cran.r-project.org/web/packages/ISwR/ISwR.pdf">ISwR package documention</a>.  Specifically see page 18.
</p>

To save you the trouble here are the variables:

```
## [1] "no"     "status" "days"   "ulc"    "thick"  "sex"
```



---
### Dataset Continued
Here are some summaries of the specific variables of interest used in my Shiny app:

```r
table(melanom$sex)
```

```
## 
##   1   2 
## 126  79
```

```r
table(melanom$status)
```

```
## 
##   1   2   3 
##  57 134  14
```

```r
summary(melanom$days)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##      10    1520    2000    2150    3040    5560
```


My Shiny app groups the censoring variable "status".  The levels 2 and 3 are recoded to 0 and considered censored events.  Also of note for the sex variable 1 is female and 2 is male.
