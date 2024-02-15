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

### One-sample t test 
```
ttest varname == # if in , level(#)
```

_Immediate form:_ 

```
ttesti #obs #mean #sd #val , level(#) 
```

### Two-sample t test using groups 
```
ttest varname, by(groupvar) [options] 
```

_Immediate form:_ 

```
ttesti #obs1 #mean1 #sd1 #obs2 #mean2 #sd2 , [options] 
```

### Two-sample t test using variables 
```
ttest varname1 == varname2, unpaired unequal welch level(#) 
```
  
### Paired t test 

```
ttest varname1 == varname2, level(#) 
```

[options]: 

**level(#)** – specifies the confidence level, as a percentage, for confidence intervals. The default is level(95) or as set by set lev

**unequal/welch** – can be used interchangeably, meaning that data has unequal variances 

**reverse** – reverse group order for mean difference computation (cannot be used in immediate forms)

# R
