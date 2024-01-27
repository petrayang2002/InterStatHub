# InterStatHub
*InterStatHub: Bridging Statistical Tool Interoperability in Social and Biological Sciences*

**Created by Tongtong Yang (Petra) @Petrayang2002 & Wanqi Zhu (Angie) @wanqi-zhu**

In this project, we aim to create a practical manual for achieving interoperability between different statistical tools in the social and biological sciences. We understand that people are trained in different tools and have preferences for some, but we realize that when people come together to communicate over their statistical analysis in areas that are interdisciplinary in nature, a common understanding and usage of multiple statistical tools is necessary; however hard to achieve. We aim to make this process simpler. 

We will discuss STATA, SPSS, R, MATLAB, and G*Power for social sciences and neuroscience to start this process. Then, we will move on to languages such as Python and behavioral analysis tools such as BORIS and DeepLabCut. Current hubs for data sharing such as Neurodata Without Borders, DANDI, and the Center for Open Science will also be discussed in this section. Finally, you can find tools and packages developed for the most specific uses at the end of this project.


## Background and Gap

Here we offer introductions to the statistical softwares we aim to include, and discuss how they are preferred/regarded useful in certain situations due to their functions.

### STATA and R

R and Stata are both powerful statistical software packages commonly used by researchers, statisticians, and data analysts for data manipulation, analysis, and visualization. However, they have some differences in terms of their origins, syntax, and capabilities.

R is an open-source programming language and it allows users to write their own functions and packages, while Stata is a commercial statistical software package developed by StataCorp, requiring the user to purchase a license. 

Stata's command-line syntax is indeed known for its simplicity and directness, which can be advantageous, especially for users who are new to statistical software. Stata allows users to abbreviate commands as long as the abbreviation is unambiguous. For example, you can use `sum` instead of `summarize`, and Stata will recognize it. R follows a function-based approach, where many operations are performed using functions rather than commands. While R's syntax may initially seem more complex compared to Stata, it provides users with powerful capabilities and a high level of customization. 

