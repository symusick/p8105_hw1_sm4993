P8105: Homework 1
================
Sydney Musick (sm4993)
9/29/21

# Problem 1

### Loading in the tidyverse library.

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

### Creating the data frame and finding the means of the variables.

``` r
set.seed(1000)

q1_df = tibble(
  random_sample = rnorm(10),
  vec_pos = random_sample > 0,
  vec_character = c("New York", "Michigan", "Florida", "Texas", "Georgia", "California", "Washington", "Colorado", "Utah", "Nevada"), 
  vec_factor = factor(c("rain", "sun", "snow", "snow", "snow", "rain", "sun", "sun", "sun", "snow"))
)

mean_random_sample = mean(pull(q1_df, random_sample))
mean_vec_pos = mean(pull(q1_df, vec_pos))
mean_vec_character = mean(pull(q1_df, vec_character))
```

    ## Warning in mean.default(pull(q1_df, vec_character)): argument is not numeric or
    ## logical: returning NA

``` r
mean_vec_factor = mean(pull(q1_df, vec_factor))
```

    ## Warning in mean.default(pull(q1_df, vec_factor)): argument is not numeric or
    ## logical: returning NA

Using this code, we can take the means of `random_sample` and of
`vec_positive`, but not of `vec_character` or `vec_factor`.

### Taking the means of `vec_character` and `vec_factor` using the `as.numeric` function.

``` r
as.numeric(pull(q1_df, vec_character))
```

    ## Warning: NAs introduced by coercion

``` r
as.numeric(pull(q1_df, vec_factor))
```

Using this code, we were able to take the mean of `vec_factor` but not
of `vec_character`. This occurs because, using `as.numeric`, we are able
to convert the factor variable to integers by numbering the different
factor “levels”. The character variable wasn’t able to be converted
because there is no order or logic to the observations within that
variable. This explains the results we get when we take the means of
these variables.

# Problem 2

### Loading the `penguins` dataset into R.

``` r
data("penguins", package = "palmerpenguins")
```

The `penguins` dataset has 344 rows and 8 columns. It includes variables
species, island, bill\_length\_mm, bill\_depth\_mm, flipper\_length\_mm,
body\_mass\_g, sex, year. The mean flipper length of the penguins in the
dataset is 200.9152047.

### Creating a scatterplot of flipper\_length\_mm vs bill\_length\_mm, and species by color.

``` r
ggplot(penguins, aes(x = bill_length_mm, y = flipper_length_mm, color = species)) + geom_point()
```

![](hw1_rmarkdown_files/figure-gfm/ggplot-1.png)<!-- -->

``` r
ggsave("scatter_plot.pdf", height = 4, width = 6)
```
