## Day 37 of #dailycoding challenge ⬇️
on #day 25 we spoke about random forest and we worked with the library "random forest", today we are going to do the same thing, but with the library caret, this library will offer us the optimal number of trees and mtry (number of features) .

we will work with the dataset diamonds of the library ggplot2, you can find the description of this dataset in this link : https://ggplot2.tidyverse.org/reference/diamonds.html

Take a look at the code below ⬇️

Happy Coding Learning !

``` r
library(ggplot2)
print(head(diamonds))

#loading library "caret"
library(caret)
#Create a random forest model with the train command, choose the rf method for Random Forest
set.seed(123)
mod <- train(price ~ ., data = diamonds, method = "rf")
print(mod)
# number of trees, mtry, l’OOB and confusion matrix
print(mod$finalModel)

# Important variables
varImp(mod)
#plot of important variables
plot(varImp(mod), top = 20)

#Prédiction
data=diamonds[c(3000,35000,50760),-c(2)]
predicted=predict(mod,data)
refrences=diamonds$cut[c(3000,35000,50760)]
table(predicted,refrences)
 ```
