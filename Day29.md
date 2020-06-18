## Day 29 of #dailycoding challenge ⬇️

Today we are interested in the #select() function for selecting variables that match a pattern.

Using the #tidyselect package, there are several selection functions that match variables according to a given pattern like the following :

🟪starts_with() : Starts with a prefix.
🟪ends_with() : Ends with a suffix.
🟪contains() : Contains a literal string.
🟪matches() : Matches a regular expression.
🟪num_range() : Matches a numerical range.
🟪one_of(vec_col) : Select columns whose names are presented in the vector vec_col, according to the order given in the vec-col.
🟪everything() : Select all columns or the columns that remain after applying select functions.

Since the new version of #tidyselect 1.1.0 has been released, new test #boolean functions for selection are introduced using the #where() function and that may be also combined with the previous functions. It's also possible to use the following operators for selecting a range of consecutive variables :

🟪! for taking the complement of a set of variables.
🟪& and | for selecting the intersection or the union of two sets of variables.
🟪c() for combining selections.

Remember that to get the magrittr pipe %>%, you just have to press ▪️CTRL + SHIFT+ M ▪️

Take a look at the examples below to understand more the use of the #select() function ⬇️

Happy Coding Learning !

#dailycoding #challenge #programming #rstats #R #rladies

``` r
# We will use the covid19tunisia data frame
# install.packages("remotes")
# remotes::install_github("MounaBelaid/covid19tunisia")
library(covid19tunisia)
covid19data <- refresh_covid19tunisia()
head(covid19data, 5)
library(dplyr)

head(covid19data %>% select(starts_with("location")), 5)

head(covid19data %>% select(ends_with(c("code","type"))), 5)

# The : operator selects a range of consecutive variables
head(covid19data %>% select(date:location_type), 5)
# The ! operator negates a selection
head(covid19data %>% select(!(date:location_type)), 5)
head(covid19data %>% select(!ends_with("type")), 5)

# Display all the columns whose names contain "location"
head(covid19data %>% select(contains("location")), 5)

# Using test boolean function
head(covid19data %>% select(where(is.character) & ends_with("type")), 5)
```
