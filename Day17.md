## Day 17 of #dailycoding challenge ⬇️

Today we are interested in the functions included in the #stringr package for string manipulation.

◾str_sub() 
◾str_length() 
◾str_c() 
◾str_subset() 
◾str_count() 
◾str_locate() 
◾str_detect()
◾str_replace()

Take a look at the examples below to understand more the use of those functions ⬇️

Happy Coding Learning !

``` r
#uploading library
library(stringr) 

#a vector of strings
x <- c("R-Ladies", "promotes", "gender", "diversity", "in", "R","community") 

#Joins two or more vectors element-wise into a single character vector
str_c(x, collapse = " ") 

# returns the number of "code points" in a string
str_length(x) 

#Extract and replace substrings from a character vector
str_sub(x, 1, 2) 
#the regular expression "[aeiou]" matches any single character that is a vowel

#Keep strings matching a pattern, or find positions
str_subset(x, "[aeiou]") 

#Count the number of matches in a string
str_count(x, "[aeiou]") 

#tells you if there’s any match to the pattern
str_detect(x, "[aeiou]") 

#gives the position of the match
str_locate(x, "[aeiou]") 

#replaces the matches with new text
str_replace(x, "[aeiou]", "?") 
```
