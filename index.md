---
title       : Basal Metabolic Rate
subtitle    : Calculating Basal Metabolic Rate using R and Shiny
author      : iambritishdaniel
job         :
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
## Introduction

Your Basal Metabolic Rate (BMR) is defined as the minimum number of calories your body burns whether at rest, working out or lying down. These calories are the absolute minimum amount of energy your body burns, and includes all involuntary activities that your body does to stay alive such as digestion, respiration, circulation, removing waste products and regulating body temperature. Factors that affect your BMR include age, genetics, weight, heredity, body fat percentage and gender [1]. 

Your BMR is a useful number to know as it helps you know how much calories to take in as food and drink: consume more calories than your BMR and you are likely to gain weight, consume fewer calories than your BMR (either by eating fewer calories, or increasing activity to raise your BMR) and you have a better chance of losing weight.

--- 

## Mifflin St. Jeor Equation

The BMR Calculator app presented here uses the Mifflin St. Joer Equation, developed by M.D. Mifflin *et al* in 1990 to calculate a person's BMR [2]. The Mifflin St. Joer equation is the most accurate for estimating an individual's BMR without knowing body fat percentage - For this reason it is perfect for developing a simple online BMR calculator.

The Mifflin St. Joer Equation needs 4 pieces of information:
 1. The person's gender.
 2. The person's age.
 3. The person's height (in cm)
 4. The person's weight (in kg)

BMR is calculated as follows:  
*BMR* = (10 * weight) + (6.25 * height) - (5 * age) + S, where S is 5 for men and -161 for women [2].

---

## Example

Suppose a 37 year old man, weighing 180lbs and 5' 8" tall were to use the calculator - what would his BMR be?  

```r
age <- 37
s <- 5 # because person is male
height <- ((5 * 12) + 8) / 0.393700787402 # convert to metric units: 1cm ~ 0.394" [3]
weight <- 180 / 2.20462262185 # convert to metric units: 1kg ~ 2.2lbs [3]
```
Now we can plug the numbers into the formula

```r
(10 * weight) + (6.25 * height) - (5 * age) + s
```

```
## [1] 1715.966
```

---

## References

[1] L.L. Taylor, *Basal Metabolic Rate*, [http://www.shapefit.com/basal-metabolic-rate.html]  
[2] Wikipedia, *Basal metabolic rate*, [http://en.wikipedia.org/wiki/Basal_metabolic_rate]  
[3] Conversion factors obtained from [http://www.convertunits.com/]  

<center style="margin-top: 150px;"><h2>Thank you!</h2></center>






