Introduction to R
================

-   [Introduction](#introduction)
    -   [The R interface](#the-r-interface)
    -   [Other software to be used with R](#other-software-to-be-used-with-r)
    -   [Suggested literature](#suggested-literature)
-   [Starting simple with R](#starting-simple-with-r)
-   [Operators](#operators)
-   [The main classes](#the-main-classes)
    -   [Switching between classes](#switching-between-classes)
-   [Objects](#objects)
    -   [Creating objects](#creating-objects)
    -   [Modifying objects](#modifying-objects)
    -   [Modifying objects part 2](#modifying-objects-part-2)
    -   [Switching classes](#switching-classes)
-   [Loading and saving from R](#loading-and-saving-from-r)
    -   [Reading from files](#reading-from-files)
    -   [Save to files](#save-to-files)
-   [Describing data using descriptive statistics](#describing-data-using-descriptive-statistics)
-   [Packages](#packages)
-   [Plotting](#plotting)
    -   [Saving plots](#saving-plots)
-   [Correlation tests in R](#correlation-tests-in-r)
-   [Simple statistical models in R](#simple-statistical-models-in-r)
-   [More advanced R: creating and running for-loops and functions](#more-advanced-r-creating-and-running-for-loops-and-functions)
-   [Other topics that could be covered](#other-topics-that-could-be-covered)

This page can be found at:
<http://goo.gl/cWAAyv>

<br>

<br>

Introduction
============

The R interface
---------------

<img src="Rlogo.png" alt="Matlof"  width="150">

<br>

-   Originated from proprietary S programming language (80s) and developed into R (1995)

-   Comes in many flavours, like *R gui* (hardly a user interface), *Rstudio*, *Eclipse*

-   Save scripts as R files, which can be opened with all kinds of software (*R*, *Rstudio*, *Sublime*, *Notepad* etc. )

-   *Annotate scripts*: that means that one uses the hashtag to write in a few lines what is going on in that bit of syntax.

-   **Safer and more reproducible than other software**: source data is not changed, scripts can be shared with others

-   Save objects to \`Rdata files, so you can continue with it next time without the need for rerunning the complete script

-   Above all: it's FREE well maintained software with a large user community in each (scientific) field

<br>

<br>

Other software to be used with R
--------------------------------

-   Rstudio is very useful: <https://www.rstudio.com/products/RStudio/>

It has many advantages: integrated help, use of tab key, more stable than Rgui.

-   Sublime when only typing syntax (to link with servers): <https://www.sublimetext.com/>

-   Packages: for an (almost infinity) number of applications people have developed packages, for example:

CRAN: <https://cran.r-project.org/>

Bioconductor: <http://bioconductor.org/>

-   Git to track your code: www.github.com

<br>

<br>

Suggested literature
--------------------

Google is your best friend. Every question has been asked more than once by someone else!

*The art of R programming, Normal Matlof, Starch Press*

<img src="ArtOfR.jpeg" alt="Matlof"  width="150">

*Introductory Statistics with R, Peter Dalgaard, Springer*

<img src="IntroWithR.jpeg" alt="Dalgaard" width="150">

<br>

<br>

Starting simple with R
======================

``` r
1+1
```

    ## [1] 2

``` r
#Assign values to variables
a <- 1
a + a
```

    ## [1] 2

``` r
#But the equal sign also works!
aa = 1
aa+aa
```

    ## [1] 2

``` r
#But professionals use the arrow and not the equal sign to distinguish from  == :)

#Or multiple values or variables
b <- c(1,2,3) # c, concatenate
b
```

    ## [1] 1 2 3

``` r
#Variables can have any names, but don't assign names to existing objects, such as sum, c, sd etc
#Spaces are not allowed as well as special symbols


#Sequences
rep(x = 1,times = 5)
```

    ## [1] 1 1 1 1 1

``` r
seq(from = 1,to = 5, by=0.5)
```

    ## [1] 1.0 1.5 2.0 2.5 3.0 3.5 4.0 4.5 5.0

``` r
seq(from = 1,to = 5, length.out = 100)
```

    ##   [1] 1.000000 1.040404 1.080808 1.121212 1.161616 1.202020 1.242424
    ##   [8] 1.282828 1.323232 1.363636 1.404040 1.444444 1.484848 1.525253
    ##  [15] 1.565657 1.606061 1.646465 1.686869 1.727273 1.767677 1.808081
    ##  [22] 1.848485 1.888889 1.929293 1.969697 2.010101 2.050505 2.090909
    ##  [29] 2.131313 2.171717 2.212121 2.252525 2.292929 2.333333 2.373737
    ##  [36] 2.414141 2.454545 2.494949 2.535354 2.575758 2.616162 2.656566
    ##  [43] 2.696970 2.737374 2.777778 2.818182 2.858586 2.898990 2.939394
    ##  [50] 2.979798 3.020202 3.060606 3.101010 3.141414 3.181818 3.222222
    ##  [57] 3.262626 3.303030 3.343434 3.383838 3.424242 3.464646 3.505051
    ##  [64] 3.545455 3.585859 3.626263 3.666667 3.707071 3.747475 3.787879
    ##  [71] 3.828283 3.868687 3.909091 3.949495 3.989899 4.030303 4.070707
    ##  [78] 4.111111 4.151515 4.191919 4.232323 4.272727 4.313131 4.353535
    ##  [85] 4.393939 4.434343 4.474747 4.515152 4.555556 4.595960 4.636364
    ##  [92] 4.676768 4.717172 4.757576 4.797980 4.838384 4.878788 4.919192
    ##  [99] 4.959596 5.000000

<br>

<br>

Operators
=========

Operators can be used to compare and select on numbers, characters (and sometimes factors)

| Operator | Description                   |
|:---------|:------------------------------|
| +        | Addition                      |
| -        | Substraction                  |
| \*       | Multiplication                |
| /        | Division                      |
| ^        | Exponentiation                |
| %%       | Modulus (7%%3 is 1)           |
| %/%      | Integer division (7%/%3 is 2) |

| Operator  | Description           |
|:----------|:----------------------|
| &lt;      | Less than             |
| &lt;=     | Equal to or less than |
| &gt;      | More than             |
| &gt;=     | Equal to or more than |
| ==        | Equal to              |
| %in%      | Is it in there?       |
| !=        | Not equal to          |
| !x        | Not x                 |
| x|y       | x OR y                |
| x&y       | x AND y               |
| isTRUE(x) | Is X TRUE?            |

``` r
#Examples
3 != 5
```

    ## [1] TRUE

``` r
5 != 5
```

    ## [1] FALSE

``` r
5 == 5
```

    ## [1] TRUE

``` r
#Why would you want that?
#Great for subsetting vectors but also objects!
a <- 1:10
a
```

    ##  [1]  1  2  3  4  5  6  7  8  9 10

``` r
a[a > 5]
```

    ## [1]  6  7  8  9 10

``` r
a[a <= 2]
```

    ## [1] 1 2

``` r
a[a==5]
```

    ## [1] 5

``` r
a %in% 5
```

    ##  [1] FALSE FALSE FALSE FALSE  TRUE FALSE FALSE FALSE FALSE FALSE

``` r
a[a %in% 2]
```

    ## [1] 2

``` r
a[a==3 | a==5]
```

    ## [1] 3 5

<br>

<br>

The main classes
================

-   Numeric and integers
-   Characters
-   Factors
-   Lists

``` r
#Numeric
num <- c(1,2,3)
#Class can be used to view the class
class(num)
```

    ## [1] "numeric"

``` r
#Character
characters <- c("A","B","C")
class(characters)
```

    ## [1] "character"

``` r
#Factor, same as character but with the levels in the data
factors <- factor(c("A","A","B","B","C"), levels=c("A","B","C"))
class(factors)
```

    ## [1] "factor"

``` r
# List 
list(GroupA = 1:3, GroupB = 2:5 , GroupC = 3:5)
```

    ## $GroupA
    ## [1] 1 2 3
    ## 
    ## $GroupB
    ## [1] 2 3 4 5
    ## 
    ## $GroupC
    ## [1] 3 4 5

Switching between classes
-------------------------

You can also convert one class to the other:

``` r
#From character to numeric
a <- c("1","2","3")
class(a)
```

    ## [1] "character"

``` r
head(a)
```

    ## [1] "1" "2" "3"

``` r
b <- as.numeric(a)
class(b)
```

    ## [1] "numeric"

``` r
head(b)
```

    ## [1] 1 2 3

``` r
#From numeric to character
c <- as.character(b)
class(c)
```

    ## [1] "character"

``` r
#From factor to numeric
af <- factor(c("5","6","7"))
# This is not right:
as.numeric(af)
```

    ## [1] 1 2 3

``` r
# But this is:
as.numeric(as.character(af))
```

    ## [1] 5 6 7

<br>

<br>

Objects
=======

Creating objects
----------------

-   Data frames

Advantages: can hold multiple classes, columns can be viewed easily Disadvantage: one cannot do analyses on the entire object

-   Matrices

Advantage: very quick and useful for matrix calculations. Disadvantage: less easy to modify (add columns, change class of data)

``` r
#Data.frame: can hold multiple classes
df <- data.frame(Group = c(1,2,3), Outcome = c(2,3,6))

#head can be used to view objects
head(df)
```

    ##   Group Outcome
    ## 1     1       2
    ## 2     2       3
    ## 3     3       6

``` r
#str will give the classes of the different columns
str(df)
```

    ## 'data.frame':    3 obs. of  2 variables:
    ##  $ Group  : num  1 2 3
    ##  $ Outcome: num  2 3 6

``` r
class(df)
```

    ## [1] "data.frame"

``` r
#Groups can called with the dollar sign (dataframe only)
df$Group
```

    ## [1] 1 2 3

``` r
#Matrix:
mtrx <- matrix(1:25, nrow=5)
head(mtrx)
```

    ##      [,1] [,2] [,3] [,4] [,5]
    ## [1,]    1    6   11   16   21
    ## [2,]    2    7   12   17   22
    ## [3,]    3    8   13   18   23
    ## [4,]    4    9   14   19   24
    ## [5,]    5   10   15   20   25

``` r
str(mtrx)
```

    ##  int [1:5, 1:5] 1 2 3 4 5 6 7 8 9 10 ...

``` r
class(mtrx)
```

    ## [1] "matrix"

``` r
#Calculate something at once
mtrx*mtrx
```

    ##      [,1] [,2] [,3] [,4] [,5]
    ## [1,]    1   36  121  256  441
    ## [2,]    4   49  144  289  484
    ## [3,]    9   64  169  324  529
    ## [4,]   16   81  196  361  576
    ## [5,]   25  100  225  400  625

Modifying objects
-----------------

``` r
#Adding rownames to files 
rownames(df) <- c("A","B","C")
#The file has already colnames
colnames(df)
```

    ## [1] "Group"   "Outcome"

``` r
#What doesn't work:
#rownames(mtrx) <- c("A","B","C")
#Why not?
## Learn to understand error codes (read them carefully)
## If you don't get the error, google it. There is ALWAYS someone before you who had the same question.
## This does work. Why?
rownames(mtrx) <- c("A","B","C","D","E")
```

Modifying objects part 2
------------------------

If the comma is on the right of the indices so \[1:2,\] then it is applied to the *rows*

If the comma is on the left of the indices so \[,1:2\] then it is applied on the *columns*

``` r
#Data.frame
df[1:2, ] #First two lines
```

    ##   Group Outcome
    ## A     1       2
    ## B     2       3

``` r
df[,1:2]
```

    ##   Group Outcome
    ## A     1       2
    ## B     2       3
    ## C     3       6

``` r
df[df$Group == 1,]
```

    ##   Group Outcome
    ## A     1       2

``` r
#Different (order has changed!)
df[2:1, ] 
```

    ##   Group Outcome
    ## B     2       3
    ## A     1       2

``` r
#You can also subset by rownames
df[c("A","B"),]
```

    ##   Group Outcome
    ## A     1       2
    ## B     2       3

``` r
#Or colnames
df[,c("Group","Outcome")]
```

    ##   Group Outcome
    ## A     1       2
    ## B     2       3
    ## C     3       6

``` r
#Subset using operators
df[df$Group ==1,]
```

    ##   Group Outcome
    ## A     1       2

``` r
df[df$Group >= 2,]
```

    ##   Group Outcome
    ## B     2       3
    ## C     3       6

``` r
df[df$Group != 1,]
```

    ##   Group Outcome
    ## B     2       3
    ## C     3       6

``` r
df[rownames(df) != "A",]
```

    ##   Group Outcome
    ## B     2       3
    ## C     3       6

``` r
#Add new columns
df$NewCol <- c(1,2,5)
head(df)
```

    ##   Group Outcome NewCol
    ## A     1       2      1
    ## B     2       3      2
    ## C     3       6      5

``` r
# Modifying a matrix:
mtrx[1:2,]
```

    ##   [,1] [,2] [,3] [,4] [,5]
    ## A    1    6   11   16   21
    ## B    2    7   12   17   22

``` r
mtrx[1:2] #Different!
```

    ## [1] 1 2

Switching classes
-----------------

``` r
#From matrix to dataframe
dfm <- as.data.frame(mtrx)

#From dataframe to matrix
dm <- as.matrix(dfm) #Will convert all columns to 1 class, likely character!
```

<br>

<br>

Loading and saving from R
=========================

Reading from files
------------------

R can read all types of files (with or without required packages), such as txt, csv, xlsx (package: xlsx), sav spss file (package: Hmisc)

``` r
# Setting a working directory (= tell R where to find files and where to save files.)
setwd("/Users/roderick/Documents/Onderwijs/IntroR/")

#Reading csv files (comma delimited)
IrisCSV <- read.table("Iris.csv", sep=",", header=T)

#Or we give the full path
IrisCSV <- read.table("/Users/roderick/Documents/Onderwijs/IntroR/Iris.csv", sep=",", header=T)

head(IrisCSV)
```

    ##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1          5.1         3.5          1.4         0.2  setosa
    ## 2          4.9         3.0          1.4         0.2  setosa
    ## 3          4.7         3.2          1.3         0.2  setosa
    ## 4          4.6         3.1          1.5         0.2  setosa
    ## 5          5.0         3.6          1.4         0.2  setosa
    ## 6          5.4         3.9          1.7         0.4  setosa

``` r
str(IrisCSV)
```

    ## 'data.frame':    150 obs. of  5 variables:
    ##  $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
    ##  $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
    ##  $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
    ##  $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
    ##  $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...

``` r
#Reading tab delimited 
IrisTXT <- read.table("Iris as text file.txt", sep="\t", header=T)
head(IrisTXT)
```

    ##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1          5.1         3.5          1.4         0.2  setosa
    ## 2          4.9         3.0          1.4         0.2  setosa
    ## 3          4.7         3.2          1.3         0.2  setosa
    ## 4          4.6         3.1          1.5         0.2  setosa
    ## 5          5.0         3.6          1.4         0.2  setosa
    ## 6          5.4         3.9          1.7         0.4  setosa

``` r
str(IrisTXT)
```

    ## 'data.frame':    150 obs. of  5 variables:
    ##  $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
    ##  $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
    ##  $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
    ##  $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
    ##  $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...

``` r
#Reading XLSX. But: usally VERY slow and requires Java. 
library(xlsx)
```

    ## Loading required package: rJava

    ## Loading required package: xlsxjars

``` r
irisxlsx <- read.xlsx("Iris as xlsx file.xlsx", sheetIndex = 1)

str(irisxlsx)
```

    ## 'data.frame':    150 obs. of  5 variables:
    ##  $ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
    ##  $ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
    ##  $ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
    ##  $ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
    ##  $ Species     : Factor w/ 3 levels "setosa","versicolor",..: 1 1 1 1 1 1 1 1 1 1 ...

``` r
#To speed up, one can define colclasses.
#Note: system.time is a function to track the speed of functions
system.time(read.xlsx("Iris as xlsx file.xlsx", sheetIndex = 1))
```

    ##    user  system elapsed 
    ##   0.720   0.013   0.453

``` r
system.time(read.xlsx("Iris as xlsx file.xlsx", sheetIndex = 1, colClasses = c("numeric","numeric","numeric","numeric","character")))
```

    ##    user  system elapsed 
    ##   0.684   0.011   0.322

``` r
#SPSS
library(Hmisc)
```

    ## Loading required package: lattice

    ## Loading required package: survival

    ## Loading required package: Formula

    ## Loading required package: ggplot2

    ## 
    ## Attaching package: 'Hmisc'

    ## The following objects are masked from 'package:base':
    ## 
    ##     format.pval, round.POSIXt, trunc.POSIXt, units

``` r
lldata <- spss.get("LifeLines.sav")
head(lldata)
```

    ##   entity.id GESLACHT  GEWICHT   LENGTE HEALTH17A1
    ## 1     32674    Woman 73.39930 166.0011        Yes
    ## 2     79597      Man 65.46211 181.1047         No
    ## 3     17027    Woman 71.53435 187.1154         No
    ## 4     79747    Woman 61.82766 180.7776         No
    ## 5     88613    Woman 83.54524 167.8344         No
    ## 6     90622      Man 73.20778 189.0722         No
    ##                                     HEALTH17B1
    ## 1 Type 2 (adult-onset diabetes, later in life)
    ## 2 Type 2 (adult-onset diabetes, later in life)
    ## 3 Type 2 (adult-onset diabetes, later in life)
    ## 4 Type 2 (adult-onset diabetes, later in life)
    ## 5 Type 2 (adult-onset diabetes, later in life)
    ## 6 Type 2 (adult-onset diabetes, later in life)
    ##                               HEALTH17D1 DBPa SMK11 SMK31 SMK4A1 SMK4A21
    ## 1 I am not treated for diabetes mellitus   90    No    No      3      No
    ## 2 I am not treated for diabetes mellitus   78   Yes   Yes      0      No
    ## 3 I am not treated for diabetes mellitus   79    No   Yes      2      No
    ## 4 I am not treated for diabetes mellitus   60    No    No      5      No
    ## 5 I am not treated for diabetes mellitus   81    No    No      0      No
    ## 6 I am not treated for diabetes mellitus   95   Yes    No      0      No
    ##          Date
    ## 1 13702608000
    ## 2 13702694400
    ## 3 13702780800
    ## 4 13702867200
    ## 5 13702953600
    ## 6 13703040000

``` r
str(lldata)
```

    ## 'data.frame':    5024 obs. of  13 variables:
    ##  $ entity.id :Classes 'labelled', 'numeric'  atomic [1:5024] 32674 79597 17027 79747 88613 90622 110450 158803 145545 174641 ...
    ##   .. ..- attr(*, "label")= Named chr "Participant ID"
    ##   .. .. ..- attr(*, "names")= chr "entity_id"
    ##  $ GESLACHT  : Factor w/ 2 levels "Man","Woman": 2 1 2 2 2 1 1 1 2 1 ...
    ##   ..- attr(*, "label")= Named chr "Sex"
    ##   .. ..- attr(*, "names")= chr "GESLACHT"
    ##  $ GEWICHT   :Classes 'labelled', 'numeric'  atomic [1:5024] 73.4 65.5 71.5 61.8 83.5 ...
    ##   .. ..- attr(*, "label")= Named chr "Weight in kg"
    ##   .. .. ..- attr(*, "names")= chr "GEWICHT"
    ##  $ LENGTE    :Classes 'labelled', 'numeric'  atomic [1:5024] 166 181 187 181 168 ...
    ##   .. ..- attr(*, "label")= Named chr "Height in cm"
    ##   .. .. ..- attr(*, "names")= chr "LENGTE"
    ##  $ HEALTH17A1: Factor w/ 2 levels "Yes","No": 1 2 2 2 2 2 2 2 2 2 ...
    ##   ..- attr(*, "label")= Named chr "Do you have diabetes mellitus (diabetes)?"
    ##   .. ..- attr(*, "names")= chr "HEALTH17A1"
    ##  $ HEALTH17B1: Factor w/ 4 levels "Type 1 (juvenile diabetes, since childhood)",..: 2 2 2 2 2 2 2 2 2 2 ...
    ##   ..- attr(*, "label")= Named chr "What type of diabetes do you have?"
    ##   .. ..- attr(*, "names")= chr "HEALTH17B1"
    ##  $ HEALTH17D1: Factor w/ 5 levels "I am not treated for diabetes mellitus",..: 1 1 1 1 1 1 1 1 1 1 ...
    ##   ..- attr(*, "label")= Named chr "How are you treated?"
    ##   .. ..- attr(*, "names")= chr "HEALTH17D1"
    ##  $ DBPa      :Classes 'labelled', 'numeric'  atomic [1:5024] 90 78 79 60 81 95 83 71 101 101 ...
    ##   .. ..- attr(*, "label")= Named chr "Diastolic Blood Pressure in mm Hg"
    ##   .. .. ..- attr(*, "names")= chr "DBPa"
    ##  $ SMK11     : Factor w/ 2 levels "Yes","No": 2 1 2 2 2 1 1 1 2 2 ...
    ##   ..- attr(*, "label")= Named chr "Have you ever smoked for a full year? "
    ##   .. ..- attr(*, "names")= chr "SMK11"
    ##  $ SMK31     : Factor w/ 2 levels "Yes","No": 2 1 1 2 2 2 2 2 2 2 ...
    ##   ..- attr(*, "label")= Named chr "Do you smoke now, or have you smoked in the past month?"
    ##   .. ..- attr(*, "names")= chr "SMK31"
    ##  $ SMK4A1    :Classes 'labelled', 'numeric'  atomic [1:5024] 3 0 2 5 0 0 0 3 6 0 ...
    ##   .. ..- attr(*, "label")= Named chr "number of cigarettes / roll-ups per day"
    ##   .. .. ..- attr(*, "names")= chr "SMK4A1"
    ##  $ SMK4A21   : Factor w/ 3 levels "Yes","Yes, but less than 1 per day",..: 3 3 3 3 3 3 3 3 1 3 ...
    ##   ..- attr(*, "label")= Named chr "Do you smoke cigarettes / roll-ups?"
    ##   .. ..- attr(*, "names")= chr "SMK4A21"
    ##  $ Date      : num  1.37e+10 1.37e+10 1.37e+10 1.37e+10 1.37e+10 ...
    ##  - attr(*, "codepage")= int 65001

``` r
#Dates are transformed! So one needs to tell the function that there are dates present
lldataNew <- spss.get("LifeLines.sav", datevars = "Date")
head(lldataNew)
```

    ##   entity.id GESLACHT  GEWICHT   LENGTE HEALTH17A1
    ## 1     32674    Woman 73.39930 166.0011        Yes
    ## 2     79597      Man 65.46211 181.1047         No
    ## 3     17027    Woman 71.53435 187.1154         No
    ## 4     79747    Woman 61.82766 180.7776         No
    ## 5     88613    Woman 83.54524 167.8344         No
    ## 6     90622      Man 73.20778 189.0722         No
    ##                                     HEALTH17B1
    ## 1 Type 2 (adult-onset diabetes, later in life)
    ## 2 Type 2 (adult-onset diabetes, later in life)
    ## 3 Type 2 (adult-onset diabetes, later in life)
    ## 4 Type 2 (adult-onset diabetes, later in life)
    ## 5 Type 2 (adult-onset diabetes, later in life)
    ## 6 Type 2 (adult-onset diabetes, later in life)
    ##                               HEALTH17D1 DBPa SMK11 SMK31 SMK4A1 SMK4A21
    ## 1 I am not treated for diabetes mellitus   90    No    No      3      No
    ## 2 I am not treated for diabetes mellitus   78   Yes   Yes      0      No
    ## 3 I am not treated for diabetes mellitus   79    No   Yes      2      No
    ## 4 I am not treated for diabetes mellitus   60    No    No      5      No
    ## 5 I am not treated for diabetes mellitus   81    No    No      0      No
    ## 6 I am not treated for diabetes mellitus   95   Yes    No      0      No
    ##         Date
    ## 1 2017-01-01
    ## 2 2017-01-02
    ## 3 2017-01-03
    ## 4 2017-01-04
    ## 5 2017-01-05
    ## 6 2017-01-06

``` r
#Class?
class(lldataNew$Date)
```

    ## [1] "Date"

``` r
#This is a new class, namely dates! Can be used to calculate!
DiffDate <- lldataNew$Date - lldataNew$Date
head(DiffDate)
```

    ## Time differences in days
    ## [1] 0 0 0 0 0 0

Save to files
-------------

``` r
data(iris)

# Save objects in analysis
save(iris, file="Iris.RData")
# Load objects from previous sessions
load("Iris.RData")

#One can also save to common formats such as csv, txt
write.table(iris, file="Iris as text file.txt", sep="\t", col.names=T, row.names=F)
write.table(iris, file="Iris as csv file.csv", sep=";", col.names=T, row.names=F)
```

Describing data using descriptive statistics
============================================

``` r
#The iris dataset is a build in dataset

#Describe dataset
nrow(iris)
```

    ## [1] 150

``` r
ncol(iris)
```

    ## [1] 5

``` r
length(iris$Sepal.Length)
```

    ## [1] 150

``` r
sum(iris$Sepal.Length)
```

    ## [1] 876.5

``` r
mean(iris$Sepal.Length)
```

    ## [1] 5.843333

``` r
median(iris$Sepal.Length)
```

    ## [1] 5.8

``` r
sd(iris$Sepal.Length)
```

    ## [1] 0.8280661

``` r
# Summary statistics by group
# by(data = someVariable, INDICES = someGrouping, FUN = aGroupingFunction)

by(data = iris$Sepal.Length, INDICES = iris$Species, mean)
```

    ## iris$Species: setosa
    ## [1] 5.006
    ## -------------------------------------------------------- 
    ## iris$Species: versicolor
    ## [1] 5.936
    ## -------------------------------------------------------- 
    ## iris$Species: virginica
    ## [1] 6.588

``` r
# Same as:
by(iris$Sepal.Length, iris$Species, mean)
```

    ## iris$Species: setosa
    ## [1] 5.006
    ## -------------------------------------------------------- 
    ## iris$Species: versicolor
    ## [1] 5.936
    ## -------------------------------------------------------- 
    ## iris$Species: virginica
    ## [1] 6.588

``` r
#Store in variable
meanGroup <- by(data = iris$Sepal.Length, INDICES = iris$Species, FUN = mean)
SDGroup <- by(data = iris$Sepal.Length, INDICES = iris$Species, FUN = sd)
LengthGroup <- by(data = iris$Sepal.Length, INDICES = iris$Species, FUN = length)

class(meanGroup)
```

    ## [1] "by"

``` r
#Small trick:
as.list(meanGroup)
```

    ## $setosa
    ## [1] 5.006
    ## 
    ## $versicolor
    ## [1] 5.936
    ## 
    ## $virginica
    ## [1] 6.588

``` r
statistics <- cbind( as.list(meanGroup),as.list(SDGroup), as.list(LengthGroup))
colnames(statistics) <- c("Mean","SD","n")
statistics
```

    ##            Mean  SD        n 
    ## setosa     5.006 0.3524897 50
    ## versicolor 5.936 0.5161711 50
    ## virginica  6.588 0.6358796 50

<br>

<br>

Packages
========

Packages are an infinite rich source to facilitate your analysis

*To install packages from CRAN*

`install.packages("ggplot2")`

*Or when from Bioconductor:*

`source("https://bioconductor.org/biocLite.R")`

`biocLite("IRanges")`

<br>

<br>

Plotting
========

R base (without packages) can plot all kind of plots but are not very nice.

ggplot2 is a very commonly used package for plotting. Although the approach is a bit different, the plots are nicer and more flexible to change. For more help see: <http://ggplot2.tidyverse.org/reference/> or google!

``` r
library(ggplot2)

#Scatter plot
plot(iris$Sepal.Length, iris$Sepal.Width, xlab="Sepal length", ylab="Sepal width")
```

![](README_files/figure-markdown_github-ascii_identifiers/plotting-1.png)

``` r
ggplot(iris, aes(x=Sepal.Length, y=Sepal.Width, col=Species))+ # Define variables
  geom_point()+ # We want to plot dots
  ggtitle("Some title")+ #Add title to graph
  xlab("Sepal length")+ #Add x-axis labels
  ylab("Sepal width")+ #Add y-axis labels
  scale_color_manual(values = c("#009AC7","#132B41","#8B1A4F"))
```

![](README_files/figure-markdown_github-ascii_identifiers/plotting-2.png)

``` r
# Boxplot
boxplot(iris$Sepal.Length~iris$Species, xlab="Sepal length", ylab="Sepal width")
```

![](README_files/figure-markdown_github-ascii_identifiers/plotting-3.png)

``` r
ggplot(iris, aes(x=Species, y=Sepal.Length, fill=Species))+ #Define variables
  geom_boxplot()+ #What kind of graph?
  ggtitle("Some title")+ #Add title to graph
  xlab("Sepal length")+ #Add x-axis labels
  ylab("Sepal width")+ #Add y-axis labels
  scale_fill_manual(values = c("#009AC7","#132B41","#8B1A4F")) # Change colors using HEX colors
```

![](README_files/figure-markdown_github-ascii_identifiers/plotting-4.png)

``` r
# Jitter plot
ggplot(iris, aes(x=Species, y=Sepal.Length, col=Species))+ #Define variables
  geom_jitter(width=0.2)+
  ggtitle("Some title")+ 
  xlab("Sepal length")+ 
  ylab("Sepal width")+ 
  scale_colour_manual(values = c("#009AC7","#132B41","#8B1A4F")) 
```

![](README_files/figure-markdown_github-ascii_identifiers/plotting-5.png)

``` r
# Smoothed line graph
ggplot(iris, aes(x=Sepal.Width, y=Sepal.Length, col=Species))+
  geom_point()+
  geom_smooth(method=lm)+
  ggtitle("Some title")+
  xlab("Sepal length")+
  ylab("Sepal width")+
  scale_color_manual(values = c("#009AC7","#132B41","#8B1A4F"))
```

![](README_files/figure-markdown_github-ascii_identifiers/plotting-6.png)

``` r
ggplot(iris, aes(x=Sepal.Width, y=Sepal.Length, col=Species))+
  geom_point()+
  geom_smooth(method=loess)+
  ggtitle("Some title")+
  xlab("Sepal length")+
  ylab("Sepal width")+
  scale_color_manual(values = c("#009AC7","#132B41","#8B1A4F"))
```

![](README_files/figure-markdown_github-ascii_identifiers/plotting-7.png)

``` r
#One can also different types of plots on top of each other
ggplot(iris, aes(x=Species, y=Sepal.Length, fill=Species))+ #Define variables
  geom_boxplot()+ #What kind of graph?
  geom_jitter(width=0.2)+
  ggtitle("Some title")+ #Add title to graph
  xlab("Sepal length")+ #Add x-axis labels
  ylab("Sepal width")+ #Add y-axis labels
  scale_fill_manual(values = c("#009AC7","#132B41","#8B1A4F")) # Change colors using HEX colors
```

![](README_files/figure-markdown_github-ascii_identifiers/ontop-1.png)

Saving plots
------------

``` r
library(ggplot2)

pdf("Boxplot of iris data.pdf")
ggplot(iris, aes(x=Species, y=Sepal.Length, fill=Species))+ #Define variables
  geom_boxplot()+ #What kind of graph?
  ggtitle("Some title")+ #Add title to graph
  xlab("Sepal length")+ #Add x-axis labels
  ylab("Sepal width")+ #Add y-axis labels
  scale_fill_manual(values = c("#009AC7","#132B41","#8B1A4F")) # Change colors using HEX colors
dev.off()
```

    ## quartz_off_screen 
    ##                 2

``` r
jpeg("Boxplot of iris data.jpg", width = 10, height = 10, units="cm", res=200)
ggplot(iris, aes(x=Species, y=Sepal.Length, fill=Species))+ #Define variables
  geom_boxplot()+ #What kind of graph?
  ggtitle("Some title")+ #Add title to graph
  xlab("Sepal length")+ #Add x-axis labels
  ylab("Sepal width")+ #Add y-axis labels
  scale_fill_manual(values = c("#009AC7","#132B41","#8B1A4F")) # Change colors using HEX colors
dev.off()
```

    ## quartz_off_screen 
    ##                 2

Correlation tests in R
======================

``` r
# We use iris data
data(iris)

#Pearson correlation 
cor.test(iris$Sepal.Length, iris$Petal.Length)
```

    ## 
    ##  Pearson's product-moment correlation
    ## 
    ## data:  iris$Sepal.Length and iris$Petal.Length
    ## t = 21.646, df = 148, p-value < 2.2e-16
    ## alternative hypothesis: true correlation is not equal to 0
    ## 95 percent confidence interval:
    ##  0.8270363 0.9055080
    ## sample estimates:
    ##       cor 
    ## 0.8717538

``` r
#Or all pairwise at once
cor(iris[,1:4])
```

    ##              Sepal.Length Sepal.Width Petal.Length Petal.Width
    ## Sepal.Length    1.0000000  -0.1175698    0.8717538   0.8179411
    ## Sepal.Width    -0.1175698   1.0000000   -0.4284401  -0.3661259
    ## Petal.Length    0.8717538  -0.4284401    1.0000000   0.9628654
    ## Petal.Width     0.8179411  -0.3661259    0.9628654   1.0000000

``` r
#Spearman 
cor.test(iris$Sepal.Length, iris$Petal.Length, method = "spearman")
```

    ## Warning in cor.test.default(iris$Sepal.Length, iris$Petal.Length, method =
    ## "spearman"): Cannot compute exact p-value with ties

    ## 
    ##  Spearman's rank correlation rho
    ## 
    ## data:  iris$Sepal.Length and iris$Petal.Length
    ## S = 66429, p-value < 2.2e-16
    ## alternative hypothesis: true rho is not equal to 0
    ## sample estimates:
    ##       rho 
    ## 0.8818981

``` r
cor(iris[,1:4], method = "spearman")
```

    ##              Sepal.Length Sepal.Width Petal.Length Petal.Width
    ## Sepal.Length    1.0000000  -0.1667777    0.8818981   0.8342888
    ## Sepal.Width    -0.1667777   1.0000000   -0.3096351  -0.2890317
    ## Petal.Length    0.8818981  -0.3096351    1.0000000   0.9376668
    ## Petal.Width     0.8342888  -0.2890317    0.9376668   1.0000000

<br>

Simple statistical models in R
==============================

t.test: `t.test()` lm: `lm()` anova: `anova()`

``` r
data(iris)

#T.test vs average
t.test(iris$Sepal.Length, mu=6)
```

    ## 
    ##  One Sample t-test
    ## 
    ## data:  iris$Sepal.Length
    ## t = -2.3172, df = 149, p-value = 0.02186
    ## alternative hypothesis: true mean is not equal to 6
    ## 95 percent confidence interval:
    ##  5.709732 5.976934
    ## sample estimates:
    ## mean of x 
    ##  5.843333

``` r
#Linear model
fit <- lm(Sepal.Length~Species, data=iris)
fit$coefficients
```

    ##       (Intercept) Speciesversicolor  Speciesvirginica 
    ##             5.006             0.930             1.582

``` r
#Anova
an <- anova(fit)
an$"Pr(>F)"[1]
```

    ## [1] 1.669669e-31

``` r
#Fit 1
fit1 <- lm(Sepal.Length~Sepal.Width, data=iris)
an1 <- anova(fit1)
an1$"Pr(>F)"[1]
```

    ## [1] 0.1518983

``` r
#Chi-square test
mt <- matrix(c(20,100,325,3000), ncol=2)
colnames(mt) <- c("Yes", "No")
rownames(mt) <- c("Brown", "Yellow")
chisq.test(mt)
```

    ## 
    ##  Pearson's Chi-squared test with Yates' continuity correction
    ## 
    ## data:  mt
    ## X-squared = 5.3644, df = 1, p-value = 0.02055

More advanced R: creating and running for-loops and functions
=============================================================

A function can replicate the same thing over and over for multiple columns to reduce the amount of work and reduce errors. We use the `EuStockMarkets` dataset

``` r
data("EuStockMarkets")

# We want the characteristics for each row 
getSummary <- function(col, Data)
{
  co <- colnames(Data)[col]
  me <- mean(Data[,col])
  sdv <- sd(Data[,col])
  #Now we create a dataset to give everything back
  out <- data.frame(Group = co, Mean = me, SD=sdv)
  out
}

getSummary(col = 1, Data=EuStockMarkets)
```

    ##   Group     Mean       SD
    ## 1   DAX 2530.657 1084.793

``` r
#But now for all
dim(EuStockMarkets)
```

    ## [1] 1860    4

``` r
res <- lapply(1:4, getSummary, Data=EuStockMarkets)
newTable <- do.call(rbind, res)
newTable
```

    ##   Group     Mean        SD
    ## 1   DAX 2530.657 1084.7927
    ## 2   SMI 3376.224 1663.0265
    ## 3   CAC 2227.828  580.3142
    ## 4  FTSE 3565.643  976.7155

<br>

<br>

Other topics that could be covered
==================================

-   If/else statements
-   Writing functions
-   For-loops
-   Else?
