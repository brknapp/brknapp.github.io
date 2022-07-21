Fourth Blog Post
================

``` r
library(tree)
library(readr)
library(tidyverse)
```

    ## ── Attaching packages ───────────────────────────────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✔ ggplot2 3.3.6     ✔ dplyr   1.0.9
    ## ✔ tibble  3.1.7     ✔ stringr 1.4.0
    ## ✔ tidyr   1.2.0     ✔ forcats 0.5.1
    ## ✔ purrr   0.3.4

    ## ── Conflicts ──────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(class)
```

    ## Warning: package 'class' was built under R version 4.2.1

``` r
library(caret)
```

    ## Warning: package 'caret' was built under R version 4.2.1

    ## Loading required package: lattice

    ## 
    ## Attaching package: 'caret'

    ## The following object is masked from 'package:purrr':
    ## 
    ##     lift

``` r
library(rpart)
library(rpart.plot)
```

    ## Warning: package 'rpart.plot' was built under R version 4.2.1

``` r
wine_data<-read.csv("C://Users//Bridget//OneDrive//R_Scripts//repos//brknapp.github.io//wine.data")

colnames(wine_data)<-c("category",
                       "Alcohol",
                       "Malic_acid",
                       "Ash",
                       "Alcalinity_of_ash",
                       "Magnesium",
                       "Total_phenols",
                       "Flavanoids",
                       "Nonflavanoid_phenols",
                       "Proanthocyanins",
                       "Color_intensity",
                       "Hue",
                       "OD280_OD315_of_diluted_wines",
                       "Proline") 
set.seed(dim(wine_data)[1])
train <- sample(1:nrow(wine_data), size = nrow(wine_data)*0.8)
test <- dplyr::setdiff(1:nrow(wine_data), train)
wine_dataTrain <- wine_data[train, ]
wine_dataTest <- wine_data[test, ]
treeFit <- tree(Alcohol ~ ., data = wine_dataTrain)
plot(treeFit); text(treeFit)
```

![](../images/4_32_7_21_2022-1.png)<!-- -->

``` r
cvTree <- cv.tree(treeFit); cvTree
```

    ## $size
    ##  [1] 11 10  9  8  7  5  4  3  2  1
    ## 
    ## $dev
    ##  [1] 62.58607 58.56485 58.56485 58.29328 57.66687 56.27490 52.47601 50.86769 67.63033 97.87939
    ## 
    ## $k
    ##  [1]      -Inf  1.024055  1.028840  1.129224  1.205961  1.537335  3.283298  5.305063 15.996943 43.790790
    ## 
    ## $method
    ## [1] "deviance"
    ## 
    ## attr(,"class")
    ## [1] "prune"         "tree.sequence"
