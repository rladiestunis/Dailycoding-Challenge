## Day 14 of #dailycoding challenge ⬇️

Today we are interested in the use of pipes %>%  in the programming language R.

It is not a base feature of the language R In fact, it can only be used after attaching a package that provides it, such as #magrittr.

Some notes about pipes :

▪ The pipe operator takes the left-hand
side (#LHS) of the pipe and uses it as the first argument of the function on the right-hand side (#RHS) of the pipe.

▪ The first pipe that appears was this one  %.% in dplyr package created by Hadley Wickham in 2013.

▪ On December 2013, Stefan Bache proposed an alternative of that pipe and included a different pipe operator as you might now know it : %>%

▪ In April 2014, the %.% operator got replaced with the one that you now know, %>% .

It takes the output of one statement and makes it the input of the next statement.

▪ R is a functional language. When you have complex code this makes your #R code hard to read and understand by containing lot of parenthesis. Using pipes make the code easier to read.

▪ You can use the pipe operator as an argument placeholder.

▪ When you work with the #dplyr package it's better to use pipe operator so you gain a more clear overview of the operations that are being performed on the data.

▪ Pipes are also used with the #plotly package for visualization.

▪ To get the magrittr pipe %>%, you have just to press CTRL + SHIFT + M .


Take a look at the examples below to understand more some use cases of %>% ⬇️

Happy Coding Learning !

``` r
years <- factor(2011:2020)

# nesting
as.numeric(as.character(years))

# piping
library(magrittr)
years %>% as.character %>% as.numeric  
1:10 %>% mean

# is equivalent to
mean(1:10)

# Initialize `x`
x <- c(0.109, 0.359, 0.63, 0.996, 0.515, 0.142, 0.017, 0.829, 0.907)
         
# Compute the logarithm of 'x', return suitably lagged and iterated differences, 
# compute the exponential function and round the result
round(exp(diff(log(x))), 1)

# Perform the same computations on 'x' as above
log(x) %>% diff() %>%
           exp() %>%
           round(1)
         
         
# Use of the pipe operator as an argument placeholder :
"Ceci  n'est pas une pipe" %>% gsub("une", "un", .) 
5  %>% round(pi, digits=.)

