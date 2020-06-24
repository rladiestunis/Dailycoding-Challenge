## Day 34 of #dailycoding challenge ⬇️

Today we are interested in one of the most used R tests, it's R - Chi Square Test :
Chi-Square test is a statistical method to determine if two categorical variables have a significant correlation between them. Both those variables should be from same population and they should be categorical like − Yes/No, Male/Female, Red/Green etc.

🔹 Syntax:
The function used for performing chi-Square test is :
🔸chisq.test().
The basic syntax for creating a chi-square test in R is :
🔸chisq.test(data)
data is the data in form of a table containing the count value of the variables in the observation.

Take a look at the examples below to understand more ⬇️

Happy Coding Learning!

``` r
library("MASS")
print(str(Cars93))

# Load the library.
library("MASS")

# Create a data frame from the main data set.
car.data <- data.frame(Cars93$AirBags, Cars93$Type)

# Create a table with the needed variables.
car.data = table(Cars93$AirBags, Cars93$Type) 
print(car.data)

# Perform the Chi-Square test.
print(chisq.test(car.data))
```


