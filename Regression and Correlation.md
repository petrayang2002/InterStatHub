# Regression and Correlation

1. A *correlation* test tells if a continuous variable is associated with another continuous variable.
Pearson's r (Cohen, 1998) can indicate the strength and the direction (positive or negative) of this association (or no association). 

The correlation is weak if r is between -.10 to -.30 (negative) or .10 to .30 (positive), moderate if r is between  -.30 to -.50 or .30 to .50, or strong if r is between -.50 to -1.00 or .50 to 1.00.



2. *Linear regression* analysis can help us understand if a continuous variable can predict another continuous variable, and if this prediction is can be shown in a straight line, y = mx + b.
The results of the regression cannot indicate any casual relationships between these variables.
Another kind of regression is the non-linear regression analysis, in which the two continous variables are related in a curved relationship.


It is important to omit missing data cases in the dataset. Otherwise, R won't run the correlation or linear regression analyses. 

Omission can happen in either pairwise or listwise. Pairwise deletion (available-case analysis) omits pairs of data with avaiable values. Listwise deletion (complete-case analysis) omits all data for cases if any value is missing.


## R
1. Correlation
```
cor(MyData$Variable1, MyData$Variable2)

cor(MyData, use="complete.obs") #listwise (by default) 
cor(MyData, use="pairwise.complete.obs") #pairwise

# or

cor.test(MyData$Variable1, MyData$Variable2)
```




2. Regression
```
model <- lm(DV ~ IV, data = MyData) #Linear regression 
model <- glm(DV ~ IV, data = MyData, family = binomial) #Logistic regression 


  summary(model)

# The results will show F value, df, p value, and multiple R-squared (indicating accuracy).

```




## SPSS


Both correlation and linear regression can be run by the Bivariate Pearson correlation in SPSS.


1) The point-click method

**Analyze > Correlate > Bivariate > Add variabls > Pearson > Two-tailed or One-tailed**
  **> Flag significant correlations > Options > Exclude cases pairwise or Exclude cases listwise**



2) The syntax method

```   
CORRELATIONS
   /VARIABLES=Weight Height
   /PRINT=TWOTAIL NOSIG
   /MISSING=PAIRWISE
```

  The omission method here is pairwise.




  Another useful link explaining [bivariate Pearson correlation in SPSS](https://libguides.library.kent.edu/SPSS/PearsonCorr)




## STATA

List-wise deletion of data: 

```
cor Variable1 Variable2 Variable3 # put all the variables as you wanted to see
cor Variable1 Variable2 Variable3, covariance # to show covariance
```

Pair-wise deletion of data: 
```
pwcorr Variable1 Variable2 Variable3 
pwcorr Variable1 Variable2 Variable3, sig # to show significance level of each correlation coefficient
pwcorr Variable1 Variable2 Variable3, sig star(#)# to show significance level, and star correlation coefficients significant at the # level
```

