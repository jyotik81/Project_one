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



# Results:

In the file LogisticRegression.ipynb we create a correlation matrix using as base a table with the indicators transformed into columns to analyze the correlation between the variables.
From the image below we can see that none of the job variables (J_L_R...) has a strong correlation with the health variables.  

![correlation](https://user-images.githubusercontent.com/111664141/216178074-09ab033b-43ef-4e29-a0a0-8b9d1fd4fad2.JPG)

In this other heatmap below containing the correlation percentages we can confirm that the health variables do not present any correlation above 0.80 with the job variables.  

![correlationper](https://user-images.githubusercontent.com/111664141/216178118-81b3d49c-adeb-4ab7-a963-47360cf2161a.JPG)

## Unsupervised Model
In the file Final_Project_Model.ipynb we first create an unsupervised model because we don't have any target variables.  
We use PCA to reduce dimension to 3 principal components. With these components we create an elbow curve to find the best value for K.   

![elbowcurve](https://user-images.githubusercontent.com/111664141/216178188-c2bf1dde-af52-453d-bdfe-3c96c69d8e1b.JPG)

For the creation of the K-Means model we chose K=5 to create 5 predicted clustering classes. Below we can see the 3D-Scatter with the PCA data and the clusters.  

![clustergraph](https://user-images.githubusercontent.com/111664141/216178240-56c1b5ef-c78e-42db-8296-71262a41d6c8.JPG)

With these classes, we create some hvplot scatter plots to evaluate if there is any bias between the classes created and the main variables we would like to evaluate.

### Analysys Indicators_Health x J_L_R_Permanent_layoff  
![healthxPerman](https://user-images.githubusercontent.com/111664141/216178406-5db68b91-d978-4013-bbf5-903260cb351c.JPG)

### Analysys Province x J_L_R_Permanent_layoff
![ProvincexPerman](https://user-images.githubusercontent.com/111664141/216178450-7573f858-ac08-45ec-8446-36a800cc8e80.JPG)
![ProvinceData](https://user-images.githubusercontent.com/111664141/216178523-446c69a8-e6ba-4d52-a3db-0c4e2dd55abf.JPG)

### Analysys Sex x J_L_R_Permanent_layoff
![sexxPeman](https://user-images.githubusercontent.com/111664141/216178562-1c545369-431b-455a-a0be-d604b083d882.JPG)
![sexData](https://user-images.githubusercontent.com/111664141/216178576-8e8501dd-be44-44d7-8f58-e0d1da5e8ccf.JPG)  



## Supervised Model
#### Logistic Regression
After creating the variable Class as a result of the predicted clustering we use it as a target variable to analyze if our model has a good accuracy in classifying classes.  

Confusion Matrix:  
![LogisticRegressio_confusion](https://user-images.githubusercontent.com/111664141/216178659-3fb5d027-94b7-490f-b291-89df796a41f6.JPG)  
![LR_accuracy](https://user-images.githubusercontent.com/111664141/216178673-afc15145-201a-4aa4-a7ef-df78d6822246.JPG)  
Classification Report:  
![LR_Class_report](https://user-images.githubusercontent.com/111664141/216178685-a0d418db-e3c0-4c78-9435-436dbcff020f.JPG)  
![Lr_confusion](https://user-images.githubusercontent.com/111664141/216178696-987e5b7b-f64f-4475-ad00-bf8d5bc1310b.JPG)


### Random Forest Classifier
As the logistic regression model did not show a good result, we modeled the data using the Random Forest Classifier model.  
![rf_accuracy](https://user-images.githubusercontent.com/111664141/216178761-408fffd7-5d6c-4883-ac95-d91295c5c100.JPG)  
Confusion Matrix:  
![rf_confusion](https://user-images.githubusercontent.com/111664141/216178782-96afddb1-3f61-47b9-bf0a-d0d906f21801.JPG)  
Classification Report:  
![rf_class_report](https://user-images.githubusercontent.com/111664141/216178789-e92d482b-aa71-4a40-8d58-f55d15d468d0.JPG)

As we can see in the images above, this model presented a very good adherence to the clustering classification of the data.

Below we list the variables with the greatest weight for the model in order of importance.
![variables](https://user-images.githubusercontent.com/111664141/216178850-6a95ede3-30fa-4368-9354-08e3f01e17dd.JPG)

### Answer to the 3 questions:

1)After a research study and accumulation of data, we came to a realisation that most people leave their job for various reasons, often not 
as serious or mandatory due to their health. With the data presented, we can that se correlation matrix shows that the primary reasons revolve around
the younger age group returning to school, when it comes to retirement mostly, unsatisfaction with the work environment which leads to disatisfaction
and in some cases permanent lay offs.

2)To a certain degree, yes there is a relation among many other however health is not the main factor for employees leaving their jobs.
As seen is the correlatio matrix and the heat map, many indicators showed revolved around different health factors that could leave to someone 
leaving their current job but comparing it to the other factors given, we can see that the correlation does not go above 0.80.
3) What are the main factors for employees leaving their jobs?
After gathering, organising, cleaning, and evaluating the data, our team realised that retirement, returning to school for students, and workplace
dissatisfaction are the main reasons why people leave their jobs. Now when it comes to some employees, our data suggest that many have pulmonary
disease, asthma and diabetes. These are main factors employees leave due to their health.

