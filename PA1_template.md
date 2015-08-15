---
title: "Reproducible Research-Assignment1"
author: "Sylvia"
date: "Sat, August 15, 2015"
output: html_document
---

This assignment makes use of data from a personal activity monitoring device. This device collects data at 5 minute intervals through out the day. The data consists of two months of data from an anonymous individual collected during the months of October and November, 2012 and include the number of steps taken in 5 minute intervals each day.

## Data

The data for this assignment can be downloaded from the course web site:

Dataset: https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2Factivity.zip

The variables included in this dataset are:

1. steps: Number of steps taking in a 5-minute interval (missing values are coded as NA)
2. date: The date on which the measurement was taken in YYYY-MM-DD format
3. interval: Identifier for the 5-minute interval in which measurement was taken

## Loading and preprocessing the data
Data are pre-downloaded and saved in working directory
Load data 


```r
data <- read.csv("activity.csv")
```
## What is mean total number of steps taken per day?

```r
library(ggplot2)

stepsday <- aggregate(steps ~ date, data, sum)
hist(stepsday$steps, main = paste("Total Steps Taken Per Day"), col="red", xlab="Number of Steps")
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png) 

```r
stepsByDayMean <- mean(stepsday$steps)
stepsByDayMedian <- median(stepsday$steps)
```
Mean of the total number of steps taken per day : 

```r
stepsByDayMean
```

```
## [1] 10766.19
```
Median of the total number of steps taken per day:

```r
stepsByDayMedian
```

```
## [1] 10765
```

## What is the average daily activity pattern?
