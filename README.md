# Determining whether various CO2 pollutants contribute to the rise of heat temperatures in the United States
Using complex data to help uncover the leading causes inn the rise of heat temperatures by various CO2 pollutants in the United States

## Topic
We are hoping to explore the relationship between CO2, the climate, and other factors (nitrous oxide per capita, GDP, population, etc.) to predict future CO2 levels/temperatures and consequently understand the how these things will affect our habitat in the years to come. We chose this subject as climate change is an unavoidable part of life and being able to understand the ways in which this phenomenon will unfold will be important when planning for the future. With this exploration we plan to understand how CO2 emissions and other related factors will affect our habitat.

## Sources of Data (may be subject to change):
- CO2 and Greenhouse Gas Emissions Dataset:
  - CO2 and Greenhouse Gas Emissions dataset is a collection of key metrics maintained by Our World in Data. It is updated regularly and includes data on CO2 emissions (annual, per capita, cumulative and consumption-based), other greenhouse gases, energy mix, and other relevant metrics. 
  - https://github.com/owid/co2-data

- California Avg Temperatures : NOAA
  - Information on average temperatures in California collected by the National Oceanic and Atmospheric Administration. The gathered information has temperature data for each month from the year 1990 to 2021.

## Communication Protocols (may be subject to change):
- Line graph to convey CO2 emissions over time
- Heat map to convey average temperatures over time


## Database Preparation

Once we had the datasets we wanted to use, we now could endeavor to join them together for the machine learning model. Before joining them with SQL, we had to reframe the “Global Land Temperatures” dataset. The “Global Land Temperatures” dataset recorded its information by year and month (ie. 199002, 199003,...) and by state in the USA; the “CO2 and Greenhouse Gas Emissions” dataset recorded their information by year and by country. This discrepancy prevented us from simply joining the two tables via SQL. The decision was made to first: convert the metric of time from "year and month" to simply "year" and to second: convert the data from being recorded by state to being recorded simply by country; both steps had to be done to the "Global Land Temperatures" dataset. The code for this step can be found in the repository and the following are images from this process: <br/>

![image](https://user-images.githubusercontent.com/72320203/160339892-1461afb0-f662-42a3-9faf-aec5734e7807.png) 
![image](https://user-images.githubusercontent.com/72320203/160340006-fff351e2-92a4-4ee5-85a8-75091608b112.png)

This left us with two datasets that we could now join through SQL. The two files were imported into PGAdmin and joined with SQL. "Global Land "Temperatures" and "CO2 and Greenhouse Gas Emissions" were joined on the shared column of "year" and then saved into a file. The following is the code for that query: <br/>

<img width="497" alt="select" src="https://user-images.githubusercontent.com/72320203/160341352-087bc044-4d4c-4bc8-b509-d1c49fae6394.PNG">

Now, we had a dataset that could be input into our machine learning model.









