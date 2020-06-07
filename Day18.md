## Day 18 of #dailycoding challenge ⬇️

Today we are interested in the Linear Regression in the programming language R.


Regression analysis is a very widely used statistical tool to establish a relationship model between 
two variables called predictor variable whose value is gathered through experiments.

The other called response variable whose value is derived from the predictor variable.

In Linear Regression these two variables are related through an equation, where exponent (power) of both these variables is 1.

Mathematically a linear relationship represents a straight line when plotted as a graph.

A non-linear relationship where the exponent of any variable is not equal to 1 creates a curve.

The general mathematical equation for a linear regression is :  y = ax + b

y is the response variable.

x is the predictor variable.

a and b are constants which are called the coefficients.

The steps to create the relationship is:

▪ Carry out the experiment of gathering a sample of observed values of height and corresponding weight.
▪ Create a relationship model using the lm() functions in R.
▪ Find the coefficients from the model created and create the mathematical equation using these
▪ Get a summary of the relationship model to know the average error in prediction. Also called residuals.
▪ To predict the weight of new persons, use the predict() function in R.

Take a look at the examples below to understand more the use of those functions⬇️

Happy Coding Learning !

``` r
x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131)
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)

# Apply the lm() function.
relation <- lm(y~x)


x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131)
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)

# Apply the lm() function.
relation <- lm(y~x)

print(summary(relation))

# The predictor vector.
x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131)

# The resposne vector.
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)

# Apply the lm() function.
relation <- lm(y~x)

# Find weight of a person with height 170.
a <- data.frame(x = 170)
result <-  predict(relation,a)
print(result)

# Create the predictor and response variable.
x <- c(151, 174, 138, 186, 128, 136, 179, 163, 152, 131)
y <- c(63, 81, 56, 91, 47, 57, 76, 72, 62, 48)
relation <- lm(y~x)

# Give the chart file a name.
png(file = "linearregression.png")

# Plot the chart.
plot(y,x,col = "blue",main = "Height & Weight Regression",
     abline(lm(x~y)),cex = 1.3,pch = 16,xlab = "Weight in Kg",ylab = "Height in cm")

# Save the file.
dev.off()
```
