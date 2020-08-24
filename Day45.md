## Day 45 of #dailycoding challenge ⬇️

Today we are interested on the #descritization of #quantitative variables.

Discretization is the operation that breaks up a series of quantitative data into classes (it is widely used for cartographic representations). The creation of classes strongly depends on the form of the distribution.

- Several existing methods, for example:

*Natural thresholds (Jenks, expensive in calculation)

*Average type and deviation

*Geometric progression (suitable for asymmetric distributions)

*Quantile method (often by default).

Today, we're going to work with #Quantile and #Jenks methods

Happy Coding Learning !

``` r
# Create a data frame
set.seed(1234)
data <- data.frame(
  sex=factor(rep(c("F", "M"), each=200)),
  weight=round(c(rnorm(200, mean=55, sd=5),
                 rnorm(200, mean=65, sd=5)))
)
head(data)
# Discretization with the quantile method
library(dplyr)
x=c(quantile(data$weight,na.rm = T))
x
tr_dens = cut (data$weight, breaks =c(quantile(data$weight,na.rm = T)),labels = c ("[0,54[", "[54,60[", "[60,66[", "[66,80["))
data = mutate (data,weight=tr_dens )
head(data)

# Discretization with Jenks method
library (cartography)
data$weight=as.numeric(data$weight)
seuils <- getBreaks (data$weight, nclass = NULL, method = "fisher-jenks")
tr_dens2 = cut (data$weight, breaks = seuils)
## in our example we didnt' choose the number of class so the function takes care of that 
data = mutate (data,weight=tr_dens2 )
head(data)
 ```
