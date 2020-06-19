## Day 31 of #dailycoding challenge ⬇️

Today we are interested in #tidygenomics which handles genomic data with the tidy-philosophy.
The main functions of this package are :

👉genome_intersect():Joins 2 data frames based on their genomic overlap.
👉genome_subtract(): Subtracts one data frame from the other.
👉genome_complement():Calculates the complement of a genomic region.

Take a look at the examples below to understand more each function ⬇️

Happy Coding Learning !

``` r
library(tidygenomics)
# Joins 2 data frames based on their genomic overlap
df1 <- data.frame(id = 1:2, 
                  chromosome = c("chr1", "chr4"),
                  start = c(100, 200),
                  end = c(150, 250))

df2 <- data.frame(id = 1:2,
                  chromosome = c("chr1", "chr4"),
                  start = c(120, 210),
                  end = c(160, 240))

genome_intersect(df1, df2, by=c("chromosome", "start", "end"), mode="both")
# Subtracts one data frame from the other
x1 <- data.frame(id = 1:2,
                 chromosome = c("chr9", "chr12"),
                 start = c(100, 200),
                 end = c(150, 250))

x2 <- data.frame(id = 1:2,
                 chromosome = c("chr9", "chr12"),
                 start = c(120, 210),
                 end = c(125, 240))

genome_subtract(df1, df2, by=c("chromosome", "start", "end"))
# calculates complement of a genomic region
df1 <- data.frame(id = 1:2,
                  chromosome = c("chr7", "chr6"),
                  start = c(6000000, 300),
                  end = c(13000000, 600))

genome_complement(df1, by=c("chromosome", "start", "end"))
 ```
