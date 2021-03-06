# CO2 and other Factors Influencing Temperature
 
## Overview
We are hoping to explore the relationship between CO2, the climate, and other factors (nitrous oxide per capita, GDP, population, etc.) to see whether or not these factors have an influence on the rising temperatures. We selected this question as we hoped to further understand global warming as climate change is becoming an unavoidable part of life. With this exploration, we plan to understand how CO2 emissions and other related factors will affect our habitat.

## Question We Would like to answer:
- Do the chosen factors for the exploration contribute to the rise in temperature in the US?

## Sources of Data:
- [Kaggle: Earth Surface Temperature Data](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)
- [Github: CO2 Emissions](https://github.com/owid/co2-data)
- [Global Land Temperatures](http://berkeleyearth.org/data-visualization/)


## Data Preprocessing
#### Temperature Data
To narrow our focus for our analysis and machine learning model, we filtered the data to only include the US. Next we extracted the year and month from the date column. This cleaned dataset will help us look at yearly temperature data in the US.

Initial dataset:

![initial-temp](https://github.com/moesteelo/Predict-CO2-With-Data/blob/judyw/img/temp-cleaning-img/initial.PNG)

Cleaned dataset:

![clean-temp](https://github.com/moesteelo/Predict-CO2-With-Data/blob/judyw/img/temp-cleaning-img/clean.PNG)

#### CO2 Emissions Data
To narrow our focus for our analysis and machine learning model, we filtered the data to only include the US. Next we dropped all columns with more than 90% NaN values. To further narrow our focus, we dropped all columns with non-beneficial data. This brought us down from 25191 rows × 60 columns to 221 rows × 22 columns

Initial dataset:
![initial-co2](https://github.com/moesteelo/Predict-CO2-With-Data/blob/judyw/img/co2-cleaning-img/initial.PNG)

Cleaned dataset:
![clean-co2](https://github.com/moesteelo/Predict-CO2-With-Data/blob/judyw/img/co2-cleaning-img/clean.PNG)

## Database Preparation

Once we had the datasets we wanted to use, we could then endeavor to join them together for the machine learning model. Before joining them with SQL, we had to reframe the “Global Land Temperatures” dataset. The “Global Land Temperatures” dataset recorded its information by year and month (ie. 199002, 199003,...) and by state in the USA; the “CO2 and Greenhouse Gas Emissions” dataset recorded their information by year and by country. This discrepancy prevented us from simply joining the two tables via SQL. The decision was made to first: convert the metric of time from "year and month" to simply "year" and to second: convert the data from being recorded by state to being recorded simply by country; both steps had to be done to the "Global Land Temperatures" dataset. The code for this step can be found in the repository and the following are images from this process: <br/>

![image](https://user-images.githubusercontent.com/72320203/160339892-1461afb0-f662-42a3-9faf-aec5734e7807.png) 
![image](https://user-images.githubusercontent.com/72320203/160340006-fff351e2-92a4-4ee5-85a8-75091608b112.png)

This left us with two datasets that we could now join through SQL. The following is an image of the ERD:<br/>

<img src= "img/erd.PNG" >

The two files were imported into PGAdmin and joined with SQL. "Global Land "Temperatures" and "CO2 and Greenhouse Gas Emissions" were joined on the shared column of "year" and then saved into a file. The following is the code for that query: <br/>

<img width="497" alt="select" src="https://user-images.githubusercontent.com/72320203/160341352-087bc044-4d4c-4bc8-b509-d1c49fae6394.PNG">

Now, we had a dataset that could be input into our machine learning model.

## Machine Learning Model

During the Machine Learning process we used 4 Supervised Machine Learning processes to evaluate our overall data and to determine which process best suits our data.

### **Multiple Linear Regression Model**

Multiple linear regression designed to find a relationship between a single independent and dependent variable. The adjusted R score of our multiple linear regression model is 37.76% indicating the machine learning model work well. However, there are many more factors than CO2 influence the Average temperature increase

<img src= "img/Multiple_Linear_Regression.png">

### **Confusion Matrix for Random Forest Classification**

The classifier confusion matrix, overall accuracy with 63%, RandomForestClassifier algorithm is better model to predict the average temperature. 

<img src= "img/Confusion_matrix.png" >

### **Logistic Regression Model**

In the process of using the Logistic Regression Model the overall result of the accuracy score was 27%. This did not meet our minimum 70% accuracy score to determine whether various CO2 factors contributes to the rise in temperature.

<img src= "img/Logistic Rgression Model.png" >

### **OLS Regression Results**

Based on our OLS Regression Results our R-squared predicted that there is a 40% Linear Model influence in various CO2 factors contributing to the rise in temperatures.

<img src= "img/OLS Regression Results.png" >

### **Random Forest Classifier Results**

Based on our Random Forest classification algorithm we used to help our prediction results to see whether factors of CO2 contribute to the increase in temperatures.  One of the biggest advantages of random forest is its versatility. It can be used for both regression and classification tasks. Based on our data the Random Forest model generated a 63% accuracy score. This score revealed that our data may have a slight positive influence to the rise in temperatures in the United States.

<img src= "img/Random Forest Classifier.png" >


## Dashboard Tableau
We used Tableau to create and host our dashboard. The file is also stored in the repository. <br/>
[Tableau Dashboard](https://public.tableau.com/app/profile/jun6899/viz/ChangesinAverageUSTemperaturesCO2andCompany/Dashboard1)

## Visualizing the Data

Below shows the United States 12 month heat forecast. It also displays the Average Temperature increasing from 1750 to 2013.

<img src= "img/United States 12 Month Temp.png"  >
<img src= "img/AVG Temperature display by years ML process.png"  >

## Conclusion Results

Seeing the upward trends CO2 and greenhouse gas emissions, population, and temperature, it’s possible that CO2 and/or a combination of these factors has a positive influence on temperature. Now that we have created this product, this can now be the foundation for future data exploration; simply add features that one wants to explore to the input dataset for the machine and then run it.

## Recommendation for future analysis

- Consider additional features in the analysis ie. country, annual military spending by country, other potential pollutants, etc.
- Explore more models for better fit
- More granular breakdown of what data sets should be examined 
- Find more recent data exploring Avg Temperature and CO2 data 


## CO2 Effect on Temperature Google Slide

[Google Slides](https://docs.google.com/presentation/d/1ufzwVPUsOWHUAslN3fsjy4kuGSDC7MxnokdIxQLYEQk/edit?usp=sharing)
