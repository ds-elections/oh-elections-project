Cleaned and Tidied CCES Data
================

Each dataset has over 400 variables. They become increasingly well labeled (12&lt;14&lt;16) but even the 2016 has hundreds of illegible variables. We're going to have to take some time to figure out what each column actually is and whether we need it. Since we're mostly looking at age I suspect we don't need most of the columns but it's going to be a bear to sort through this. Ohio is input state 39.

``` r
CCES12 <- read_tsv("/home/shaswitz/Desktop/oh-elections-project/CCES_data/CCES12.tab") %>% mutate(age = 2017-(birthyr)) %>% select(StateAbbr, age, votereg, CC401, CC403, CC350) %>% filter(StateAbbr == "OH") 
```

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_integer(),
    ##   weight_vv = col_double(),
    ##   weight_vv_post = col_double(),
    ##   V103 = col_double(),
    ##   CC317_t = col_character(),
    ##   CC354b_t = col_character(),
    ##   CC354c_t = col_character(),
    ##   CC355_t = col_character(),
    ##   CC355b_t = col_character(),
    ##   CC356_t = col_character(),
    ##   CC356b_t = col_character(),
    ##   CC390_t = col_character(),
    ##   CC390b_t = col_character(),
    ##   employertext = col_character(),
    ##   employtext = col_character(),
    ##   employ_t = col_character(),
    ##   pid3_t = col_character(),
    ##   religpew_t = col_character(),
    ##   religpew_protestant_t = col_character(),
    ##   religpew_baptist_t = col_character(),
    ##   religpew_methodist_t = col_character()
    ##   # ... with 171 more columns
    ## )

    ## See spec(...) for full column specifications.

    ## Warning: 195 parsing failures.
    ##  row          col           expected actual
    ## 2793 CC421_t      delimiter or quote e     
    ## 2793 CC421_t      delimiter or quote .     
    ## 3278 CC412_t      delimiter or quote a     
    ## 3278 CC412_t      delimiter or quote _     
    ## 3278 CCj413_WV_97 an integer         __NA__
    ## .... ............ .................. ......
    ## See problems(...) for more details.

``` r
colnames(CCES12)[4] <- "askvote"
colnames(CCES12)[6] <- "party_ID"
colnames(CCES12)[5] <- "vote_method"
write.csv(CCES12, file = "CCES12.csv")
CCES14 <- read_tsv("/home/shaswitz/Desktop/oh-elections-project/CCES_data/CCES14.tab") %>% mutate(age = 2017-(birthyr)) %>% select(StateAbbr, age, votereg, pid3, CC401, CC403) %>% filter(StateAbbr == "OH")
```

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_integer(),
    ##   weight = col_double(),
    ##   lookupzip = col_character(),
    ##   countyname = col_character(),
    ##   countyfips = col_character(),
    ##   CurrentGovName = col_character(),
    ##   CurrentGovParty = col_character(),
    ##   CurrentHouseGender = col_character(),
    ##   CurrentHouseName = col_character(),
    ##   CurrentHouseParty = col_character(),
    ##   CurrentSen1Gender = col_character(),
    ##   CurrentSen1Name = col_character(),
    ##   CurrentSen1Party = col_character(),
    ##   CurrentSen2Gender = col_character(),
    ##   CurrentSen2Name = col_character(),
    ##   CurrentSen2Party = col_character(),
    ##   GovCand1Name = col_character(),
    ##   GovCand1Party = col_character(),
    ##   GovCand2Name = col_character(),
    ##   GovCand2Party = col_character(),
    ##   HouseCand1Gender = col_character()
    ##   # ... with 184 more columns
    ## )
    ## See spec(...) for full column specifications.

    ## Warning: 1562 parsing failures.
    ## row                 col           expected actual
    ##  83 jobactivities       delimiter or quote       
    ## 431 CurrentGovName      delimiter or quote      B
    ## 431 CurrentGovName      delimiter or quote       
    ## 431 CurrentGovName_post delimiter or quote      B
    ## 431 CurrentGovName_post delimiter or quote       
    ## ... ................... .................. ......
    ## See problems(...) for more details.

``` r
colnames(CCES14)[4] <- "party_ID"
colnames(CCES14)[5] <- "askvote"
colnames(CCES14)[6] <- "vote_method"
write.csv(CCES14, file = "CCES14.csv")
CCES16 <- read_tsv("/home/shaswitz/Desktop/oh-elections-project/CCES_data/CCES16.tab") %>% mutate(age = 2017-(birthyr)) %>% select(inputstate, votereg, age, CC16_421a, CC16_401, CC16_403) %>% filter(inputstate == "39")
```

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_integer(),
    ##   commonweight = col_double(),
    ##   commonweight_post = col_double(),
    ##   lookupzip = col_character(),
    ##   countyfips = col_character(),
    ##   countyname = col_character(),
    ##   CurrentGovName = col_character(),
    ##   CurrentGovParty = col_character(),
    ##   CurrentHouseGender = col_character(),
    ##   CurrentHouseName = col_character(),
    ##   CurrentHouseParty = col_character(),
    ##   CurrentSen1Gender = col_character(),
    ##   CurrentSen1Name = col_character(),
    ##   CurrentSen1Party = col_character(),
    ##   CurrentSen2Gender = col_character(),
    ##   CurrentSen2Name = col_character(),
    ##   CurrentSen2Party = col_character(),
    ##   GovCand1Name = col_character(),
    ##   GovCand1Party = col_character(),
    ##   GovCand2Name = col_character(),
    ##   GovCand2Party = col_character()
    ##   # ... with 152 more columns
    ## )
    ## See spec(...) for full column specifications.

    ## Warning: 5361 parsing failures.
    ## row                 col           expected actual
    ##  22 HouseCand2Name      delimiter or quote      T
    ##  22 HouseCand2Name      delimiter or quote       
    ##  22 HouseCand2Name_post delimiter or quote      T
    ##  22 HouseCand2Name_post delimiter or quote       
    ##  72 HouseCand1Name      delimiter or quote      C
    ## ... ................... .................. ......
    ## See problems(...) for more details.

``` r
colnames(CCES16)[4] <- "party_ID"
colnames(CCES16)[5] <- "askvote"
colnames(CCES16)[6] <- "vote_method"
write.csv(CCES16, file = "CCES16.csv")
```
