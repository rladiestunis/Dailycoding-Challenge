## Day 3 of #dailycoding challenge ⬇️

Today, we will have some insights about two match functions in R: %in% and match.

▪ ️%in% operator in R, is used to identify if an element belongs to a given vector.

It is a logical vector which indicates whether a match was located for vector1 in vector2.

Syntax: vector1 %in% vector2.

▪ ️The match() function returns a vector of the position of first occurrence of the vector1 in vector2.

Syntax: match(vector1, vector2)
vector1: vector, the values to be matched
vector2: vector, the values to be matched against

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
 # %in% and match operators in R, are used to identify if an element belongs to a vector.
 # let's see it with a small example.
 # Here is a vector containing nine numeric values 1, 2, 3 , 4, 5, 6, 7 , 4, 5. Let's see if the value 5 is included this vector:
 5 %in% c(1, 2, 3, 4, 5, 6, 7,4 , 5)
 # Here is a vector containing nine numeric values 1, 2, 3, 4, 5, 6 ,7 ,4, 5. Let's see if the value 9 is included in this vector:
 9 %in% c(1, 2, 3, 4,5 ,6, 7, 4, 5)
 # The result value will be either TRUE or FALSE but never NA.
 # Here is a vector fruits containing different character values of fruits 
 fruits <- c("apple", "strawberry", "orange", "kiwi", "mango", "grapefruit", "mandarin", "lime")
 # Here is a vector vegetables containing different character values of vegetables:
 vegetables <- c("potatoes", "spinach", "tomatoes", "carrots", "garlic", "celeri", "lettuce")
 to_buy <- c("potatoes", "tomatoes", "garlic", "grapefruit" , "kiwi", "mango")
 # Is there elements from the vector fruits in the vector to_buy?
 fruits %in% to_buy
 
 #The match() function returns a vector of the position of first occurrence of the vector1 in vector2
 #If the element of the vector1 does not exist in vector2, NA is returned
 # Is there elements from the vector fruits in the vector to_buy?
 m <- match(fruits, to_buy)
 m
 # Here we show those elements
 to_buy_fruits <- fruits[m]
 to_buy_fruits
 # Is there elements from the vector vegetables in the vector to_buy?
 m1 <- match(vegetables, to_buy)
 m1
 # Here we show those elements
 to_buy_vegetables <- vegetables[m1]
 to_buy_vegetables
 

```
