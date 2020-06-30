## Day 38 of #dailycoding challenge ⬇️

Today we are interested in #R #Shiny. Shiny is a framework for creating web applications using R code. You can create pretty complicated Shiny apps with no knowledge of #HTML, #CSS, or #JavaScript. 

Shiny is an R package that allows you to easily create rich, #interactive web apps. It allows the creator of the application to take the work done in R and expose it via a web browser so that anyone can use it. 

The two key components of every Shiny app : the UI (short for user interface) which defines how the app looks, and the server function which defines how the app works.

Through the upcoming posts, we will be interested in adding UI controls (some inputs and outputs to the UI) and defining them in the server function.

For more details, you may take a look at the Shiny cheatsheet from https://www.rstudio.com/resources/cheatsheets/ which includes the main components of a Shiny app.

Interesting resources :

- [Mastering Shiny book created by Hadley Wickham](https://lnkd.in/eNy4nvN)

- [Engineering Production-Grade Shiny Apps" this book is created by Colin Fay, Sébastien Rochette, Vincent Guyader and Cervan Girard](https://lnkd.in/euJC2QM)

Happy Coding Learning !

``` r
# There are several ways to create a Shiny app. The simplest is to create a new directory for your app,
# and put a single file called app.R in it.
# This app.R file will be used to tell Shiny both how your app should look, and how it should behave.

# Here's a script app.R
library(shiny) # loading the shiny package
ui <- fluidPage(
  "Welcome to R-Ladies Tunis!" # the script defines the user interface, the HTML webpage
                               # that humans interact with. In this case, it’s a page containing
                               # the words "Welcome to R-Ladies Tunis!".
)
# the script specifies the behavior of the app by defining a server function.
# It’s currently empty, so the app doesn’t do anything.
server <- function(input, output, session) {
}
# Then executing shinyApp(ui, server) to construct and start a Shiny application from UI and server.
# After preparing the app.R script, you may click the Run App button in the document toolbar.
shinyApp(ui, server)
```
