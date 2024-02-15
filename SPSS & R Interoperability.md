# 4 Statistical Analyses That Demonstrate the Interoperability between SPSS & R



### R
   1. one-sample t-Test: 
```
      t.test(Data$Variable, mu = ##, alternative = “two.sided”)

#a sample is tested against a population mean
#The default setting of confidence level is 0.95. You can add `conf.level=0.99`
#after `alternative` to make it another value.
```
or `alternative = "less"` or `"more"`


   2. independent samples t-Test:
```
      leveneTest(Data$DV~Data$IV)

#leveneTest() from the {car} package is Levene's Test for equal variance of the two samples
#from the same population, DV is changed by IV

      t.test(Data$DV~Data$IV, var.equal=TRUE/FALSE, alternative = “two.sided”, “less”, “greater”)

#var.equal is equal variance based on Levene's Test for equal variance
#The default setting of confidence level is 0.95. You can add `conf.level=0.99`
#after `alternative` to make it another value.
```


   3. Paired/Dependent Samples t-Test: 
```
      t.test(Data$Variable2, Data$Variable1, paired=TRUE, alternative=“two.sided”, “less”, “greater”)

#testing if there is a difference between two measurements in the same individual
#The default setting of confidence level is 0.95. You can add `conf.level=0.99`
#after `alternative` to make it another value.
```


   4. Two independent sample unequal variance or Welch’s Test:
```
      t.test(x, y, alternative = c(“two.sided”, “less”, “greater”))

#x: first population
#y: second population
#The results will give a p-value and the two means for the two populations.
```



## Analysis 2: ANOVA and post hocs

The analysis of variance compares between-group variability with within-group variability. This exact ratio of comparison is the F ratio. There are 4 types of ANOVA: one-way ANOVA for one factor and one DV, factorial ANOVA for multiple factors, multivariate ANOVA (MANOVA) for multiple DVs, and repeated-measures ANOVA for multiple within-subject measurements.


### SPSS
a) the *point-click* method

- For one-way ANOVA and repeated-measures ANOVA, in the toolbar, select Analyze > Bayesian Statistics > a specific ANOVA
  
  ![SPSS_ANOVA1](https://github.com/petrayang2002/InterStatHub/assets/155834271/323aadab-f63f-4324-a05b-bd25a8f3ac9a)

  
- For factorial and multivariate ANOVA, in the toolbar, select Analyze > General Linear Model > Univariate or Multivariate
  
![SPSS_ANOVA2](https://github.com/petrayang2002/InterStatHub/assets/155834271/5b7f88b3-f906-491e-b2cb-9bdcfff7aa49)



b) the *syntax* method

1. one-way ANOVA and post hoc
```
ONEWAY Pretest BY Condition1
  /MISSING ANALYSIS
  /POSTHOC=BTUKEY ALPHA(0.05).
```

2. factorial ANOVA, post hoc, and plot
```
UNIANOVA Pretest BY Condition1 Condition2
  /METHOD=SSTYPE(3)
  /INTERCEPT=INCLUDE
  /POSTHOC=Condition1 Condition2(BTUKEY) 
  /PLOT=PROFILE(Condition1*Condition2) TYPE=LINE ERRORBAR=NO MEANREFERENCE=NO YAXIS=AUTO
  /PRINT ETASQ DESCRIPTIVE
  /CRITERIA=ALPHA(.05)
  /DESIGN=Condition1 Condition2 Condition1*Condition2.
```

3. multivariate ANOVA (MANOVA)
```
GLM Time1SampleData Time2SampleData BY Condition1
  /METHOD=SSTYPE(3)
  /INTERCEPT=INCLUDE
  /POSTHOC=Condition1(TUKEY) 
  /PRINT=DESCRIPTIVE
  /CRITERIA=ALPHA(.05)
  /DESIGN= Condition1.
```

4. repeated measures ANOVA and plot
```
GLM Time1SampleData Time2SampleData BY Condition2
  /WSFACTOR=TimeDataset 2 Polynomial 
  /METHOD=SSTYPE(3)
  /PLOT=PROFILE(TimeDataset*Condition2) TYPE=LINE ERRORBAR=NO MEANREFERENCE=NO YAXIS=AUTO
  /PRINT=DESCRIPTIVE 
  /CRITERIA=ALPHA(.05)
  /WSDESIGN=TimeDataset 
  /DESIGN=Condition2.
```


### R

1. one-way ANOVA and post hoc
```
model<-aov(DV~Factor, data=MyData)

# It is important to save your ANOVA using `model` or any other name you want

summary(model)

# Use summary to present the results of your ANOVA.

TukeyHSD(model)

# Using a Tukey HSD function, Conduct a post hoc test of your ANOVA
# to present the 1-1 comparisons between means
# so that specific differences between means can be located.
```


2. factorial ANOVA and post hoc
```
   model<-aov(DV~Factor1*Factor2, data=MyData)

# It is important to save your ANOVA using `model` or any other name

   summary(model)

# Use summary to present the results of your ANOVA.

   TukeyHSD(model, which = “Factor1”)

# Using a Tukey HSD function, Conduct a post hoc test of main effect
# for the first factor in  `which = “Factor1” `

   TukeyHSD(model, which = “Factor2”)

# Post hoc of main effect for the second fector

   TukeyHSD(model)

# Conduct post hoc for the interaction effect between factors 1 and 2 on DV.
```



3. multivariate ANOVA (MANOVA)
```
   model <- manova(cbind(DV1, DV2) ~ Factor, data = MyData)

# It is important to save your ANOVA using `model` or any other name

   summary(model)

# Use summary to present the results of your ANOVA.

   summary.aov(model)

# Conduct another test to see if individual DVs differ between the factor (IV).
```


4. repeated measures ANOVA
``` 
   model <- anova_test(data = MyData, dv = DV, wid = Factor, within = time)

   get_anova_table(model)

# This table gives the F-ratio, df, p-value, and ges (the effect size, which is
# the variability based on the within-subject variable, time.

  
  pairwise_t_test(DV ~ time, paired = TRUE, p.adjust.method = "bonferroni")

# Conduct post hoc tests between different times
```

   
## Analysis 3: Regression and Correlation


## Analysis 4: Mediation


## Analysis 5: Moderation

Binary moderator


## Analysis 6: Exploratory and Confirmatory Factor Analysis
