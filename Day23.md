## Day 23 of #dailycoding challenge ⬇️

Today we will talk about #tibbles :

In fact, tibbles are a modern take on data frames. They keep the features that have stood the test of time, and drop the features that used to be convenient but are now frustrating (i.e. converting character vectors to factors).

There are three key differences between tibbles and data frames: printing, subsetting, and recycling rules.

Take a look at the examples below to understand more ⬇️

Happy Coding Learning!

``` r
library(tidyverse)
head(swiss) #Showing the first 5 rows of swiss data
as_tibble(swiss) #Transform a data drame to tibble
as_tibble(rownames_to_column(swiss)) #adding the rownames

#Printing
#Tibbles only print the first 10 rows and all the columns that fit on a screen. - Each column displays its data type.
tibble(
  a = lubridate::now() + runif(1e3) * 86400,
  b = lubridate::today() + runif(1e3) * 30,
  c = 1:1e3,
  d = runif(1e3),
  e = sample(letters, 1e3, replace = TRUE)
)
#Subsetting

df <- tibble(
  x = runif(5),
  y = rnorm(5)
)

df$x
df[["x"]]
df[[1]]
#we can do the same with piping or chaining
df %>% .$x
df %>% .[[1]]
df %>% .[["x"]]
 ```
