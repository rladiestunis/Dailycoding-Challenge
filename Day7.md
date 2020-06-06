## Day 7 of #dailycoding challenge ⬇️

Today we are interested in #R functions that are dealing with file and directory manipulation in R.

Every R session has a default location on your operating system’s file structure called the working directory. Having an idea of where your files are stored with R and how to manipulate those files is really important.

▪ getwd() : tells you what the current working directory is.

▪ setwd(): changes your working directory. The working directory has to be a character string.

▪ dir.create(): creates a new directory.

▪ dir.exists(): checks if a folder exixts.

▪ file.create(): creates an empty file.

▪ file.remove(): removes a file.

▪ list.files(): lists all the files in a directory.

▪ file.exists(): checks if a file exixts.

▪ unlink(): deletes a specified folder.

Take a look at the examples below to understand more the functionnality of every function ⬇️

Happy Coding Learning !

You can install the released version of covid19tunisia with:

``` r
 # It’s usually a good idea before starting a script to first know what directory you’re working in
 # get current working directory
 getwd()
 # create a new directory
 dir.create("dailycoding")
 # check if a folder exists
 dir.exists("dailycoding")
 # set working directory
 setwd("dailycoding")
 # let's recheck our working directory
 getwd()
 # create an empty file
 file.create("test_csv_file.csv")
 file.create("test_text_file.txt")
 # list files in a specified folder
 list.files()
 # check if a file exists
 file.exists("test_text_file.txt")
 #get the base name of a file
 basename("/home/rstudio-user/dailycoding/test_text_file.txt")
 # delete a file
 file.remove("test_text_file.txt")
 list.files()
 # delete a directory
 unlink("dailycoding", recursive = TRUE)
 list.files()

```
