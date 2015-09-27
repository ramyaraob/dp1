---
title: "Course Project Developing Data Products"
author: "Ramya Rao"
date: "Sunday, September 27, 2015"
output: slidy_presentation
---

## Iris Flower Family Predictor operation

The application consists of a left panel with four sliders, for petal length width and sepal length and width. 

The right panel displays the output of the prediction for the current user inputs.

As the user modifies the inputs by sliding the slider, each slider input is converted into measurements in centimeters and used to predict the family.

The predictor is developed using Random trees and the training data is the 'iris' data set available in the r data sets, which represents Edgar Anderson's Iris Data.

The prediction is based on the data provided in the Edgar Anderson's Iris Data.

This famous (Fisher's or Anderson's) iris data set gives the measurements in centimeters of the variables sepal length and width and petal length and width, respectively, for 50 flowers from each of 3 species of iris. The species are Iris setosa, versicolor, and virginica

Further details can be obtained from the documentation of iris data set.



---

## Operation

The predictor will calculate and predict the family the considered flower would belong to.
Iris is a genus of 260-300[1][2] species of flowering plants with showy flowers. It takes its name from the Greek word for a rainbow, which is also the name for the Greek goddess of the rainbow, Iris.
The Iris genera is subclassified based on the sepal and petal dimensions. To calculate this data the predictor application can be used.

Below is the operation of the predictor

```r
library(caret)
tempTrain <- createDataPartition(y=iris$Species, p=0.7, list=FALSE)
  
  forTraining <- iris[tempTrain,] 
  forTesting <- iris[-tempTrain,]
  
  require(randomForest)
  set.seed(12345)
  
  rfTraining=randomForest(Species~.,data=forTraining,ntree=100, importance=TRUE)
```

---
The prediction model analysis


```r
rfTraining
```

```
## 
## Call:
##  randomForest(formula = Species ~ ., data = forTraining, ntree = 100,      importance = TRUE) 
##                Type of random forest: classification
##                      Number of trees: 100
## No. of variables tried at each split: 2
## 
##         OOB estimate of  error rate: 8.57%
## Confusion matrix:
##            setosa versicolor virginica class.error
## setosa         35          0         0   0.0000000
## versicolor      0         31         4   0.1142857
## virginica       0          5        30   0.1428571
```

---

## Thank you

The application is available at https://ramyaraob.shinyapps.io/dataproduct

The related code and other documentation can be found at https://github.com/ramyaraob/developdataproduct

