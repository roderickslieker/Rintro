Introduction to R
================

Where to get this page from:
----------------------------

Beginning simple
----------------

-   Originated from proprietary S programming language

-   Comes in many flavours, like GUI (hardly a user interface), Rstudio, Eclipse

-   Rstudio is very useful: <https://www.rstudio.com/products/RStudio/>

-   Sublime when only typing syntax (to link with servers): <https://www.sublimetext.com/>

-   Git to track your code: <https://git.lumc.nl>

-   Packages: for an (almost infinity) number of applications people have developed packages, for example Bioconductor: <http://bioconductor.org/>

-   Suggested literature:

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
#Or multiple values ot variables
b <- c(1,2,3) # c, concatenate
b
```

    ## [1] 1 2 3

String classes
--------------

-   Numeric
-   Characters
-   Factors

``` r
#Numeric
num <- c(1,2,3)
#Class can be used to view the classs
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
#Factor
factors <- factor(c("A","A","B","B","C"), levels=c("A","B","C"))
class(factors)
```

    ## [1] "factor"

Objects
-------

-   Data frames

Advantages: can hold multiple classes, columns can be viewed easily Disadvantage: one cannot do analyses on the entire object

-   Matrices

Advantage: very quick and useful for matrix calculations. Disadvantage: less easy to modify (add columns)

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

Modifying objects
-----------------

``` r
#Data.frame
df[1:2, ] #First two lines
```

    ##   Group Outcome
    ## 1     1       2
    ## 2     2       3

``` r
#Add column
df$NewCol <- c(1,2,5)
head(df)
```

    ##   Group Outcome NewCol
    ## 1     1       2      1
    ## 2     2       3      2
    ## 3     3       6      5

``` r
#Matrix:
mtrx[1:2,]
```

    ##      [,1] [,2] [,3] [,4] [,5]
    ## [1,]    1    6   11   16   21
    ## [2,]    2    7   12   17   22

``` r
mtrx[1:2] #Different!
```

    ## [1] 1 2

Reading from files
------------------

R can read all types of files (with or without required packages), such as txt, csv, xlsx (package: xlsx), sav spss file (package: Hmisc)

``` r
#read.table(" ")
```

Plotting: mult
==============
