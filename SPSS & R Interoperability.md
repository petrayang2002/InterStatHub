**5 Statistical Analyses That Demonstrate the Interoperability between SPSS & R**
by Tongtong Yang_Petra


*Analysis 1: t-Test*
There are three types of t-tests: one-sample t-Test, independent samples t-Test, and paired/dependent samples t-Test.

1. One-sample t-Test
This t-Test is useful when a sample is tested against a population mean.
The population mean and the sample data are required.

   
2. Independent samples t-Test
This t-Test is useful when testing if two samples in the same population are similar.
The sample data for both samples is required.

   
3. Paired/dependent samples t-Test
This t-Test is useful when testing if there is a difference between two measurements in the same individual (within subject test).
The two measurements from the same individual are required.





SPSS: In the toolbar, select Analyze > Compare Means > a specific t-test
![SPSS_t-Test](https://github.com/petrayang2002/InterStatHub/assets/155834271/315baa07-0bfb-4abb-9186-7614a0f5e1ea)



R: 1) one-sample t-Test: 
```
      t.test(Data$Variable, mu = ##, alternative = “two.sided”)

#a sample is tested against a population mean
#The default setting of confidence level is 0.95. You can add `conf.level=0.99` after `alternative` to make it another value.
```
or `alternative = "less"` or `"more"`


   2) independent samples t-Test:
```
      leveneTest(Data$DV~Data$IV)

#leveneTest() from the {car} package is Levene's Test for equal variance of the two samples from the same population, DV is changed by IV

      t.test(Data$DV~Data$IV, var.equal=TRUE/FALSE, alternative = “two.sided”)

#var.equal is equal variance based on Levene's Test for equal variance
#The default setting of confidence level is 0.95. You can add `conf.level=0.99` after `alternative` to make it another value.
```
or `alternative = "less"` or `"more"`


   3) Paired/Dependent Samples t-Test: 
```
      t.test(Data$Variable2, Data$Variable1, paired=TRUE, alternative=“two.sided”)

#testing if there is a difference between two measurements in the same individual
#The default setting of confidence level is 0.95. You can add `conf.level=0.99` after `alternative` to make it another value.
```
or `alternative = "less"` or `"more"`


