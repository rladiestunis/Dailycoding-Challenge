## Day 46 of #dailycoding challenge ⬇️

Today we are interested in time series and we are using a new package called #modeltime created by Matt Dancho.

Today we will explore some functions of #modeltime.

* plot_time_series() which creates a nice graph of your data.

* initial_time_split() which splits the data into training and split sets.

* arima_reg() to create a basic univariate ARIMA model using "AutoArima".

* exp_smoothing() to create an Error-Trend-Season(ETS) model using an Exponential Smoothing State Space model.

* prophet_reg() to create a prophet model.

*modeltime_table() to add the models into a scalable structure.

* modeltime_forecast() and plot-modeltime_forecast() to create a plot of the forecast test.

For more details about the #modeltime package, please take a look at this link 👉🏻 https://lnkd.in/dwhvnN6

Happy Coding Learning !

``` r
#Loading Libraries 
library(tidymodels)
library(modeltime)
library(tidyverse)
library(lubridate)
library(timetk)

# This toggles plots from plotly (interactive) to ggplot (static)
interactive <- TRUE

# Data
m750 <- m4_monthly %>% filter(id == "M750")

# Plotting the data 
m750 %>%
  plot_time_series(date, value, .interactive = interactive)

# Split Data 80/20
splits <- initial_time_split(m750, prop = 0.9)

# Model 1: auto_arima 
model_fit_arima_no_boost <- arima_reg() %>%
  set_engine(engine = "auto_arima") %>%
  fit(value ~ date, data = training(splits))

# Model 2: ets 
model_fit_ets <- exp_smoothing() %>%
  set_engine(engine = "ets") %>%
  fit(value ~ date, data = training(splits))

# Model 3: prophet 
model_fit_prophet <- prophet_reg() %>%
  set_engine(engine = "prophet") %>%
  fit(value ~ date, data = training(splits))

# Add fitted models to a Model Table

models_tbl <- modeltime_table(
  model_fit_arima_no_boost,
  model_fit_ets,
  model_fit_prophet
)

models_tbl

# Calibrate the model to a testing set
calibration_tbl <- models_tbl %>%
  modeltime_calibrate(new_data = testing(splits))

calibration_tbl

# Visualizing the Forecast Test 
calibration_tbl %>%
  modeltime_forecast(
    new_data    = testing(splits),
    actual_data = m750
  ) %>%
  plot_modeltime_forecast(
    .legend_max_width = 25, # For mobile screens
    .interactive      = interactive
  )
 ```
