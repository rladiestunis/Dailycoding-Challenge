## Day 10 of #dailycoding challenge ⬇️

Today we are interested in #reshaping data between #long and #wide forms.
In R, tabular data is stored in data frames. Through this post we will cover the various ways of transforming a single table.
In a wide format, each variable has its own column. However, sometimes it is more convenient to have a long format, in which all variables are in one column and the values are in a second column.

▪ Base R : stack() and unstack() functions.

▪ The tidyr package : the gather() and spread() functions.

▪ The data.table package : melt() and dcast() functions.

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
 # For each of the options, the mtcars dataset will be used. 
 # By default, this dataset is in a long format. In order for the packages to work, we will insert the row names as the first column.
 
 data <- data.frame(observation=row.names(mtcars),mtcars)
 head(data)
 
 # Base R
 long <- stack(data)
 head(long) # this shows the long format and we get two columns.
 # Let's see the values in the variable ind to understand more what happened.
levels(long$ind)
 wide <- unstack(long)
 head(wide) # this shows the wide format. We get back to the original data.
 
 # However, these functions can become very complex for more advanced use cases. Luckily, there are other options using third party packages : The tidyr package.
 
 library(tidyr)
 long <- gather(data, variable, value, 2:12) # where variable is the name of the variable column, value indicates the name of the value column and 2:12 refers to
 # the columns to be converted. 
 head(long) # shows the long result
 wide <- spread(long,variable,value)
 head(wide) # shows the wide result (~data)
 
 # The data.table package
 library(data.table)
 long <- melt(setDT(data),'observation',2:12,'variable', 'value')
 head(long) # shows the long result
 wide <- dcast(long, observation ~ variable)
 head(wide) # shows the wide result
```
