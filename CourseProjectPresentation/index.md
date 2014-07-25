---
title       : Analysis of mtcars dataset (Shiny App)
subtitle    : Developing Data Products (Course Project)
author      : Rocio Elizalde
job         : Data Scientist
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

The Shiny app is part of the course project of the *Developing Data Products* course in Coursera. 

This app uses data from the `mtcars` dataset, the data was extracted from the 1974 Motor Trend US magazine, and comprises fuel consumption and 10 aspects of automobile design and performance for 32 automobiles (1973-74 models).

The `mtcars` dataset consists in a data frame with 32 observations on 11 variables.

For the purpose of the application, we only worked with the `mpg`, `cyl` and `am` variables.

- [, 1] mpg    Miles/(US) gallon
- [, 2] cyl	Number of cylinders
- [, 9]	am	Transmission (0 = automatic, 1 = manual)

--- .class #id 

## Description of the User Interface

The Shiny app consists in a `ggplot2` boxplot of `mpg` by number of `cyl`, comparing *automatic*  and *manual* transmission. The app also displays the number of cars analyzed and the table with the data. The user needs to select the number of cylnders as a filter for the original data.

The outputs of the app are "reactive" and therefore should re-execute automatically when inputs change.

--- .class #id

## Internal Operations

Considering the user selection, the app filters the original `mtcars` dataset. It displays on the sidebar the data filtered and on the main section displays the number of cars analyzed and plot the mileage by cylinder number for this data.

The total number of cars analyzed is calculated as following (for the purpose of this example we assume the user select 4 and 6 cylinders in the car):




```r
x <- row.names(mtcars[mtcars$cyl %in% c(4,6),])
        
cat('Total number of cars analyzed: ', as.character(length(x)))
```

```
## Total number of cars analyzed:  18
```

On the following slide the resultant Shiny app is shown.

--- .class #id

<iframe src=http://relizalde.shinyapps.io/DataProductsProject></iframe>
