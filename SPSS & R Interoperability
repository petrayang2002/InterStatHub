**5 Statistical Analyses That Demonstrate the Interoperability between SPSS & R**
by Tongtong Yang_Petra


*Analysis 1: t-Test*
There are three types of t-tests: one-sample t-Test, independent samples t-Test, and paired/dependent samples t-Test.

SPSS: In the toolbar, select Analyze > Compare Means > a specific t-test
![Screenshot of the SPSS t-Test page](https://github.com/petrayang2002/InterStatHub/blob/main/SPSS_t-Test.pdf)

R: 1) one-sample t-Test: 
      t.test(Data$Variable, mu = ##, alternative = “two.sided”)
or alternative = "less" or "more"

   2) independent samples t-Test: 
      leveneTest(Data$DV~Data$IV)
      t.test(Data$DV~Data$IV, var.equal=TRUE/FALSE, alternative = “two.sided”)
or alternative = "less" or "more"

   3) Paired/Dependent Samples t-Test:
      t.test(Data$Variable2, Data$Variable1, paired=TRUE, alternative=“two.sided”)
or alternative = "less" or "more"

