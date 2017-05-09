MDSR Wrangling Questions
================

Wrangling Unruly Data
=====================

Ohio Voter Demographics (Context)
---------------------------------

Voter participation is the bedrock of American democracy. In order to understand who votes and how, we can look either at estimates derived from samples in studies like The Cooperative Congressional Elections Study (CCES), which rely on self reporting but cover a broad range of topics, or directly looking at voter files, which though completely accurate give us much less information. Demographic information can help predict voting behavior, especially in key swing states like Ohio but this is only true if the representative samples are, in fact, representative. Do people, when asked, over report their voting habits?

Ohio does not collect any demographic information other than age when residents register to vote. Even with this limited information, we can look at whether the age range represented in the CCES accurately reflects the age range of Ohio voters. Who votes in Ohio and who says they vote? Are representative samples of the state actually representative? How reflective are surveys like CCES at all?

There's a lot of data here. Let's start by making information on the year 2012 more managable.

### Exercise 1

The CCES asks over 400 questions, most of which are irrelevant for comparing to the voter file. Narrow the dataset down to just the pertinent information. This should include the weighting of each participant, the state they live in, whether they're registered to vote, the party they're registered with, and whether they voted in the 2012 election.

Select for only the Ohio participants.

Next recode the answers so that the table is more legible - it doesn't matter why someone didn't vote so all of those options can be collated into one answer, no.

You should now have a table that looks like this:

``` r
head(vote12table)
```

    ## # A tibble: 6 × 5
    ##      weight   age registered       party       voted
    ##       <dbl> <dbl>      <chr>       <chr>       <chr>
    ## 1 0.2256249    57        Yes    Democrat         yes
    ## 2 0.2321987    24        Yes  Republican         yes
    ## 3 0.1080216    50        Yes Independent         yes
    ## 4 0.2524297    59        Yes NAorMissing NAorMissing
    ## 5 1.9587926    35        Yes Independent         yes
    ## 6 1.3827350    41        Yes Independent         yes

### Exercise 2

Now, let's do the same thing with the pared down Ohio voter registration file. There's a lot less here, and we only have Ohio voters but we want to narrow it down to just the general election in 2012 and get rid of any superfluous information like the voter's name or address.

You'll also want to create an age variable out of birthdate. For this, make sure you have the lubridate package installed.

Play around with the data, is there anything obviously off with it? How would you explain any irregularities found?

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
