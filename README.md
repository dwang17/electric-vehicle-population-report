DS 2020 Final Project Report
================
David Wang, Logan Pappas
2025-11-30

Topic: Differences in electric range across various vehicle makes and
models

``` r
#load the data
library(tidyverse)
```

    ## Warning: package 'ggplot2' was built under R version 4.5.2

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.4     ✔ readr     2.1.5
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.1
    ## ✔ ggplot2   4.0.0     ✔ tibble    3.3.0
    ## ✔ lubridate 1.9.4     ✔ tidyr     1.3.1
    ## ✔ purrr     1.1.0     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
electric_vehicle_population_data <- read_csv("Electric_Vehicle_Population_Data.csv")
```

    ## Rows: 269673 Columns: 17
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (11): VIN (1-10), County, City, State, Make, Model, Electric Vehicle Typ...
    ## dbl  (6): Postal Code, Model Year, Electric Range, Base MSRP, Legislative Di...
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
head(electric_vehicle_population_data)
```

    ## # A tibble: 6 × 17
    ##   `VIN (1-10)` County   City    State `Postal Code` `Model Year` Make      Model
    ##   <chr>        <chr>    <chr>   <chr>         <dbl>        <dbl> <chr>     <chr>
    ## 1 3C3CFFGE1G   Yakima   Yakima  WA            98908         2016 FIAT      500  
    ## 2 WP0AB2Y16L   King     Auburn  WA            98092         2020 PORSCHE   TAYC…
    ## 3 5YJ3E1EB2J   King     Seattle WA            98109         2018 TESLA     MODE…
    ## 4 5YJYGDEF5L   King     Seattle WA            98125         2020 TESLA     MODE…
    ## 5 5YJXCBE22J   Thurston Olympia WA            98501         2018 TESLA     MODE…
    ## 6 1G1FZ6S00L   Thurston Olympia WA            98506         2020 CHEVROLET BOLT…
    ## # ℹ 9 more variables: `Electric Vehicle Type` <chr>,
    ## #   `Clean Alternative Fuel Vehicle (CAFV) Eligibility` <chr>,
    ## #   `Electric Range` <dbl>, `Base MSRP` <dbl>, `Legislative District` <dbl>,
    ## #   `DOL Vehicle ID` <dbl>, `Vehicle Location` <chr>, `Electric Utility` <chr>,
    ## #   `2020 Census Tract` <chr>
