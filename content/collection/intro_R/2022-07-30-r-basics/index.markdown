---
title: R Basics
author: Juan Quinonez
date: '2022-07-30'
slug: []
categories:
  - R
tags: []
weight: 2
---

R is a programming language that’s optimized for statistical analysis and data visualization. It is used with RStudio, a very common IDE for R that is transitioning to [Posit](https://urldefense.com/v3/__https://posit.co__;!!MXQJGYEVCjwd!UDf6YH6TmRbogZJPDq0FY_4sg14ZlvgZgoMnylWOYf3Nfp_wIfCJGmKCQdh1g8GF9VMPbgPZqhPYZqaUgu0hPfM6XQ$ ) a new developing tool that support several other programming languages (such as Python, similar to VC Studio). Although this might be obsolete in a few months, we will show how to install RStudio in the first section and comment the general environment on the section one. Following these sections we'll cover the basics of some of the most common R objects and how to work with them using just base functions.

## Installation Guide
A very detailed guide showing the steps to install R and RStudio can be found in [TechVidvan](https://urldefense.com/v3/__https://techvidvan.com/tutorials/install-r/__;!!MXQJGYEVCjwd!UDf6YH6TmRbogZJPDq0FY_4sg14ZlvgZgoMnylWOYf3Nfp_wIfCJGmKCQdh1g8GF9VMPbgPZqhPYZqaUgu0PDi-1vA$ ) website. In general terms, one has to choose the R version according to one's operative system and then download [R](https://urldefense.com/v3/__https://cran.r-project.org__;!!MXQJGYEVCjwd!UDf6YH6TmRbogZJPDq0FY_4sg14ZlvgZgoMnylWOYf3Nfp_wIfCJGmKCQdh1g8GF9VMPbgPZqhPYZqaUgu17PwZrbA$ ) and then [RStudio](https://urldefense.com/v3/__https://www.rstudio.com/products/rstudio/__;!!MXQJGYEVCjwd!UDf6YH6TmRbogZJPDq0FY_4sg14ZlvgZgoMnylWOYf3Nfp_wIfCJGmKCQdh1g8GF9VMPbgPZqhPYZqaUgu0ScQZXwA$ ).

## Environment
At first, the initial window of RStudio can be a little intimidating, because there are a lot of options and too much white space.


## General Structures
R uses different kind of object to work with, in this section we will cover some of the most important ones and show how to work with them using base functions.

Most of the material used it this section is taken from [w3school](https://www.w3schools.com/r/default.asp) and also from *Wickham* (r4ds.had.co.nz)

### Vectors
Vectors are the simplest data structures in R and represent a list of items. *Wickham* classify vectors based on the data they contain:
- *Atomic vectors:* These are vectors that contain homogeneous data, which can be logical, integer, double, character, complex, and raw.

- *List:* These are heterogeneous vectors that can contain other vectors with different structures (data types and lengths).

#### Atomic Vectors
To create an atomic vector you can use the `c()` function and bind together several values of **the same** type.


```r
lgl <- c(TRUE, FALSE, FALSE, TRUE)
int <- c(1,2,3,4,5,6)
dbl <- c(1.2, 3.4, 5.6)
char <- c("this", "is", "a", "character", "vector")
```

Operations with vectors will depend on the type of data they contain. The following examples are carried out with character vectors. You can access elements of a vector using []

```r
pets <- c("dog", "cat", "fish", "bird", "snakes")

pets[2] # selects cats
```

```
## [1] "cat"
```

```r
pets[c(2,4)] # selects cats and bird
```

```
## [1] "cat"  "bird"
```

```r
pets[-5] # selects everything but snakes
```

```
## [1] "dog"  "cat"  "fish" "bird"
```

Using number vectors (integers or doubles) will allow use arithmetic functions and many more.

```r
x <- c(1, 2, 3, 5, 7, 11)
y <- seq(10:5)

# Addition
x + y
```

```
## [1]  2  4  6  9 12 17
```

```r
# Multiplication
x*y
```

```
## [1]  1  4  9 20 35 66
```

```r
# Division
x/y
```

```
## [1] 1.000000 1.000000 1.000000 1.250000 1.400000 1.833333
```

```r
# Power
x^y
```

```
## [1]       1       4      27     625   16807 1771561
```
Vectors are R's most basic object.

#### Lists
List are a collection of vectors, they can contain vectors with different data types, and even lists. To create a list, we can use the `list()` function.


```r
x <- list(1, 2, 3)
x
```

```
## [[1]]
## [1] 1
## 
## [[2]]
## [1] 2
## 
## [[3]]
## [1] 3
```

```r
y <- list("a", 1L, 1.5, TRUE)
y
```

```
## [[1]]
## [1] "a"
## 
## [[2]]
## [1] 1
## 
## [[3]]
## [1] 1.5
## 
## [[4]]
## [1] TRUE
```

Accessing elements inside a list can be done using the []

```r
a <- list(a = 1:3, b = "a string", c = pi, d = list(-1, -5))

a[1:2] # selects the elements a and b
```

```
## $a
## [1] 1 2 3
## 
## $b
## [1] "a string"
```

```r
a[[1]] # extracts a single component from a list
```

```
## [1] 1 2 3
```
### Factors
Factors are used to categorize data, like male/female; first/second/third. Some times, factors can be used to show order of importance in different categories.


```r
music <- factor(c("Jazz", "Rock", "Classic"))
music
```

```
## [1] Jazz    Rock    Classic
## Levels: Classic Jazz Rock
```
By default, factors are ordered by alphabetical order. This can be changed:

```r
levels(music) <- c("Rock", "Jazz", "Classic")
music
```

```
## [1] Jazz    Classic Rock   
## Levels: Rock Jazz Classic
```
To access the items in a factor, refer to the index number, using [] brackets:

```r
music[2] # Selects the second element.
```

```
## [1] Classic
## Levels: Rock Jazz Classic
```

### Matrices
A matrix is a two dimensional data set with columns and rows. A column is a vertical representation of data, while a row is a horizontal representation of data. A matrix can be created with the `matrix()` function. Specify the `nrow` and `ncol` parameters to get the amount of rows and columns.

```r
A <- matrix(c(1:10), nrow = 5, ncol = 2)
A
```

```
##      [,1] [,2]
## [1,]    1    6
## [2,]    2    7
## [3,]    3    8
## [4,]    4    9
## [5,]    5   10
```
To access the items in a matrix, refer to the index number, using [] brackets, specifying the row and column number.

```r
A[1, 2] # selects the first row - second column element
```

```
## [1] 6
```

```r
A[1,] # select first row
```

```
## [1] 1 6
```

### Data Frames
Data Frames are data displayed in a format as a table, similar to matrices. While the latter can hold only elements of the same class, data frames can store columns of different classes.

Use the `data.frame()` function to create a data frame.

```r
df <- data.frame (
  Training = c("Strength", "Stamina", "Other"),
  Pulse = c(100, 150, 120),
  Duration = c(60, 30, 45)
)
df
```

```
##   Training Pulse Duration
## 1 Strength   100       60
## 2  Stamina   150       30
## 3    Other   120       45
```

There are different ways of accessing elements of a data frame:

```r
df <- data.frame (
  Training = c("Strength", "Stamina", "Other"),
  Pulse = c(100, 150, 120),
  Duration = c(60, 30, 45)
)

df[1]
```

```
##   Training
## 1 Strength
## 2  Stamina
## 3    Other
```

```r
df[["Training"]]
```

```
## [1] "Strength" "Stamina"  "Other"
```

```r
df$Training
```

```
## [1] "Strength" "Stamina"  "Other"
```


## Basic Visualization

### Plot

### Line

### Scatterplot

### Bar plot

### Pie charts

