Models
================

``` r
m12 <- glm(CCESminusVoterReg ~ age, data = diff12, family = gaussian())
summary(m12)
```

    ## 
    ## Call:
    ## glm(formula = CCESminusVoterReg ~ age, family = gaussian(), data = diff12)
    ## 
    ## Deviance Residuals: 
    ##      Min        1Q    Median        3Q       Max  
    ## -0.34880  -0.06476   0.01580   0.05797   0.22422  
    ## 
    ## Coefficients:
    ##              Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)  0.328243   0.038043   8.628 1.99e-12 ***
    ## age         -0.003642   0.000636  -5.727 2.73e-07 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for gaussian family taken to be 0.0105977)
    ## 
    ##     Null deviance: 1.04700  on 67  degrees of freedom
    ## Residual deviance: 0.69945  on 66  degrees of freedom
    ## AIC: -112.26
    ## 
    ## Number of Fisher Scoring iterations: 2

``` r
m14 <- glm(CCESminusVoterReg ~ age, data = diff14, family = gaussian())
summary(m14)
```

    ## 
    ## Call:
    ## glm(formula = CCESminusVoterReg ~ age, family = gaussian(), data = diff14)
    ## 
    ## Deviance Residuals: 
    ##      Min        1Q    Median        3Q       Max  
    ## -0.51231  -0.06227   0.00549   0.06720   0.51669  
    ## 
    ## Coefficients:
    ##               Estimate Std. Error t value Pr(>|t|)  
    ## (Intercept)  0.0896208  0.0517877   1.731   0.0881 .
    ## age         -0.0009724  0.0008765  -1.109   0.2712  
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for gaussian family taken to be 0.02200795)
    ## 
    ##     Null deviance: 1.5236  on 69  degrees of freedom
    ## Residual deviance: 1.4965  on 68  degrees of freedom
    ## AIC: -64.522
    ## 
    ## Number of Fisher Scoring iterations: 2

``` r
m16 <- glm(CCESminusVoterReg ~ age, data = diff16, family = gaussian())
summary(m16)
```

    ## 
    ## Call:
    ## glm(formula = CCESminusVoterReg ~ age, family = gaussian(), data = diff16)
    ## 
    ## Deviance Residuals: 
    ##      Min        1Q    Median        3Q       Max  
    ## -0.51231  -0.06227   0.00549   0.06720   0.51669  
    ## 
    ## Coefficients:
    ##               Estimate Std. Error t value Pr(>|t|)  
    ## (Intercept)  0.0896208  0.0517877   1.731   0.0881 .
    ## age         -0.0009724  0.0008765  -1.109   0.2712  
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## (Dispersion parameter for gaussian family taken to be 0.02200795)
    ## 
    ##     Null deviance: 1.5236  on 69  degrees of freedom
    ## Residual deviance: 1.4965  on 68  degrees of freedom
    ## AIC: -64.522
    ## 
    ## Number of Fisher Scoring iterations: 2
