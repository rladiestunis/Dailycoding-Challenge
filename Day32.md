## Day 32 of #dailycoding challenge ⬇️

Today we are interested in data manipulation with dplyr package :

The scoped variants of summarise() make it easy to apply the same transformation to multiple variables. There are three variants:

🔹 summarise_all(): affects all variables in the dataset

🔹 summarise_at(): affects variables selected with a character vector or vars()

🔹 summarise_if(): affects variables selected with a predicate function(a function that returns TRUE or FALSE)

🔹 mutate(): adds new columns at the end of your dataset

🔹 head(): a function to look at the first few rows

🔹 tail(): a function to look at the last few rows

Take a look at the examples below to understand more ⬇️

Happy Coding Learning !

``` r
#### Install packages
library(dplyr)
library(datasets)
head(iris)
str(iris)

###  summarise_at() affects variables selected with a character vector or vars()
### Calculate the mean for 2 variables: Sepal.Length and Sepal.Width

iris  %>% 
  summarise_at(vars("Sepal.Length", "Sepal.Width"), mean, na.rm = TRUE) 
### summarise_all() affects every variable
### For all variables, we calculate the min and the max for each species. The new variables includes the function name.
NewData1<- iris %>% group_by(Species)%>% summarise_all(list(min=min ,max=max)) 
NewData1 <- data.frame(NewData1)
NewData1

### summarise_if() affects variables selected with a predicate function(a function that returns TRUE or FALSE)
###  Here, we apply the mean to numeric column

NewData2<- iris %>% group_by(Species) %>%
  summarise_if(is.numeric, mean, na.rm = TRUE)
NewData2<- data.frame(NewData2)
NewData2

### mutate(): adds new columns at the end of your dataset
### head(): a function to look at the first few rows
### tail():  a function to look at the last few rows

## we create a 2 new colums and we look the first 6 rows

iris %>% mutate(NewVar1= Sepal.Length*Sepal.Width,
                NewVar2= Petal.Length*Petal.Width)%>%head() 
### we create a 2 new colums and we look the last 6 rows

iris %>% mutate(NewVar1= Sepal.Length*Sepal.Width,
                NewVar2= Petal.Length*Petal.Width)%>%tail()

### We can also make a boxplot 

iris %>% select(Sepal.Length, Petal.Length )%>% boxplot()
```
