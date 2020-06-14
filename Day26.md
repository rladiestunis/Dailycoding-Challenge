## Day 26 of #dailycoding challenge ⬇️

Today we are interested in how to format ggplot date axis using #scale_x_date() and #scale_x_datetime() :

▪️ scale_x_date(date_labels, date_breaks): Format date axis

▪️ scale_x_datetime(date_labels, date_breaks): Format datetime axis

To format date/datetime axis labels, you can use different combinations of days, weeks, months ,years, …. :
• Weekday name: use %a and %A for abbreviated and full weekday name, respectively

• Month name: use %b and %B for abbreviated and full month name, respectively

• %d: day of the month as decimal number

• %Y: Year with century

• %H : Hours as decimal number (00--23)

• %M : Minute as decimal number (00--59)

• %S : Second as integer (00--61)

• See more options in the documentation of the function ?#strptime

Take a look at the examples below to understand more ⬇️

Happy Coding Learning!

``` r
### Install package
### install.packages("ggplot2")
library(ggplot2)

### Create time series data
set.seed(1234)
Date <- Sys.Date() - 0:59
Value<- runif(60)
Data <- data.frame(Date,Value)

head(Data)

### Create a simple plot with date axis
p <- ggplot(data=Data, aes(x = Date, y = Value)) +
  geom_line()

### How to change the format date axis label
# Format : month/day
p1 <- p +
  scale_x_date(date_labels = "%b/%d",date_breaks = "week") +geom_line(colour="blue") + geom_point(colour="blue4")+theme(axis.text.x = element_text(angle=45, hjust = 1))+ggtitle("Month/Day")

# Format : Week
p2 <- p + scale_x_date(date_labels = "%U",date_breaks = "week")+geom_line(colour="blue") + geom_point(colour="blue4") +ggtitle("Week")

# Months only
p3<- p + scale_x_date(date_labels = "%B",date_breaks = "week")+ geom_line(colour="blue") + geom_point(colour="blue4")+ggtitle("Months") +theme(axis.text.x = element_text(angle=45, hjust = 1))

library(gridExtra)
grid.arrange(p1, p2, p3, ncol=2, nrow = 2)

### Datetime Series axis

Datetime <- Sys.time() - 0:359
Value <- runif(360)
Data <- data.frame(Datetime,Value)

ggplot(data=Data, aes(x = Datetime, y = Value)) +
  geom_line(colour="blue") + geom_point(colour="blue4") + scale_x_datetime(date_breaks = "1 min", date_labels = ("%b %d %H:%M:%S")) +
  theme(axis.text.x = element_text(angle = 45, vjust = 1.0, hjust = 1.0))+ggtitle("Month Day Hour:Minute:Second")
```
