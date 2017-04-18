Visualizations
================

``` r
viz16 <- read_csv("~/Desktop/oh-elections-project/CCES_Files/vote16_long.csv")
```

    ## Warning: Missing column names filled in: 'X1' [1]

    ## Parsed with column specification:
    ## cols(
    ##   X1 = col_integer(),
    ##   weight = col_double(),
    ##   age = col_integer(),
    ##   voted = col_character(),
    ##   party = col_character(),
    ##   method_vote = col_character(),
    ##   wtd = col_integer(),
    ##   ids = col_integer()
    ## )

``` r
smallviz16 <- viz16 %>% select(age, voted) %>% group_by(age) %>% summarize(percent_voted = mean(voted == "yes"))
ggplot(smallviz16, aes(x = age, y = percent_voted)) + geom_line()
```

![](OH_data_viz_files/figure-markdown_github/play-1.png)
