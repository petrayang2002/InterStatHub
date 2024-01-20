# InterStatHub
*InterStatHub: Bridging Statistical Tool Interoperability in Social and Biological Sciences*

**Created by Tongtong Yang (Petra) @Petrayang2002 & Wanqi Zhu (Angie) @wanqi-zhu**

In this project, we aim to create a practical manual of achieving the interoperability between different statistical tools in the social and biological sciences. We understand that people are trained in different tools and have preferences for some, but we realize that when people come together to communicate over their statistical analysis in areas that are interdisciplinary in nature, a common understanding and usage of multiple statistical tools is necessary; however hard to achieve. We aim to make this process simpler. 

We will discuss STATA, SPSS, R, MATLAB, and G*Power for social sciences and neuroscience to start this process. Then, we will move onto languages such as Python and behavioral analysis tools such as BORIS and DeepLabCut. Current hubs for data sharing such as Neurodata Without Borders, DANDI, and the Center for Open Science will also be discussed in this section. Finally, you can find tools and packages developed for the most specific uses at the end of this project.


## Background and Gap

Which software is used more or preferred? 
What is the function for each software or a group of softwares? 
Why is this function useful?

**STATA and R**

STATA is __________. R is ____________.
STATA to R: guides in links
STATA: econometrics
Limited R to STATA translation. R can use more datasets. STATA cannot use a lot of datasets. 

[how is STATA limited; Angie’s notebook with STATA codes]


**SPSS and R**

SPSS (Statistical Package for the Social Sciences) or IBM SPSS Statistics is a software for statistical analysis in social sciences and data in other fields. The user can perform analysis in a point-click fashion or by writing and running syntaxes. Syntaxes (in external packages) are often used by advanced analyses such as mediated moderation that the point-click method cannot cover. SPSS and R are taught together/interchangeably in some undergraduate level courses.


**Power analysis**

**G*Power** (Faul et al., 2007, 2009) is a free-to-use software for power analysis. It can calculate different sample sizes and present relevant graphs and tables for each experimental analysis. The types of analysis compatible with G*Power include t tests, F tests, χ2 tests, z tests, and exact tests (correlation, linear multiple regression, proportion, proportions, and generic binomial test). Based on different input parameters, the types of power analysis include A priori, compromise, criterion, post hoc, and sensitivity, which gives different output parameters.

Power analysis can also be conducted in R for F tests, GLMs, z tests, t tests, χ2 tests, and binomial tests. A tutorial of conducting power analysis using linguistic empirical data can be found at https://ladal.edu.au/pwr.html (Schweinberger, 2022). In R, users need to download packages like pwr (Champely 2020) or lme4 (Green and MacLeod 2016a) for particular types of tests. 


**NVivo**

NVivo is a software for qualitative data coding and analysis. For data collected by surveys, researchers can first store it in SPSS, conduct scale reliability tests, then transfer it to NVivo for coding and analysis. Qualitative data collected in other forms, such as field notes, interviews, web pages, and creative textual forms, is usually either directly entered into NVivo and analyzed or coded by hand in a document.


**MATLAB**

MATLAB is a platform and programming language for data analysis and development. Its capacities range from performing statistical analyses on readable data to designing apps. It is widely used in mathematics, neuroscience, and engineering. Its Live Editor allows group editing on a project, and enables codes to be written in sections with comments and figures. Combined with the GitHub repository and the Jupyter Notebook platform, data analysis pipelines can be generated and shared. Large datasets take longer to process, and there is a limit to that size regardless of the Cloud storage. 


**Python**

Python is a programming language for data engineering used in computer science and neuroscience. Mostly utilized for programming, it can be used to analyze data in a similar way as in MATLAB.



## Current HUBs for Statistical Tools and Dataset Sharing in Different Fields

In response to the diverse data formats in the neuroscience field, Neurodata Without Borders: Neurophysiology 2.0 (NWB:N; Teeters et al., 2015; Rubel et al., 2019) is developed as a data standard of stimuli, imaging, neurophysiology, and behavioral data. Scientists are now developing processing pipelines for importing and exporting data from and to NWB:N.
Dandi datasets in the NWB format. 

Center for Open Science, OSF, Reproducibility Project: Psychology | Reproducibility Project: Cancer Biology

## How Will Our Work Be Useful

Researchers started their training with specific tools like Python, but with the development of more tools and platforms, they need to learn and teach these tools. Our work will help this learning and teaching process by offering straightforward translations between tools.

We are first creating novel translations between tools. We are also collecting and summarizing existing translations between tools. These translations occur on a case-by-case basis. Looking for them is time-consuming. Our work can offer straightforward translations in one hub. In addition, we are introducing relatively new platforms and projects that will be more useful for the field if more people hear about and use them.

## Sample analysis using multiple statistical tools

1. *[Data Visualization: A practical Introduction](https://socviz.co/)* by Kieran Healy
R
Python

2. *[A User’s Guide To Network Analysis](https://nwcommands.wordpress.com/)* by Douglas A. Luke
R to STATA

3. *[Memorandum: Stata to R::dplyr](https://github.com/takakishi/stata-to-dplyr)* Written by Takaaki Kishida
STATA to R

4. SPSS to R, R to SPSS + OSF
   e.g. ANOVA
   e.g. scale/item reliability
   e.g. moderated mediation

6. Power Analysis in G*Power* or R
   e.g. F tests, z tests, binomial tests
   
8. MATLAB & Python + NWB:N
   e.g. [Chandravadia et al., 2020](https://www.nature.com/articles/s41597-020-0415-9)
   A receiver operating characteristic (ROC) curve is used to form a clear cut-off value in order to test a dichotomous classification.
