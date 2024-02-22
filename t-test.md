# t-Test using SPSS, R, and STATA

There are 4 types of t-tests assuming normal distribution: one-sample t-Test, independent samples t-Test, paired/dependent samples t-Test, and two indepdent sample unequal variance t-test.


1. One-sample t-Test
This t-Test is useful when a sample is tested against a population mean.
The population mean and the sample data are required.

2. Independent samples t-Test
This t-Test is useful when testing if two samples in the same population are similar.
The sample data for both samples is required.

   
3. Paired/dependent samples t-Test
This t-Test is useful when testing if there is a difference between two measurements in the same individual (within subject test).
The two measurements from the same individual are required.

4. Two independent sample unequal variance or Welch’s Test
This t-test is useful when comparing the means of two populations while not assuming equal variance between populations.
The means of the two populations are required.




# SPSS

In the toolbar, select Analyze > Compare Means > a specific t-test

![SPSS_t-Test](https://github.com/petrayang2002/InterStatHub/assets/155834271/315baa07-0bfb-4abb-9186-7614a0f5e1ea)

For Welch's Test, select Analyze > Compare Means > One-Way ANOVA, then select Options > check Homogeneity of variance test and the Welch.





# Stata 

## Meau				
ttest Statistics > Summaries, tables, and tests > Classical tests of hypotheses > t test (mean-comparison test)		

## Syntax 		

   1. one-sample t-Test: 
```
ttest varname == # if in , level(#)
#level(#) – specifies the confidence level, as a percentage, for confidence intervals. The default is level(95) or as set by set level
#Test that the mean of varname is # at the #% confidence level
```

_Immediate form:_ 

```
ttesti #obs #mean #sd #val , level(#)
```

   2. independent samples t-Test:
```
ttest varname, by(groupvar) level(#)
#groupvar is a categorical variable

ttest varname1 == varname2, level(#) unpaired
# to calculate the differences between varname1 and varname2
```

_Immediate form:_ 

```
ttesti #obs1 #mean1 #sd1 #obs2 #mean2 #sd2 
```

   3. Paired/Dependent Samples t-Test: 
```
ttest varname1 == varname2, level(#)
```


   4. Two independent sample unequal variance or Welch’s Test:
```
ttest varname, by(groupvar) welch level(#)
ttest varname1 == varname2, unpaired unequal level(#)
##unequal/welch – welch and unequal can be used interchangeably, meaning that data has unequal variances 
```


# R

   1. one-sample t-Test: 
```
      t.test(MyData$Variable, mu = ##, alternative = “two.sided”, “less”, “greater”)

#a sample is tested against a population mean
#The default setting of confidence level is 0.95. You can add `conf.level=0.99`
#after `alternative` to make it another value.
```



   2. independent samples t-Test:
```
      leveneTest(MyData$DV~MyData$IV)

#leveneTest() from the {car} package is Levene's Test for equal variance of the two samples
#from the same population, DV is changed by IV

      t.test(MyData$DV~MyData$IV, var.equal=TRUE/FALSE, alternative = “two.sided”, “less”, “greater”)

#var.equal is equal variance based on Levene's Test for equal variance
#The default setting of confidence level is 0.95. You can add `conf.level=0.99`
#after `alternative` to make it another value.
```


   3. Paired/Dependent Samples t-Test: 
```
      t.test(MyData$Variable2, MyData$Variable1, paired=TRUE, alternative=“two.sided”, “less”, “greater”)

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

