## Day 39 of #dailycoding challenge ⬇️

Today we are interested in #groupdata2.

groupdata2 is an R package that allows you Methods for dividing data into groups. Create balanced partitions and cross-validation folds. Perform time series windowing and general grouping and splitting of data. Balance existing groups with up- and downsampling.

Today we are interested in two functions of groupdata2

* group_factors() which returns a factor with group numbers and can be used to subset, aggregate, group_by, etc.

* group() which creates a grouping factor and adds it to the given data frame. The data frame is grouped by the grouping factor for easy use in magrittr (%>%) pipelines.

Finally we will calculate the mean of each group.

Happy Coding Learning !

``` r
# Loding packages 
library(groupdata2)
library(dplyr)       # %>% filter() arrange() summarize()
library(knitr)       # kable()

# Create small data frame
df_small <- data.frame(
  "x" = c(1:12),
  "species" = rep(c(
    'dog', 'tiger', 'elephant'
  ), 4),
  "age" = sample(c(1:70), 12),
  stringsAsFactors = FALSE
)

# Create grouping factor
group_factor(
  data = df_small, 
  n = 5, 
  method = "n_dist"
)

# Use group()
group(data = df_small, n = 5, method = 'n_dist') %>%
  kable()

# Use group() in a pipeline 
# Get average age per group
df_small %>%
  group(n = 5, method = 'n_dist') %>% 
  dplyr::summarise(mean_age = mean(age)) %>%
  kable()
```
