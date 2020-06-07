## Day 20 of #dailycoding challenge ⬇️

Today we are interested in the relocate() function included in the dplyr package for data manipulation.

R users enjoy coding in dplyr better than in R base because #dplyr is full of powerful functions that offer solutions to the most common dataframe #wrangling problems.
A new version of dplyr was recently released.

 You may need to update your R version to R 4.0.0 in order to ensure that the update of dplyr 1.0.0 is installed.

Some new features were created in the new version and we would like to introduce to you the relocate() function which allows you to change the order of the columns in the dataset.

The output has the following properties :

▪ Rows are not affected.
▪ The same columns appear in the output, but usually in a different place.
▪ Data frame attributes are preserved.
▪ Groups are not affected.

Remember that to get the magrittr pipe %>%, you have just to press CTRL + SHIFT+ M .

Take a look at the examples below to understand more the use of the relocate() function ⬇️

Happy Coding Learning !

``` r
# We will use the covid19tunisia data frame
# install.packages("remotes")
# remotes::install_github("MounaBelaid/covid19tunisia")
library(covid19tunisia)
data <- refresh_covid19tunisia()
head(data)
library(dplyr)
data %>% relocate(location) # We note that the column is moved to the first position.

# By specifying the parameters .after or .before, it is possible to choose the new position of our variable.
data %>% relocate(location, .after = location_type)
data %>% relocate(value, .before = data_type)

# We can also also select variables based on their type and apply logical rules to this function. 
# For example : place the numeric type variables in the first positions.
data %>% relocate(where(is.numeric))
```
