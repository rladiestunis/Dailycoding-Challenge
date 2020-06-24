## Day 35 of #dailycoding challenge ⬇️

Today we will continue with the use of Loops in the programming language #R.
https://github.com/rladiestunis/Dailycoding-Challenge/edit/master/Day27.md

Today, we will learn how  to create a while loop in R programming.
#### While Loop:
The While loop in R Programming is a control flow statement that allows code to be executed repeatedly based on a given Boolean condition. While loop in R starts with the expression, and if the expression is True,
then statements inside the while loop will be executed. If the specified expression is false, it won’t be
executed at least once. It means, R while loop may execute zero or more time.

Take a look at the examples below to understand more the use of While Loops ⬇️

Happy Coding Learning !

``` r

##Let's go through a very simple example to understand the concept of while loop.
 
ctr <- 1   #Create a variable with value 1

#Create the loop
while (ctr <= 6) {
  print(paste("counter is set to",ctr))
  ctr = ctr+1 #increment ctr
}

#In the above example, ctr is initially initialized to 1.

#Here, the test_expression is ctr <= 6 which evaluates to TRUE since 1 is less 
#than 6
#So, the body of the loop is entered and ctr is printed and incremented.

#In the next iteration, the value of ctr is 2 and the loop continues.

#This will continue until ctr takes the value 7. The condition 7 <= 6 will give
#FALSE and the while loop finally exits.

ctr

#7 is the first value of ctr for which the condition fails, so we can't increment
#ctr further


#Incrementing ctr is important as this will eventually meet the exit condition.
#Failing to do so will result into an infinite loop.



##infinite while loop

ctr <- 1
while (ctr <= 6) {
  print(paste("counter is set to",ctr))
}


#the line ctr is set to 1 will be printed indefinitely until we stop the session
#manually  because ctr does not get updated
#this means that the condition is always TRUE and R keeps re executing the code 
#in the while loop
#long story short, always make sure your while loop will end at some point


##break statement

#beaks out of the while loop
#we want to stop our while loop as soon as the ctr value is equal to 4
#break will end the loop abruptly.
ctr <- 1
while (ctr <= 6) {
  if (ctr == 4 ) {
    break
  }
  print(paste("counter is set to",ctr))
  ctr = ctr+1 #increment ctr
}


#the sentence is only printed 3 times 


##Next statement
#Let's skip one step when ctr=4:

ctr <- 1
while (ctr <= 6) {
  if (ctr == 4 ) {
    ctr = ctr+1
    next
  }
  print(paste("counter is set to",ctr))
  ctr = ctr+1 #increment ctr
}




##Nested while loops
i <- 1
while(i <= 2){  #first loop
  j <- 1
  while (j <= 2) {  #second loop
    print(c(i,j))
    j<- j+1
  }
  i<- i+1
}

#we started with the fist value of the first loop, then we execute the second loop
#entirely for the first value of the first loop, before moving on to the second value
#of the fist while loop
```