R offers a high degree of flexibility and power when it comes to data manipulation. In R, you can load multiple datasets into memory simultaneously and manipulate them as needed. You can use functions like `read.csv()` to import datasets into R, and assign each dataset to a different object in the R environment. R has a vast ecosystem of packages specifically designed for data manipulation tasks. For example, the [tidyverse](https://www.tidyverse.org/) is a [collection of R packages](https://www.tidyverse.org/packages) for data sciences. The grammar and data structures are shared among all packages, making it easier for users to learn and apply them across different tasks.

That said, Stata also offers a range of commands for data manipulation. However, Stata's command-based interface and syntax may require more manual steps for certain data manipulation tasks, especially when dealing with complex operations. Stata commands, by default, operate on the dataset that is currently loaded into memory. This could affect how users merge or transform datasets.


### SPSS and R

SPSS (Statistical Package for the Social Sciences) or IBM SPSS Statistics is a software for statistical analysis in social sciences and data in other fields. The user can perform analysis in a point-click fashion or by writing and running syntaxes. Syntaxes (in external packages) are often used by advanced analyses such as mediated moderation that the point-click method cannot cover. SPSS and R are taught together/interchangeably in some undergraduate-level courses.


### Power analysis

**G*Power** (Faul et al., 2007, 2009) is a free-to-use software for power analysis. It can calculate different sample sizes and present relevant graphs and tables for each experimental analysis. The types of analysis compatible with G*Power include t-tests, F tests, χ2 tests, z-tests, and exact tests (correlation, linear multiple regression, proportion, proportions, and generic binomial test). Based on different input parameters, the types of power analysis include A priori, compromise, criterion, post hoc, and sensitivity, which gives different output parameters.

Power analysis can also be conducted in R for F tests, GLMs, z tests, t-tests, χ2 tests, and binomial tests. A tutorial on conducting power analysis using linguistic empirical data can be found at https://ladal.edu.au/pwr.html (Schweinberger, 2022). In R, users need to download packages like pwr (Champely, 2020) or lme4 (Green and MacLeod, 2016a) for particular types of tests. 


### NVivo

NVivo is a software for qualitative data coding and analysis. For data collected by surveys, researchers can first store it in SPSS, conduct scale reliability tests, then transfer it to NVivo for coding and analysis. Qualitative data collected in other forms, such as field notes, interviews, web pages, and creative textual forms, is usually either directly entered into NVivo and analyzed or coded by hand in a document.


### MATLAB

MATLAB is a platform and programming language for data analysis and development. Its capacities range from performing statistical analyses on readable data to designing apps. It is widely used in mathematics, neuroscience, and engineering. Its Live Editor allows group editing on a project and enables codes to be written in sections with comments and figures. Combined with the GitHub repository and the Jupyter Notebook platform, data analysis pipelines can be generated and shared. Large datasets take longer to process, and there is a limit to that size regardless of the Cloud storage. 


### Python

Python is a programming language for data engineering used in computer science and neuroscience. Mostly utilized for programming, it can be used to analyze data in a similar way as in MATLAB.



## Why InterStatHub?

Researchers started their training with specific tools like Python, but with the development of more tools and platforms, they need to learn and teach these tools. Our work will help this learning and teaching process by offering straightforward translations between tools.

We are first creating novel translations between tools. We are also collecting and summarizing existing translations between tools. These translations occur on a case-by-case basis. Looking for them is time-consuming. Our work can offer straightforward translations in one hub. In addition, we are introducing relatively new platforms and projects that will be more useful for the field if more people hear about and use them.


## Background: Existing tools that engage interoperability between multiple statistical tools

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

5. Power Analysis in G*Power* or R

   e.g. F tests, z tests, binomial tests
   
6. MATLAB & Python + NWB:N


7. [The reticulate package for interoperability between Python and R](https://github.com/rstudio/reticulate)

8. [A R-STATA interface: use STATA commands in R](https://github.com/lbraglia/RStata)

9. [R and Stata Equivalencies by Chuck Lanfear](https://clanfear.github.io/Stata_R_Equivalency/docs/r_stata_commands.html)
This github page offers examples of wrangling data, modeling data, and plotting figures in STATA and R ways. Viewers can compare their syntaxes presented side-by-side.


10. R packages for data science
    
    [The tidyverse](https://www.tidyverse.org/) is a collection of R packages for data sciences. The grammar and data structures are shared among all packages. Tidyverse, apart from R packages themselves, also has a blog, [a learning center with resources](https://www.tidyverse.org/learn/) such as books, workshops, and teaching materials that include semester-long course materials.
    
    [Haven](https://github.com/tidyverse/haven) is one of the R packages in Tidyverse. It is useful for reading SPSS, STATA, and SAS files in RStudio. It achieves this goal by wrapping the [ReadStat](https://github.com/WizardMac/ReadStat) C library written by [Evan Miller](https://www.evanmiller.org/). 



## Directory of InterStatHub: Specific Interoperability between Statistical Tools
**[STATA & R Interoperability](https://github.com/petrayang2002/InterStatHub/blob/main/STATA%20%26%20R%20Interoperability)** by Wanqi Zhu_Angie

**[SPSS & R Interoperability](https://github.com/petrayang2002/InterStatHub/blob/main/SPSS%20%26%20R%20Interoperability)** by Tongtong Yang_Petra



## Bonus resources: current HUBs for dataset sharing in different fields

**Neuroscience**

In response to the diverse data formats in the neuroscience field, Neurodata Without Borders: Neurophysiology 2.0 ([NWB:N](https://www.nwb.org/); Teeters et al., 2015; Rubel et al., 2019) is developed as a data standard of stimuli, imaging, neurophysiology, and behavioral data. Scientists are now developing processing pipelines for importing and exporting data from and to NWB:N.

Dandi datasets in the NWB format. 

[The Rutishauser Laboratory at Cedars-Sinai](https://www.cedars-sinai.edu/research/labs/rutishauser.html) creates software packages for neural spike sorting, stimulus management, and importing neurophysiological data into MATLAB. In addition, the Rutishauser Lab has [published a dataset](https://www.nature.com/articles/s41597-020-0415-9) of behavioral and spiking in the NWB format and relevant MATLAB and Python pipelines for processing the data.


**Psychology, Cancer Biology**

Center for Open Science (OSF) is a hub where psychologists and cancer biologists can share their data and research materials under specific projects with brief information on the project design. In turn, scientists in these fields can read about these projects that might have not been published and access the data.
