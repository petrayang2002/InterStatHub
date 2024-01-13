# InterStatHub
InterStatHub: Bridging Statistical Tool Interoperability in Social and Biological Sciences
In this project, we aim to create a practical manual of achieving the interoperability between different statistical tools in the social and biological sciences. We understand that people are trained in different tools and have preferences for some, but we realize that when people come together to communicate over their statistical analysis in areas that are interdisciplinary in nature, a common understanding and usage of multiple statistical tools is necessary; however hard to achieve. We aim to make this process simpler. 

We will discuss STATA, SPSS, R, MATLAB, and G*Power for social sciences and neuroscience to start this process. Then, we will move onto languages such as Python and behavioral analysis tools such as BORIS and DeepLabCut. Current hubs for data sharing such as Neurodata Without Borders, DANDI, and the Center for Open Science will also be discussed in this section. Finally, you can find tools and packages developed for the most specific uses at the end of this project.


[background and gap]

Which software is used more or preferred? 
What is the function for each software or a group of softwares? 
Why is this function useful?

STATA and R

STATA is __________. R is ____________.
STATA to R: guides in links
STATA: econometrics
Limited R to STATA translation. R can use more datasets. STATA cannot use a lot of datasets. 

[how is STATA limited; Angie’s notebook with STATA codes]


SPSS and R

SPSS is____________.
SPSS and R share a lot of applications and are taught together/interchangeably in some undergraduate level courses. Although SPSS makes use of the “point-click” method, advanced analyses such as mediated moderation in SPSS cannot be conducted by the internal point-click procedures and would require external packages to be downloaded and relevant syntax to be written and run. Furthermore, these advanced analyses and syntaxes are simpler to create than R.

Both SPSS and R for scale/item reliability


Power analysis

G*Power (Faul et al., 2007, 2009) is a free-to-use software for power analysis. It can calculate different sample sizes and present relevant graphs and tables for each experimental analysis. The types of analysis compatible with G*Power include t tests, F tests, χ2 tests, z tests, and exact tests (correlation, linear multiple regression, proportion, proportions, and generic binomial test). Based on different input parameters, the types of power analysis include A priori, compromise, criterion, post hoc, and sensitivity, which gives different output parameters.

Power analysis can also be conducted in R for F tests, GLMs, t tests, and χ2 tests. A tutorial of conducting power analysis using linguistic empirical data can be found here (Schweinberger, 2022). In R, users need to download packages like pwr (Champely 2020) or lme4 (Green and MacLeod 2016a) for particular types of tests. 
Amy’s class: Z-test and binomial are also possible in R.


NVivo

NVivo is a software for qualitative data coding and analysis. For data collected by surveys, researchers can first store it in SPSS, conduct scale reliability tests, then transfer it to NVivo for coding and analysis. Qualitative data collected in other forms, such as field notes, interviews, web pages, and creative textual forms, is usually either directly entered into NVivo and analyzed or coded by hand in a document.


MATLAB

MATLAB is a platform and programming language for data analysis and development. Its capacities range from performing statistical analyses on readable data to designing apps. It is widely used in mathematics, neuroscience, and engineering. Its Live Editor allows group editing on a project, and enables codes to be written in sections with comments and figures. Combined with the GitHub repository and the Jupyter Notebook platform, data analysis pipelines can be generated and shared. Large datasets take longer to process, and there is a limit to that size regardless of the Cloud storage. 


Python

Python is a programming language for data engineering used in computer science and neuroscience. Mostly utilized for programming, it can be used to analyze data in a similar way as in MATLAB. An example of this similarity is demonstrated in Chandravadia et al. (2020).



[current HUBs for statistical tools and dataset sharing in different fields]

In response to the diverse data formats in the neuroscience field, Neurodata Without Borders: Neurophysiology 2.0 (NWB:N; Teeters et al., 2015; Rubel et al., 2019) is developed as a data standard of stimuli, imaging, neurophysiology, and behavioral data. Scientists are now developing processing pipelines for importing and exporting data from and to NWB:N.
Dandi datasets in the NWB format. 

Center for Open Science, OSF, Reproducibility Project: Psychology | Reproducibility Project: Cancer Biology

[how will our work be useful]

Researchers started their training with specific tools like Python, but with the development of more tools and platforms, they need to learn and teach these tools. Our work will help this learning and teaching process by offering straightforward translations between tools.

We are first creating novel translations between tools. We are also collecting and summarizing existing translations between tools. These translations occur on a case-by-case basis. Looking for them is time-consuming. Our work can offer straightforward translations in one hub. In addition, we are introducing relatively new platforms and projects that will be more useful for the field if more people hear about and use them.


[content page]
