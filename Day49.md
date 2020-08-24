## Day 49 of #dailycoding challenge ⬇️

The starting point for analyzing data in R is having access to the data. This data must be stored in one or more R objects. To use R, you must first know the different types of objects that can serve as "data containers" and know how to work with these objects. so today we will be interested in #Different #types #of #R #objects #serving #as #data #structure.
Objects whose elements are constrained to be all data of the same type are called "atomic", while the others are called "recursive".
*** atomic objects

1 Vector: The vector is the simplest object, It has only one dimension.

2 Matrix: The matrix is ​​a 2-dimensional generalization of the vector.

3 Array: The last atomic object is the array, which generalizes the vector and the matrix to any number of dimensions.

*** recursive objects

1 List: A list is for a recursive object: it contains other objects, of any type.

2 Data.farme: The data frame is a particular type of list, but it also shares characteristics with matrices, being deemed to have 2 dimensions (rows and columns). Its elements are objects constrained to be of corresponding dimensions. In the vast majority of cases, the elements are vectors or factors of the same length, forming the columns of the data frame.

3 Factor: This type of object is used to store the observed values of a categorical variable.

Please take a look at the examples below to understand more ⬇️

``` r
#vector
vec=c(0,1,2,3,"cars","iris","orange","dora",0.1)
vec
str(vec)


#Matrix
mat=matrix(data=NA , nrow=3 ,ncol=3)
mat
str(mat)

#Array
my.array <- array(1:24, dim=c(3,4,2))
my.array
str(my.array)

#List
list=list(vec,my.array,mat)
list
str(list)


#Data frame
data <- data.frame("SN" = 1:3, "Age" = c(21,15,50), "Name" = c("John","Dora","liza"))
data
str(data)

#Factor
fruit=factor(c("banana","orange","strawberry","strawberry","banana"))
fruit
str(fruit)
```
