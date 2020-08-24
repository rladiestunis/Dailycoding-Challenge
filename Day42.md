## Day 42 of #dailycoding challenge ⬇️

Today we will continue with the use of #Loops in the programming language #R https://lnkd.in/euDJ4ZJ

Today, we will learn how to create a repeat loop in#R programming.

repeat Loop:

A repeat loop is used to iterate over a block of code multiple number of times until a stop condition is encountered. . Repeat loop does not have any condition to terminate the loop,
We must ourselves place a condition explicitly within the loop’s body and use the break statement to exit the loop. Failing to do so will result into an infinite loop.


Break Statement:

The break keyword is a jump statement which is used to terminate the loop at a particular iteration.

Take a look at the examples below to understand more the use of repeat Loop, its Syntax and Execution Flow with Example R Scripts.⬇️

Happy Coding Learning !

``` r
#Let's get started with a simple example to demonstrate the use of repeat loop 
#Example 1: Using repeat loop to display numbers from 1 to 6

val <- 1

repeat{
  # statement to be executed multiple times 
  print(val) 
  # incrementing the iteration variable 
  val = val + 1
  
  # checking stop condition 
  if(val > 6){
    print("repeat loop ends");
    break# using break statement to terminate the loop 
  }
  
} 

#In the above program, the variable val is initialized to 1,
#then in each iteration of the repeat loop the value of val
#is displayed and then it is incremented until it becomes 
#greater than 6. If the value of val becomes greater than 6 
#then break statement is used to terminate the loop.

# infinite loop
#A repeat loop without a break statement results into an endless loop.

repeat {
  print("Press Esc to stop me!")  
}

#Example 2: Program to display a statement five times.

# initializing the iteration variable with 1
count <- 1

repeat {
  # statement to be executed multiple times 
  print("Hello World")
  
  #increment count by 1 each time the repeat block is executed
  count <- count+1 
  #checking the stop condition
  if (count > 5) {
    print("repeat loop ends");
    break
  }
}

#Here, initially the variable count is initialized with 1 
#then in each iteration of the repeat loop after printing
#Hello World the value of count is incremented till count
#becomes 6 and the condition in the if statement becomes 
#true then, the break statement is executed to terminate the 
#repeat loop.
 ```
