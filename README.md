# JobXHealth_Analysis

# Overview of the analysis:
This project aims to assess the reasons for leaving the job and whether they are related to different types of health characteristics.
Our initial objective was to study the effects on the health of people affected by the layoffs that have occurred in the most different industries lately, especially in IT, but due to the limitation in the researched databases, it was necessary to change the initial idea and in this way we will work with all the reasons for leaving the job.



## Description of the data:
To carry out this project, we used tables available on the Statistics Canada website.
The tables used are:
- Reason for leaving job during previous year (https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1410012601)
-colar tabela com os dados brutos
- Health characteristics (https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1310009601)
-colar tabela com os dados brutos
In the images below we present the data in its raw form as well as identify which cleanings are necessary for future modeling.
Colar dicionario  tabelas

To create our future models, we merge the two previous tables by Year, Province, Sex and Age_group, reaching the final result in the table below.
colar tabela final

As previously mentioned, because we have a limitation of the data found, our analysis will be based on the years between 2017 and 2021 (5 years).
Our final dataframe:
- colar tabela final


## Questions to answer with the project:
Based on the data presented above, the questions we intend to answer in this project are:
-  What are the main reasons why employees tend to leave their current job?
- Is there a relationship between reasons for leaving employment and health characteristics? If such relationships exist, what are the major correlations?
- Do province, gender, and age group interfere with any specific health characteristics?