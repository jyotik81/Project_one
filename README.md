# Study of the relation between Reasons for Leaving a Job and Health Characteristics

# Overview of the analysis:
This project aims to assess the reasons for leaving the job and whether they are related to different types of health characteristics.  
Our initial objective was to study the effects on the health of people affected by the layoffs that have occurred in the most different industries lately, especially in IT, but due to the limitation in the researched databases, it was necessary to change the initial idea and in this way we will work with all the reasons for leaving the job.

## Description of the data:
To carry out this project, we used tables available on the Statistics Canada website.  
The tables used are:  

- Reason for leaving job during previous year (https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1410012601)  

![job_df](https://user-images.githubusercontent.com/111664141/214451791-b6f69b54-a5f9-406f-aecf-9a284cabcf84.JPG)

- Health characteristics (https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1310009601)   

![heath_df](https://user-images.githubusercontent.com/111664141/214452085-fd692e54-2bdd-4266-99e1-042d7af5e303.JPG)

In the images below we present the data in its raw form as well as identify which cleanings are necessary for future modeling.  

![job_dic](https://user-images.githubusercontent.com/111664141/214452510-8ff06096-6adc-4b37-a14a-6be5d336e51d.JPG)
![health_dic](https://user-images.githubusercontent.com/111664141/214452524-f1b3eca4-a70e-429d-9e1c-83b4554490cd.JPG)


To create our future models, we merge the two previous tables by Year, Province, Sex and Age_group, reaching the final result in the table below.  

![final_dic](https://user-images.githubusercontent.com/111664141/214452552-19dec640-385c-4848-b74f-f9cfd1594b43.JPG)


As previously mentioned, because we have a limitation of the data found, our analysis will be based on the years between 2017 and 2021 (5 years).  
Our final dataframe is:  

![healthXjob_df](https://user-images.githubusercontent.com/111664141/214452574-22411f82-ecf0-4fe5-acfe-9096cdc1e01e.JPG)


## Questions to answer with the project:
Based on the data presented above, the questions we intend to answer in this project are:
-  What are the main reasons why employees tend to leave their current job?
- Is there any relation between reasons for leaving employment and health characteristics? If such relation exist, what are the major correlations?
- Do province, gender, and age group interfere with any specific health characteristics?
