## Day 6 of #dailycoding challenge ⬇️

Today we are interested in #R functions that are dealing with missing values. In R, missing values are often represented by NA. We will show you a few simple commands to help you work easily with it.

▪ is.na() function : It will test if your data contain missing values or not. it returns a logical vector with TRUE in the element locations that contain missing values represented by NA. You can use it on vectors, lists, matrices, and data frames.

▪ sum(is.na()) function : it will count the missing values in the dataframe. You can also use #colSums() to compute the total missing value in each column.

▪ na.rm = TRUE function : It will exclude missing values from mathematical operations.

▪ na.omit() function : it will omit all rows containing missing values.

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
 library(openair) # Load the package
 data("airquality") # Load the dataset
 head(airquality)
 
 # Identify the missing values in the data.To identify all the missing values, you just use is.na(airquality).
 is.na(head(airquality))
 
 # Identify location of NAs in the dataframe. It gives the position of the NAs in the dataframe. 
 which(is.na(airquality))
 
 # Identify count of NAs in data frame.We have 44 missing values in this dataframe.
 sum(is.na(airquality))
 
 # A convenient shortcut to compute the total missing values in each column is to use colSums().
 colSums(is.na(airquality))
 
 # Impute The missing values by mean and median
 airquality$Ozone[is.na(airquality$Ozone)] <- mean(airquality$Ozone, na.rm = TRUE) #Will replace the missing values in Ozone by the mean
 head(airquality)
 
 airquality$Solar.R[is.na(airquality$Solar.R)] <- median(airquality$Solar.R, na.rm = TRUE) #Will replace the missing values in Solar.R by the median
 head(airquality)
 
 # A shorthand alternative is to simply use na.omit() to omit all rows containing missing values.
 na.omit(head(airquality))

```
