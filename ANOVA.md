# ANOVA and post hocs

The analysis of variance compares between-group variability with within-group variability. This exact ratio of comparison is the F ratio. There are 4 types of ANOVA: one-way ANOVA for one factor and one DV, factorial ANOVA for multiple factors, multivariate ANOVA (MANOVA) for multiple DVs, and repeated-measures ANOVA for multiple within-subject measurements.


## SPSS
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





## Exploratory and Confirmatory Factor Analysis
