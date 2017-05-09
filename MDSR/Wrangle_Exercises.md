MDSR Wrangling Questions
================

Wrangling Unruly Data
---------------------

There's a lot of data here. Let's start by making information on the year 2012 more managable.

Exercise 1
==========

The CCES asks over 400 questions, most of which are irrelevant for comparing to the voter file. Narrow the dataset down to just the pertinent information. This should include the weighting of each participant, the state they live in, whether they're registered to vote, the party they're registered with, and whether they voted in the 2012 election.

Select for only the Ohio participants.

Next recode the answers so that the table is more legible - it doesn't matter why someone didn't vote so all of those options can be collated into one answer, no.

You should now have a table that looks like this:

``` r
head(vote12table)
```

    ##      weight age registered       party       voted
    ## 1 0.2256249  57        Yes    Democrat         yes
    ## 2 0.2321987  24        Yes  Republican         yes
    ## 3 0.1080216  50        Yes Independent         yes
    ## 4 0.2524297  59        Yes NAorMissing NAorMissing
    ## 5 1.9587926  35        Yes Independent         yes
    ## 6 1.3827350  41        Yes Independent         yes

Exercise 2
==========

Now, let's do the same thing with the Ohio voter registration file. There's a lot less here, and we only have Ohio voters but we want to narrow it down to just the general election in 2012 and get rid of any superfluous information like the voter's name or address.

You'll also want to create an age variable out of birthdate. For this, make sure you have the lubridate package installed.

``` r
head(Ohio12table)
```

    ##   age party voted
    ## 1  60  <NA>   yes
    ## 2  66     D   yes
    ## 3  56  <NA>    no
    ## 4  88  <NA>   yes
    ## 5  33  <NA>    no
    ## 6  93     R   yes
