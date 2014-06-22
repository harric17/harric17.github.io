---
title       : Class Project
subtitle    : Practical Machine Learning, June 2014
author      : Will Harris
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

A significant challenge to today's data scientists is extracting meaningful insights from the large volumes of data that are continuously being collected from a variety of sources.   The goal of this analysis was to develop an accurate algorithm for predicting the manner of exercise being performed by 6 participants based on measurements collected from inexpensive personal activity sensors.


--- .class #id 

## Methods

The training dataset contained 19622 observations across 160 variables.  The testing set contained 20 observations, though it did not contain information related to the outcome measure.  The outcome variable of interest, classe, is a categorical variable consisting of 5 different levels.   A random forest model was fit to predict this categorical outcome.

There was substantial data management required for this analysis.  First, five variables were excluded as obvious noise: X, problem_id, raw_timestamp_part_1, raw_timestamp_part_2, and cvtd_timestamp.  Next, variables that had exclusively missing values in the test set were also excluded.  This resulted in a dataset with 55 predictor variables, two of which were factors with the remaining numeric. 
The training dataset was then ultimately divided.  Using a random uniform number generator a small subset of exactly 3000 observations was used to train the random forest model and the remaining data was set aside for further validation of the model.  Ultimately this smaller training subset contained levels of the factor variables that were not in the test data set, so the two factor variables were also additionally excluded from the analysis.  A forest of 500 trees was created, and the number of variables randomly chosen at each split was left as the default value, which was 7.



---

## Methods

## Table 1
 [1] "num_window"           "roll_belt"            "pitch_belt"          
 [4] "yaw_belt"             "total_accel_belt"     "gyros_belt_x"        
 [7] "gyros_belt_y"         "gyros_belt_z"         "accel_belt_x"        
[10] "accel_belt_y"         "accel_belt_z"         "magnet_belt_x"       
[13] "magnet_belt_y"        "magnet_belt_z"        "roll_arm"            
[16] "pitch_arm"            "yaw_arm"              "total_accel_arm"     
[19] "gyros_arm_x"          "gyros_arm_y"          "gyros_arm_z"         
[22] "accel_arm_x"          "accel_arm_y"          "accel_arm_z"         
[25] "magnet_arm_x"         "magnet_arm_y"         "magnet_arm_z"        
[28] "roll_dumbbell"        "pitch_dumbbell"       "yaw_dumbbell"        
[31] "total_accel_dumbbell" "gyros_dumbbell_x"     "gyros_dumbbell_y"    
[34] "gyros_dumbbell_z"     "accel_dumbbell_x"     "accel_dumbbell_y"    
[37] "accel_dumbbell_z"     "magnet_dumbbell_x"    "magnet_dumbbell_y"   
[40] "magnet_dumbbell_z"    "roll_forearm"         "pitch_forearm"       
[43] "yaw_forearm"          "total_accel_forearm"  "gyros_forearm_x"     
[46] "gyros_forearm_y"      "gyros_forearm_z"      "accel_forearm_x"     
[49] "accel_forearm_y"      "accel_forearm_z"      "magnet_forearm_x"    
[52] "magnet_forearm_y"     "magnet_forearm_z"     "classe"              

