## Day 5 of #dailycoding challenge ⬇️

Today we are interested in #R functions that display the structure of an R object. When you particularly work with data, you are looking to understand what variables you have, how many records the data set contains, how many missing values, what's the variable structure, what are the variable relationships and more. We will show you a few simple commands to help you get a fast overview of the data set you are working with.

▪ Str() function : It will output the information on one line for each basic structure. It will help to get a quick look at the data and its structure.

▪ Summary() function : It will output each column and a few other attributes which are especially useful for numeric attributes. It always displays min, 1st quartile, median, mean, 3rd quartile and max values.

▪ Skim() function from the skimr package : It's a good addition to the summary function. It displays most of the numerical attributes from the summary() function, but it also displays missing values, more quantile information and an inline histogram for each variable. It reports each data types separately and handles dates, logicals, and a variety of other types. It also supports spark-bar and spark-line.

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
 # We will use the mtcars data frame and apply the str() function.
 head(mtcars)
 str(mtcars)
 
 # The obove output tells you how many observations were tracked in the data frame 
 # against the number of variables (mpg was one of the variables of data tracked for each 
 # observation) and shows the type of every variable (num).
 
 summary(mtcars)
 # The above output shows the corresponding statistical attributes to every variable.
 
 library(skimr) # load the package
 skim(mtcars)
 
 # We note that the skim() function provides a larger set of statistics than the R base
 # function summary(). It also draws histogram charts for numeric variables.

```
