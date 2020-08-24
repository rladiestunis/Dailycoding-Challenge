## Day 40 of #dailycoding challenge ⬇️

Today, we are interested in #windrose function from the package clifro.
The function needs as arguments:

· Speed: numeric vector of wind speeds

· Direction: numeric vector of wind directions

· Facet: character or factor vector of the facets used to plot the various windroses

· n_directions: the number of direction bins to plot (petals on the rose). The number of directions defaults to 12

· n_speeds: the number of equally spaced wind speed bins to plot

· speed_cuts: numeric vector containing the cut points for the wind speed intervals

Take a look at the examples below to understand more ⬇️
Happy Coding Learning!

``` r
install.packages("clifro")
library(clifro)
### Create a data frame
wind_df = data.frame(wind_speeds = c(rweibull(80, 2, 4), rweibull(20, 3, 9)),wind_dirs = c(rnorm(80, 135, 55),rnorm(20, 315, 35)) %% 360,station = rep(rep(c("Station A", "Station B"), 2),rep(c(40, 10), each = 2)))
head(wind_df)
#### Plot a windrose with the default arguments
with(wind_df, windrose(speed= wind_speeds, direction= wind_dirs))

#### Plot a windrose for each station
with(wind_df, windrose(speed=wind_speeds, direction=wind_dirs, facet= station, n_col = 2))
 ```
