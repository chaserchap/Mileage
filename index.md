---
title       : Mileage Estimator
subtitle    : Proven Efficiency
author      : Chase Chapman
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## An Introduction
### What is Mileage Estimator?
A common question posed when purchasing a new car is what the mileage will be, as 
such companies must consider the fuel efficiency when designing a car. In order to 
calculate estimated efficiency many variables can be considered, and the process
can be cumbersome. To free up valuable development time we have created the 
Mileage Estimator.  With the Mileage Estimator your developers can make quick fact
based estimates to guide their designs.

---

## How it works
Mileage Estimator uses a sophisticated algorithm created from the 'mtcars' dataset
on R. Utilizing this dataset a linear model is created, as shown in the following:

```r
data(mtcars)
head(mtcars)
```

```
##                    mpg cyl disp  hp drat    wt  qsec vs am gear carb
## Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
## Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
## Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
## Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
## Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
## Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1
```
It can be seen in the above that there are various factors possibly related to mileage, however after performing several analyses it was decided that the two most influential factors were weight (wt) and number of cylinders (cyl). Thus these two data points were used in developing our model.

---

## Building our Model

```r
fit <- lm(mpg ~ as.factor(cyl) + wt, data = mtcars)
fit
```

```
## 
## Call:
## lm(formula = mpg ~ as.factor(cyl) + wt, data = mtcars)
## 
## Coefficients:
##     (Intercept)  as.factor(cyl)6  as.factor(cyl)8               wt  
##          33.991           -4.256           -6.071           -3.206
```
Thus our model is created, giving us the numbers necessary to adequately utilize weight and cylinders to estimate mileage.

---

## Conclusion
This has been a short introduction to the Mileage Estimator, emphasis on short. A lot of information can be said of this product, however, to better utilize time, much information was cut down.

That said, the product can increase production and design by saving time and effort of your designers. 





