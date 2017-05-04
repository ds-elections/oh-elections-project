MDSR Wrangling Questions
================

Wrangling Unruly Data
---------------------

There's a lot of data here. Let's start by making information on the year 2012 more managable.

Exersise 1
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
