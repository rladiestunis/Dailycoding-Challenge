## Day 4 of #dailycoding challenge ⬇️

Today, we will discuss some statistical functions in R. Most of these functions are part of the R base package. These functions take R vector as an input along with the arguments and give the result.

The functions we are discussing are mean, median and mode.

▪ ️Mean : It is calculated by taking the sum of the values and dividing with the number of values in a data series.

The function mean() is used to calculate this in R.
The basic syntax for calculating mean in R is :
mean(x, trim = 0, na.rm = FALSE, ...)
Following is the description of the parameters used :(x is the input vector, trim is used to drop some observations from both end of the sorted vector, na.rm is used to remove the missing values from the input vector,..)

▪ ️Median : The middle most value in a data series is called the median.

The median() function is used in R to calculate this value.
The basic syntax for calculating median in R is :
median(x, na.rm = FALSE)
Following is the description of the parameters used :(x is the input vector, na.rm is used to remove the missing values from the input vector)

▪ ️Mode : The mode is the value that has highest number of occurrences in a set of data. Unike mean and median, mode can have both numeric and character data.

R does not have a standard in-built function to calculate mode. So we create a user function to calculate mode of a data set in R. This function takes the vector as input and gives the mode value as output.

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
 # Create a vector. 
 x <- c(12,7,3,4.2,18,2,54,-21,8,-5)
 
 # Find Mean.
 result.mean <- mean(x)
 print(result.mean)

 # Create a vector.
 x <- c(12,7,3,4.2,18,2,54,-21,8,-5)
 
 # Find Mean.
 result.mean <-  mean(x,trim = 0.3)
 print(result.mean)

 # Create a vector. 
 x <- c(12,7,3,4.2,18,2,54,-21,8,-5,NA)
 
 # Find mean.
 result.mean <-  mean(x)
 print(result.mean)
 
 # Find mean dropping NA values.
 result.mean <-  mean(x,na.rm = TRUE)
 print(result.mean)

 # Find median.
 median(x, na.rm = FALSE)
 # Create the vector.
 x <- c(12,7,3,4.2,18,2,54,-21,8,-5)
 
 # Find the median.
 median.result <- median(x)
 print(median.result)
 
 # Create the function.
 getmode <- function(v) {
         uniqv <- unique(v)
         uniqv[which.max(tabulate(match(v, uniqv)))]
 }
 
 # Create the vector with numbers.
 v <- c(2,1,2,3,1,2,3,4,1,5,5,3,2,3)
 
 # Calculate the mode using the user function.
 result <- getmode(v)
 print(result)
 
 # Create the vector with characters.
 charv <- c("o","it","the","it","it")
 
 # Calculate the mode using the user function.
 result <- getmode(charv)
 print(result)

```
