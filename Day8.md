## Installation

Day 8 of #dailycoding challenge ⬇️

Today we are interested in #R functions that are dealing with merging two datasets.

Datascients are working always with more than one dataset. Like SQL, R also allows you to merge two datasets using different options.

▪ merge() : Return only the rows in which the left table have matching keys in the right table.

▪ all=TRUE : when you add all = TRUE to merge, you will have a dataframe with all rows from both tables, join records from the left which have matching keys in the right table.

▪ all.x=TRUE : Left outer join:To include all the rows of your data frame x and only those from y that match, specify x=TRUE.

▪ all.y=TRUE : Right outer join: To include all the rows of your data frame y and only those from x that match, specify y=TRUE.

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

``` r
 ## Creation of two dataframes 
 height <- data.frame("Character" = c("Luke", "Han", "Leia","Mark"),
                      "height" = c("1.75m", "1.85m", "1.5m","1.65m"))
 gender <- data.frame("Character" = c("Luke", "Han", "Leia","Jane","Ramsey"),
                      "gender" = c("m", "m", "f","f","m"))
 
 ## INNER JOIN : returns rows when there is a match in both tables.
 merge(x = height, y = gender, by = "Character")
 
 ## FULL (outer) JOIN: As you can see in the results it generates NA for gender to Mark as Mark doesn't exist in gender and NAs for Jane and Ramsey as they don't appear in height.
 merge(height,gender, all=TRUE)
 
 ## Left outer join in R: Return all rows from height, and all the rows with matching keys from gender. It puts NA for the gender of Mark as Mark doesn't appear in gender. 
 merge(x = height, y = gender, by = "Character",all.x=TRUE)
 
 ## Right outer join in R: Return all rows from gender, and any rows with matching keys from height.It generates NAs for the heights of Jane and Ramsey as they exist only in height.
 merge(x = height, y = gender, by = "Character",all.y=TRUE)

```
