P8105: Homework 1
================
Sydney Musick (sm4993)
9/29/21

# Problem 1

Loading in the tidyverse library.

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.4     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
    ## ✓ readr   2.0.1     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

Creating the dataframe.

``` r
q1_df = tibble(
  random_sample = rnorm(10),
  vec_pos = random_sample > 0,
  vec_character = c("New York", "Michigan", "Florida", "Texas", "Georgia", "California", "Washington", "Colorado", "Utah", "Nevada"), 
  vec_factor = factor(c("rain", "sun", "snow", "snow", "snow", "rain", "sun", "sun", "sun", "snow"))
)
```
