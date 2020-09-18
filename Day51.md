## Day 51 of #dailycoding challenge ⬇️

Today we will talk about  **R operators**.

R has many operators to carry out different mathematical and logical operations.
Operators in R can mainly be classified into the following categories:

#Arithmetic operators :These operators are used to carry out mathematical operations like addition and multiplication.

#Relational operators: These operators are used to compare between values.

#Logical operators: These operators are used to carry out Boolean operations like AND, OR etc.

Happy Coding Learning !

``` r
 #Arithmetic Operators
x <- 7
y <- 18
x + y
x * y
y / x 
y%/%x
y%%x
y^x
#Relational operators
x <- 7
y <- 18
x < y
y >= 20
x != 5
#On vectors:
x <- c(2,8,3)
y <- c(6,4,1)
x + y
x>y
#logical Operators 
x <- c(TRUE,FALSE,0,7)
y <- c(FALSE,TRUE,FALSE,TRUE)
!x
x&y
x|y

#It is possible to have multiple operators of same precedence in an expression.
#In such case the order of execution is determined through associativity.
#Precedence
2 + 6 * 5
(2 + 6) * 5
#Associativity
3 / 4 / 5
3 / (4 / 5)
 ```
