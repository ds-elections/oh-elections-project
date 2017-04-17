Visualizations
================

``` r
viz16 <- read_csv("~/Desktop/oh-elections-project/CCES_Files/CCES_vote16.csv")
```

    ## Warning: Missing column names filled in: 'X1' [1]

    ## Parsed with column specification:
    ## cols(
    ##   X1 = col_integer(),
    ##   weight = col_double(),
    ##   age = col_integer(),
    ##   voted = col_character(),
    ##   party = col_character(),
    ##   registered = col_character(),
    ##   method_vote = col_character()
    ## )

``` r
viz14 <- read_csv("~/Desktop/oh-elections-project/CCES_Files/CCES_vote14.csv")
```

    ## Warning: Missing column names filled in: 'X1' [1]

    ## Parsed with column specification:
    ## cols(
    ##   X1 = col_integer(),
    ##   weight = col_double(),
    ##   age = col_integer(),
    ##   voted = col_character(),
    ##   party = col_character(),
    ##   registered = col_character(),
    ##   method_vote = col_character()
    ## )

``` r
viz12 <- read_csv("~/Desktop/oh-elections-project/CCES_Files/CCES_vote12.csv")
```

    ## Warning: Missing column names filled in: 'X1' [1]

    ## Parsed with column specification:
    ## cols(
    ##   X1 = col_integer(),
    ##   weight = col_double(),
    ##   age = col_integer(),
    ##   voted = col_character(),
    ##   party = col_character(),
    ##   registered = col_character(),
    ##   method_vote = col_character()
    ## )

``` r
ohfiles <- read_csv("~/Desktop/oh-elections-project/Ohio_df_lite.csv")
```

    ## Warning: Missing column names filled in: 'X1' [1]

    ## Parsed with column specification:
    ## cols(
    ##   X1 = col_integer(),
    ##   SOS_VOTERID = col_character(),
    ##   COUNTY_ID = col_character(),
    ##   DATE_OF_BIRTH = col_date(format = ""),
    ##   REGISTRATION_DATE = col_date(format = ""),
    ##   VOTER_STATUS = col_character(),
    ##   PARTY_AFFILIATION = col_character(),
    ##   RESIDENTIAL_CITY = col_character(),
    ##   RESIDENTIAL_STATE = col_character(),
    ##   `PRIMARY-03/06/2012` = col_character(),
    ##   `GENERAL-11/06/2012` = col_character(),
    ##   `PRIMARY-05/06/2014` = col_character(),
    ##   `GENERAL-11/04/2014` = col_character(),
    ##   `PRIMARY-03/15/2016` = col_character(),
    ##   `GENERAL-06/07/2016` = col_character(),
    ##   `PRIMARY-09/13/2016` = col_character(),
    ##   `GENERAL-11/08/2016` = col_character()
    ## )
