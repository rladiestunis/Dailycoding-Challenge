## Day 41 of #dailycoding challenge ⬇️

Today we are interested in showing you some helpful #keyboard #shortcuts to use while being working on #RStudio.

In order to navigate between the main #rstudio panels, you may use : 

CTRL + 1 to switch to the #source

CTRL + 2 to switch to the #console

CTRL + 3 to display the #help panel

CTRL + 5 to display the #files

CTRL + 6 to display the #plots

CTRL + 7 to display the #packages

CTRL + 8 to display the #environment


If you end up with just one visible panel, you can get the 4 panels with ◾CTRL + SHIFT + ALT + 0◾ on Windows and ◾CTRL + SHIFT + 0◾ on Ubuntu or go to the View menu -> Panes -> Show All Panes.

There are also some shortcuts that aim to write the whole code : 

◾ ALT + - ◾ will write the assignment sign <- (with spaces before and after)

◾ CTRL + SHIFT + M ◾ for writing pipes ◾ %>% ◾

◾ CTRL + SHIFT + R ◾ will allow you to properly write a title for a new section

If you have a piece of code that you want to transform into a function, this keyboard shortcut ◾ CTRL + ALT + X ◾ will do all the work.

◾ CTRL + ALT + V ◾ allows to extract a part of the code to make it a variable.

Happy Coding Learning !

``` r
# New Section -------------------------------------------------------------

# Using the keyboard shortcut CTRL + ALT + X
mean <- mean(a, b)

# After selecting this code and typing CTRL + ALT + X, a window opens like in the pic below
# and we may note the code turns into :

mean_function <- function(a, b) {
  mean <- mean(a, b)
  mean
}


# Using the keyboard shortcut CTRL + ALT + V
print("Welcome to R-Ladies Tunis")

# After selecting this code and typing CTRL + ALT + V, a window opens like in the pic below
# and we may note the code turns into :
text <- print("Welcome to R-Ladies Tunis")
text
```
