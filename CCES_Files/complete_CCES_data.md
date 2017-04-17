Did You Vote? Complete
================

``` r
vote16 <- read.csv("~/Desktop/oh-elections-project/CCES_Files/CCES16.csv")

#making a vote column
vote16complete <- mutate(vote16, voted = ifelse(askvote %in% 1:4,"no",
                                            ifelse(askvote %in% 5, "yes",  "NAorMissing" ))) %>%
  
#making a party column
  mutate(party = ifelse(party_ID %in% 1,"Democrat",
ifelse(party_ID %in% 2, "Republican", 
ifelse(party_ID %in% 3, "Independent",
ifelse(party_ID %in% 4, "Other",  "NAorMissing" ))))) %>%

  # making a registered column

  mutate(registered = ifelse(votereg %in% 1, "Yes", 
                                                                           ifelse(votereg %in% 2, "No", 
        ifelse(votereg %in% 3, "DontKnow", "NAorMissing"
                                    )))) %>%
  
#vote method method
  mutate(method_vote = ifelse(vote_method %in% 1, "In person on election day", 
                              ifelse(vote_method %in% 2, "In person early", 
                              ifelse(vote_method %in% 3, "Voted by mail or absentee", "Dontknow_skipped_notasked"
                              )))) %>% select(weight, age, voted, party, registered, method_vote)
```

``` r
vote14 <- read.csv("~/Desktop/oh-elections-project/CCES_Files/CCES14.csv")

#making a vote column
vote14complete <- mutate(vote14, voted = ifelse(askvote %in% 1:4,"no",
                                            ifelse(askvote %in% 5, "yes",  "NAorMissing" ))) %>%
  
#making a party column
  mutate(party = ifelse(party_ID %in% 1,"Democrat",
ifelse(party_ID %in% 2, "Republican", 
ifelse(party_ID %in% 3, "Independent",
ifelse(party_ID %in% 4, "Other",  "NAorMissing" ))))) %>%

  # making a registered column

  mutate(registered = ifelse(votereg %in% 1, "Yes", 
                                                                           ifelse(votereg %in% 2, "No", 
        ifelse(votereg %in% 3, "DontKnow", "NAorMissing"
                                    )))) %>%
  
#vote method method
  mutate(method_vote = ifelse(vote_method %in% 1, "In person on election day", 
                              ifelse(vote_method %in% 2, "In person early", 
                              ifelse(vote_method %in% 3, "Voted by mail or absentee", "Dontknow_skipped_notasked"
                              )))) %>%
#remove old columns
select(weight, age, voted, party, registered, method_vote)
```

``` r
vote12 <- read.csv("~/Desktop/oh-elections-project/CCES_Files/CCES12.csv")

#making a vote column
vote12complete <- mutate(vote12, voted = ifelse(askvote %in% 1:4,"no",
                                            ifelse(askvote %in% 5, "yes",  "NAorMissing" ))) %>%
  
#making a party column
  mutate(party = ifelse(party_ID %in% 1,"Independent",
ifelse(party_ID %in% 2, "Democrat", 
ifelse(party_ID %in% 3, "Republican",
ifelse(party_ID %in% 4, "Other",  "NAorMissing" ))))) %>%

  # making a registered column

  mutate(registered = ifelse(votereg %in% 1, "Yes", 
                                                                           ifelse(votereg %in% 2, "No", 
        ifelse(votereg %in% 3, "DontKnow", "NAorMissing"
                                    )))) %>%
  
#vote method method
  mutate(method_vote = ifelse(vote_method %in% 1, "In person on election day", 
                              ifelse(vote_method %in% 2, "In person early", 
                              ifelse(vote_method %in% 3, "Voted by mail or absentee", "Dontknow_skipped_notasked"
                              )))) %>%
#remove old columns
select(weight, age, voted, party, registered, method_vote)
```

``` r
write.csv(vote16complete, file = "CCES_vote16.csv")
write.csv(vote14complete, file = "CCES_vote14.csv")
write.csv(vote12complete, file = "CCES_vote12.csv")
```
