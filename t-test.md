


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

