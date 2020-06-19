## Day 30 of #dailycoding challenge ⬇️

Today we are interested in Text mining and how to create a wordcloud.

Using the #tm package, you can do many manipulations to your text in order to clean it and make a comprensive wordcloud. Then using the #wordcloud package to create the wordcloud.

▪️ tm_map() do all the necessary transformation to the text which are : *Transforming the caracters to lower *Removing numbers *Removing stopwords *Removing punctuation *Removing whitespace

▪️ word () to create the word cloud.

Check to code below and share with us your wordcloud in comment.

Happy Coding Learning !

``` r
#Loading Packages 
library("tm")
library("SnowballC")
library("wordcloud")
library("RColorBrewer")

#Loding the data set
filePath <- "C:/Users/TOSHIBA/Desktop/R-Ladies.txt"
text <- readLines(filePath)

#Loading the data as corpus
docs <- Corpus(VectorSource(text))

# Text Transformation
toSpace <- content_transformer(function (x , pattern ) gsub(pattern, " ", x))
docs <- tm_map(docs, toSpace, "/")
docs <- tm_map(docs, toSpace, "@")
docs <- tm_map(docs, toSpace, "\\|")

# Transforming content to lower 
docs <- tm_map(docs, content_transformer(tolower))
# Removing the numbers
docs <- tm_map(docs, removeNumbers)
# Removing stopwords
docs <- tm_map(docs, removeWords, stopwords("english"))
# Removing Punctuation
docs <- tm_map(docs, removePunctuation)

# Removing white space
docs <- tm_map(docs, stripWhitespace)

# Matrix of most frequent worlds 

dtm <- TermDocumentMatrix(docs)
m <- as.matrix(dtm)
v <- sort(rowSums(m),decreasing=TRUE)
d <- data.frame(word = names(v),freq=v)
head(d, 10)

# The wordcloud

set.seed(1234)
wordcloud(words = d$word, freq = d$freq, min.freq = 1,
          max.words=100, random.order=FALSE, rot.per=0.35, 
          colors=brewer.pal(8, "Dark2"))
```
