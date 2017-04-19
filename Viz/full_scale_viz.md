Data visualization of voting by age according to polls
================

creating summary tables for voting percentage my age with Ohio data
-------------------------------------------------------------------

``` r
 Ohio_df_lite <- read.csv ("~/Downloads/Ohio_df_lite.csv")
 
 #mutate to make an age variable
 
 Ohio_df_lite <- mutate(Ohio_df_lite, age = 2017 - year(DATE_OF_BIRTH))
 
 ohio_age_vote <- select(Ohio_df_lite, age, GENERAL.11.08.2016) %>% filter(age < 99)
 #remove ohio_df_lite to save space
 rm(Ohio_df_lite)

#rename column names
colnames(ohio_age_vote) <- c("age", "vote")



#renaming the NAs
ohio_age_vote1 <- mutate(ohio_age_vote, newvote = ifelse(vote %in% "X", "X", "O"))

Ohio_summary2 <- ohio_age_vote1 %>% group_by(age) %>% dplyr::summarise(perc = base::mean(newvote == "X"), n())

# https://github.com/ProjectMOSAIC/mosaic/issues/625
```

polling data : summarized voting percent by age
-----------------------------------------------

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
smallviz16 <- viz16 %>% select(age, voted) %>% group_by(age) %>% summarize(percent_voted = base::mean(voted == "yes"), n())

#noNAviz16 <- filter(viz16, voted %in% c("yes", "no"))
#noNAsmallviz16 <- noNAviz16 %>% select(age, voted) %>% group_by(age) %>% summarize(percent_voted_noNA = base::mean(voted == "yes"))
```

``` r
#tidying it up so we can merge


filteredCCES <- filter(smallviz16, age %in% 19:91)

filteredOhio <- filter(Ohio_summary2, age %in% 19:91)
```

``` r
#merging
merged <- merge(filteredCCES, filteredOhio, by = "age")
colnames(merged) <-c("age", "CCESpercent", "CCESN", "VoterRegPercent", "VoterRegN")


diff <- mutate(merged, CCESminusVoterReg = CCESpercent-VoterRegPercent)

SEdiff <- mutate(diff, SE = sqrt((CCESpercent*(1-CCESpercent))/CCESN)+((VoterRegPercent*(1-VoterRegPercent))/VoterRegN))

ggplot(SEdiff, aes(age, CCESminusVoterReg)) + geom_errorbar(aes(ymin = CCESminusVoterReg - SE, ymax = CCESminusVoterReg + SE))
```

![](full_scale_viz_files/figure-markdown_github/Merge%20and%20Plot-1.png)
