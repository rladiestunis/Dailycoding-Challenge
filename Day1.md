## Day 1 of #dailycoding challenge ⬇️

We introduce the challenge by having a look at some useful fonctions in #R.

Writing for, while loops is useful when programming but not particularly easy when working interactively on the command line. There are some functions which implement looping
to make life easier :

▪️ apply : It is the base function. It takes 3 arguments : (1) data matrix; (2) row/column operation (1 for row wise operation, 2 for column wise operation); (3) function to be applied on the data.

▪️ lapply : Loop over a list and evaluate a function on each element. lapply takes three arguments : (1) a list; (2) a function (or the name of a function) FUN; (3) other arguments.

▪️ sapply : it will try to simplify the result of lapply if possible. It is wrapper class to lapply with difference being it returns vector or mamtrix instead of list object.

▪️ tapply : It is used to apply a function over subsets of a vector.

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
options(digits = 2)
# Writing for, while loops is useful when programming but not particularly easy when working interactively on the command line. There are some functions which implement looping
# to make life easier.

# apply function is the base function. It takes 3 arguments : (1) data matrix; (2) row/column operation (1 for row wise operation, 2 for column wise operation); (3) function to be applied
# on the data.

head(mtcars)
apply(mtcars, 2, mean)

# lapply : Loop over a list and evaluate a function on each element.
# lapply takes three arguments : (1) a list; (2) a function (or the name of a function)
# FUN; (3) other arguments. 
 x <- list(a = 1:10, b = 20:30)
 x
 lapply(x, mean)

 # sapply will try to simplify the result of lapply if possible. It is wrapper class to lapply with difference being it returns vector or mamtrix instead of list object.
 sapply(x, mean)
 
 # tapply() is used to apply a function over subsets of a vector. 
 x <- runif(20, min=45, max=80) # Simulate 10 random weights
 y <- gl(2, 10, labels = c("Male", "Female")) # Generate factors by specifying the pattern of their levels.
 tapply(x, y, mean) # We see that the average weight for males is 66 and the average weight for females is 64.

```
