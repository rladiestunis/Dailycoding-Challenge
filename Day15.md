## Day 15 of #dailycoding challenge ⬇️

Today we are interested in the use of filter function in the programming language R.

We will show you how to filter the data in different ways using dplyr package created by Hadley Wickham in 2013.

Most common functions are :

▪ slice(): Extract rows by position.

▪ filter(): Extract rows that meet a certain logical criteria.

▪ filter_all(), filter_if() and filter_at(): filter rows within a selection of variables. 
  These functions replicate the logical criteria over all variables or a selection of variables.

▪ sample_n(): Randomly select n rows

▪ sample_frac(): Randomly select a fraction of rows

▪ top_n(): Select top n rows ordered by a variable

Take a look at the examples below to understand more the use of those functions.

Happy Coding Learning !

``` r
## Loading package 
library(dplyr)

## Converting the iris data into a tibble data frame (tbl_df) 
## for easier data analysis.

my_data <- as_tibble(iris)
my_data

## Extractiong row by position from row 1 to row 3
my_data %>% slice(1:3)

## Extracting rows where Sepal.Length > 7
my_data %>% filter(Sepal.Length > 7)

## Create a new demo data set from my_data by removing the grouping column "Species"
my_data2 <- my_data %>% select(-Species)

## Selecting rows where all variables are greater than 3.2.
my_data2 %>% filter_all(all_vars(.> 3.2))

## The following R code apply the filtering criteria 
## on the columns Sepal.Length and Sepal.Width
my_data2 %>% filter_at(vars(starts_with("Sepal")), any_vars(. > 2.4))

## We first use the function set.seed() to initiate random number generator engine.
set.seed(1234)

## Extract 3 random rows without replacement
my_data %>% sample_n(3, replace = FALSE)

# Extract 3% of rows, randomly without replacement
my_data %>% sample_frac(0.03, replace = FALSE)

## Select the top 5 rows ordered by Sepal.Length

my_data %>% top_n(5, Sepal.Length)
```
