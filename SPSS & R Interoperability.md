# 4 Statistical Analyses That Demonstrate the Interoperability between SPSS & R


## Analysis 1: t-Test

There are 3 types of t-tests: one-sample t-Test, independent samples t-Test, and paired/dependent samples t-Test.


1. One-sample t-Test
This t-Test is useful when a sample is tested against a population mean.
The population mean and the sample data are required.

2. Independent samples t-Test
This t-Test is useful when testing if two samples in the same population are similar.
The sample data for both samples is required.

   
3. Paired/dependent samples t-Test
This t-Test is useful when testing if there is a difference between two measurements in the same individual (within subject test).
The two measurements from the same individual are required.





### SPSS

In the toolbar, select Analyze > Compare Means > a specific t-test

![SPSS_t-Test](https://github.com/petrayang2002/InterStatHub/assets/155834271/315baa07-0bfb-4abb-9186-7614a0f5e1ea)




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

      t.test(Data$DV~Data$IV, var.equal=TRUE/FALSE, alternative = “two.sided”)

#var.equal is equal variance based on Levene's Test for equal variance
#The default setting of confidence level is 0.95. You can add `conf.level=0.99`
#after `alternative` to make it another value.
```
or `alternative = "less"` or `"more"`


   3. Paired/Dependent Samples t-Test: 
```
      t.test(Data$Variable2, Data$Variable1, paired=TRUE, alternative=“two.sided”)

#testing if there is a difference between two measurements in the same individual
#The default setting of confidence level is 0.95. You can add `conf.level=0.99`
#after `alternative` to make it another value.
```
or `alternative = "less"` or `"more"`




## Analysis 2: ANOVA and post hocs

There are 4 types of ANOVA: one-way ANOVA, factorial ANOVA, multivariate ANOVA (MANOVA), and repeated-measures ANOVA.


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




## Analysis 3: Regression and Correlation


## Analysis 4: Mediation


## Analysis 5: Moderation

Binary moderator


## Analysis 6: Exploratory and Confirmatory Factor Analysis
