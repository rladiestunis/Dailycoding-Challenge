## Day 48 of #dailycoding challenge ⬇️

Today we are interested in #Mice Package: Multivariate Imputation by Chained Equations.

The #mice package implements a method to deal with missing data. The package creates multiple imputations (replacement values) for multivariate missing data. The method is based on Fully Conditional Specification, where each incomplete variable is imputed by a separate model. The MICE algorithm can impute mixes of continuous, binary, unordered categorical and ordered categorical data.
Mice function arguments:

  data : A data frame or a matrix containing the incomplete data. Missing values are coded as NA

  m : Number of imputation

  Maxit : Number of iterations

  Method : Can be either a single string, or a vector of strings with length length(blocks), specifying the imputation method to be used for each column in data. If specified as a single string, the same method will be used for all blocks. The methods that can be used are :

  PMM (Predictive Mean Matching): suitable for numeric variables

  logreg(Logistic Regression): suitable for categorical variables with 2 levels 

  polyreg(Bayesian polytomous regression): suitable for categorical variables with more than or equal to two levels 

  Proportional odds model: suitable for ordered categorical variables with more than or equal to two levels 

   predictorMatrix: A numeric matrix of length(blocks) rows and ncol(data) columns, containing 0/1 data specifying the set of predictors to be used for each target column.

Happy Coding Learning !

``` r
library(mice)
library(missForest)
library(VIM)
data <- iris
head(iris)
#Add randomly  missing values in 10% of the data: prodNA package from the package missForest
iris.mis <- prodNA(iris, noNA = 0.1)
head(iris.mis)
## Missing data patterns: 
md.pattern(iris.mis)
## Number of NAs for each variable using sapply
sapply(iris.mis, function(x) sum(is.na(x)))
## Use the aggr function from the VIM package to visualize missing data
miss_plot <- aggr(iris.mis,
                  numbers=TRUE, sortVars=TRUE,
                  labels=names(iris.mis), cex.axis=.7,
                  gap=3, prop=T,ylab=c("Proportion of missing data","Combinations"))
imputed_Data <- mice(iris.mis, m=5, maxit = 50, method = 'pmm', seed = 500)
summary(imputed_Data)
 ```
