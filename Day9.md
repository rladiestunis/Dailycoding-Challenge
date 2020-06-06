## Day 9 of #dailycoding challenge ⬇️

Today we are interested in #R Matrices :

Matrices are the R objects in which the elements are arranged in a two-dimensional rectangular layout. They contain elements of the same atomic types. Though we can create a matrix containing only characters or only logical values, they are not of much use. We use matrices containing numeric elements to be used in mathematical calculations.

A Matrix is created using the matrix() function.

Syntax :
The basic syntax for creating a matrix in R is −

▪ matrix(data, nrow, ncol, byrow, dimnames)

- Following is the description of the parameters used :

▪ data is the input vector which becomes the data elements of the matrix.

▪ nrow is the number of rows to be created.

▪ ncol is the number of columns to be created.

▪ byrow is a logical clue. If TRUE then the input vector elements are arranged by row.

▪ dimnames are the names assigned to the rows and columns.

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
 # Elements are arranged sequentially by row
 M <- matrix(c(3:14), nrow = 4, byrow = TRUE)
 print(M)
 
 # Elements are arranged sequentially by column
 N <- matrix(c(3:14), nrow = 4, byrow = FALSE)
 print(N)

 
 # Define the column and row names
 rownames = c("row1", "row2", "row3", "row4")
 colnames = c("col1", "col2", "col3")
 P <- matrix(c(3:14), nrow = 4, byrow = TRUE, dimnames = list(rownames, colnames))
 print(P)
 
 
 # Define the column and row names
 rownames = c("row1", "row2", "row3", "row4")
 colnames = c("col1", "col2", "col3")
 
 # Create the matrix
 P <- matrix(c(3:14), nrow = 4, byrow = TRUE, dimnames = list(rownames, colnames))
 
 # Access the element at 3rd column and 1st row
 print(P[1,3])
 
 # Access the element at 2nd column and 4th row
 print(P[4,2])
 
 # Access only the  2nd row
 print(P[2,])
 
 # Access only the 3rd column
 print(P[,3])

 # Create two 2x3 matrices
 matrix1 <- matrix(c(3, 9, -1, 4, 2, 6), nrow = 2)
 print(matrix1)
 
 matrix2 <- matrix(c(5, 2, 0, 9, 3, 4), nrow = 2)
 print(matrix2)
 
 # Add the matrices
 result <- matrix1 + matrix2
 cat("Result of addition","\n")
 print(result)
 
 # Subtract the matrices
 result <- matrix1 - matrix2
 cat("Result of subtraction","\n")
 print(result)
 
 # Create two 2x3 matrices
 matrix1 <- matrix(c(3, 9, -1, 4, 2, 6), nrow = 2)
 print(matrix1)
 
 matrix2 <- matrix(c(5, 2, 0, 9, 3, 4), nrow = 2)
 print(matrix2)
 
 # Multiply the matrices
 result <- matrix1 * matrix2
 cat("Result of multiplication","\n")
 print(result)
 
 # Divide the matrices
 result <- matrix1 / matrix2
 cat("Result of division","\n")
 print(result)
```
