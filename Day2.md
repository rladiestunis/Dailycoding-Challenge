## Day 2 of #dailycoding challenge ⬇️

We introduce the challenge by having a look at some useful fonctions in #R.

Today, we will have some insights about vectors in R A vector is the simplest type of data structure in R. Simply put, a vector is a sequence of data elements of the same basic type. Members of a vector are called Components.

▪️ Vectors are generally created using the c() function. And a vector can contain numeric values, logical values, text or date ...

▪️ The number of members in a vector is given by the function length().

▪️ The c() function is used to combine vectors with more than one value. The c() function maintains the order of the members.

▪️ You can combine a vector with itself if you want to repeat it, but if you want to repeat the values in a vector many times, using the c() function becomes a bit impractical. R makes life easier by offering you a function for repeating a vector: rep()

▪️ You can also modify a vector using the assignment operator.

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
 # Today, we will have some insights about vectors in R A vector is the simplest type of data structure in R. Simply put, a vector is a sequence of data elements of the same basic type. Members of a vector are called Components.
 
 # ▪️ Vectors are generally created using the c() function. And a vector can contain numeric values, logical values, text or date ...
 
 # ▪️ The number of members in a vector is given by the function lenght().
 
 # ▪️ The c() function is used to combine vectors with more than one value. The c() function maintains the order of the members.
 
 # ▪️ You can combine a vector with itself if you want to repeat it, but if you want to repeat the values in a vector many times, using the c() function becomes a bit impractical. R makes life easier by offering you a function for repeating a vector: rep()
 
 # ▪️ You can also modify a vector using the assignment operator.
 
 # Here is a vector containing three numeric values 2, 3 and 5 :
 c(2, 3, 5) 
 
 # Here is a vector of logical values :
 c(TRUE, FALSE, TRUE, FALSE, FALSE)
 
 # A Vector which contains text values :
 c("aa", "bb", "cc", "dd", "ee")
 
 # The number of members in a vector is given by the length function :
 length(c("aa", "bb", "cc", "dd", "ee","ff","gg"))
 
 # The c() function combines vectors with more than one value, as in the following example:
 
 fruits <- c("Apple", "Lemon", "Kiwi")
 vegetables <- c("potatoes", "spinach", "tomatoes")
 all_basket_items <- c(fruits, vegetables)
 all_basket_items
 
 # To repeat the vector c(0, 0, 7) three times, use this code:
 rep(c(1,2,3), times = 4)
 
 # To repeat every value by specifying the argument each, like this:
 rep(c(2, 4, 2), each = 3)
 
 # This code replaces the second element of the vector with "Strawberries"
 fruits[2] <- "strawberries"
 fruits

```
