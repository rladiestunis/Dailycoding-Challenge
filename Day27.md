## Day 27 of #dailycoding challenge ⬇️


Today we are interested in the use of Loops in the programming language #R.

What Are Loops?

"Looping", "cycling, "iterating" or just replicating instructions are used in programming to repeat a specific block of code/instructions.
Loops are also called Control structures.
To read more about control structures, this link may be very useful https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/Control.

Commonly used control structures :

▪ for Loop: execute a loop a fixed number of times
	
▪ while Loop: execute a loop while a condition is true

▪ repeat Loop: execute an infinite loop (must break out of it to stop)



Today, we will learn how  to create a for loop in R programming.
#### For Loop:
In R, for loops take an interator variable and assign it successive values from a sequence or vector. For loops are most commonly used for iterating over the elements of an object (list, vector, etc.)


Take a look at the examples below to understand more the use of For Loops ⬇️

Happy Coding Learning !

``` r
###LOOPING THROUGH A VECTOR


# Create a vector filled with numeric values
loopVec <- c(5,10,20,30,40)

#This loop prints the  elements of vector loopVec
for (i in loopVec) {
  ## Print out each element of 'loopVec'
  print(i)
}

#In the above example, the loop iterates 5 times as the vector loopVec has 5 elements.

#The following three loops all have the same behavior.

#For one line loops, the curly braces are not strictly necessary
#But the curly braces definitely enhance the readability of your 
#code and allow to spot the loop block and potential errors within it easily.....
 for(i in loopVec) print(i)


# Generate a sequence based on length of 'loopVec'
for (j in 1:length(loopVec)) {
  print(loopVec[j])
}

#The seq_along() function is commonly used in conjunction with for loops in order
#to generate an integer sequence based on the length of an object
for (j in seq_along(loopVec)) {
  print(loopVec[j])
}


#This loop calculates the square of the elements of vector loopVec
for (i in loopVec) {
  ## Print out the square of each element of 'loopVec'
  print(i^2)
}


##create a vector to store the elements of the for loop

# Initialize 'storage'
storage <- numeric(5)

for(i in 1:length(loopVec)) {
  # i-th element of 'loopVec' squared into i-th position of 'storage'
  storage[i] <- loopVec[i]^2
  print(storage[i])
}

#Now we can easily use the results of the for loop 

mean(storage)
max(storage)

# Create a vector filled with letters

loop_letter_Vec <- c("a", "b", "c", "d")
 
 for(i in seq_along(loop_letter_Vec)) {
            ## Print out each element of 'loop_letter_Vec'
              print(loop_letter_Vec[i])  
     }



###LOOPING OVER LISTS

myList <- list(10,20,30,40,50)

for (i in myList) {
  ## Print out each element of 'myList'
  head(print(i))
}


###LOOPING OVER MATRIX

# Create a 4 x 10 matrix (of 4 rows and 10 columns)
myMatrix <- matrix(1:40, nrow = 4)
myMatrix


#This loop prints the sqaure of the 5 fisrt elements of 'myMatrix'
for (i in myMatrix[1:5]) {
  print(i^2)
}


###NESTED LOOPS

##for loops can be nested inside of each other.
##code and allow to spot the loop block and potential errors within it easily.....
##Nested loops are commonly needed for multidimensional or hierarchical data 
##structures (e.g. matrices, lists). 


for (row in 1:nrow(myMatrix)) {
  for (col in 1:ncol(myMatrix)) {
    print(paste('The value of Row =',row,'and Col=',col,'is',myMatrix[row,col]))
  }
  
}

#We have two nested for loops, each is governed by its own index.
#That is, row runs over the rows and col runs over the columns.
```
