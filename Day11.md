## Day 11 of #dailycoding challenge ⬇️

Today we are interested in manipulating data with data.table.
The data.table extension allows you to extend the data tables. 
It radically changes the syntax of the hooks, allowing for a shorter and more powerful code.
In addition, it is particularly fast for performing data operations and allowing direct 
assignment operations to be performed without having to copy objects in memory. 
In other words, it is particularly useful when working on large data files.

We will learn :

▪ setDT and setDF functions

▪ How to select observations

▪ How to select variables

▪ How to group results

▪ How to add, modify and delete a variable

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
#Loading the package 
 library(data.table)
 
 #Converting iris data to data.table format 
 iris2 <- as.data.table(iris)
 class(iris2)
 
 #setDT converts a data array into data.table while setDF does the opposite.
 setDT(iris)
 class(iris)
 setDF(iris)
 class(iris)
 
 #The selection of an observation is done by indicating a condition to the first argument, i.e. i.
 iris2[Sepal.Length < 5]
 
 #To select a variable, just enter its name in the second part, i.e. j.
 iris2[, Sepal.Length]
 
 #To select several variables, a list set with list (not a vector defined with c) will be provided.
 iris2[, list(Sepal.Length, Sepal.Width)]
 
 #If in j we use functions that from a vector return a unique value (such as mean, median, min, max, first, last, nth, etc.), we can get a summary. We can also use . N to get the number of observations.
 iris2[, .(min_sepal_width = min(Sepal.Width), max_sepal_width = max(Sepal.Width), 
           n_observations = .N)]
 
 #data.table introduces a new operator: to modify a variable by direct assignment. This means that the change takes place directly in memory in the data table, without the need to reallocate the result with. You can also combine the i-observations with a selection of i-observations to change only certain observations. Similarly, the use of by allows calculations by group.
 iris2[, group := "A"]
 iris2[Species == "virginica", group := "B"]
 iris2[, n_obs_per_species := .N, by = Species]
 ```
