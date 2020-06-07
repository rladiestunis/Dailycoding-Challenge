## Day 16 of #dailycoding challenge ⬇️

Today we are interested in the use of regular expressions in the programming language R.

A string is several characters put together, this can be words, sentences, or DNA code.
When working with strings, regular expressions are an extremely powerful tool to look for specific patterns in the strings.
Base R includes seven main functions that use regular expressions with different outcomes. These are grep(), grepl(), regexpr(), gregexpr(), sub(), and gsub().
Although they require mostly similar inputs, their returned values are quite different.

Most common functions are :

▪ grep():examines each element of a character vector and returns the indices where the pattern is matched. When setting #value=TRUE it will return the character element instead of its index.

▪ grepl(): returns a logical value instead of the index or the element.

▪ regexpr():seeks for a pattern in a text and returns an integer vector with two attributes (also vectors). 
     The main integer vector returned represents the position where the pattern was first matched in the text. 
     Its attribute “match.length” is also an integer vector representing the length of the match. 
     If the pattern is not matched, both of the main vector and the length attribute will have a value of -1.
     The second attribute (“useBytes”) is always a logical vector of length one. It represents whether matching is done byte-by-byte (TRUE) or character-by-character (FALSE), but you may disregard it for now.

▪ gregexpr(): does not return a single vector, but a list of vectors. Each of these vectors reflects an input content string as is the length of the number of matches within that content.
   
▪ The final two base regex functions are #sub() and #gsub(). they substitute a matched pattern by a specified replacement and then return all inputs.

Take a look at the examples below to understand more the use of those functions⬇️

Happy Coding Learning !

``` r
words <- c("statistics", "estate", "street", "stalin", "stubborn", "shoes")

#Identify match to a pattern
grep("st",words, value=FALSE)

#Extract match to a pattern
grep("st",words, value=TRUE)

#Identify match to a pattern
grepl("st", words)

#seek for a pattern in a text
regexpr("st", words)
gregexpr("st", words)

#substitute a matched pattern
sentences <- c("I hate statistics", "I like mathematics")

#sub()
sub("hate","like", sentences)

#gsub()
gsub("like", "hate", sentences)
```
