## Day 19 of #dailycoding challenge ⬇️

Today we are interested in the functions included in the #lubridate package.

Lubridate is an R package that makes it easier to work with dates and times.
It was created by Garrett Grolemund and Hadley Wickham, and is now maintained by Vitalie Spinu.

Take a look at the examples below to understand more the use of some functions of this package ⬇️

Happy Coding Learning !

``` r
### Install the package 
###install.packages("lubridate")
library(lubridate)

### Create a date
Date <- mdy(06052020) 
Date

### Some function to extract the year, the month and the day
year <- year(Date)
year
month <- month(Date)
month
day <- wday(Date,label=TRUE)
day

### Extraction of  the hour, minute and second from a datetime
Datetime<- ymd_hms("2020-06-05 18:35:25")
Datetime
hour <- hour(Datetime)
hour
minute<- minute(Datetime)
minute
second<- second(Datetime)
second

### check if the Date is a weekend
install.packages("chron")
library(chron)
is.weekend(Date)
```
