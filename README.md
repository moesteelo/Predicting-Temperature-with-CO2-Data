# Fighting-WildFire-With-Data
Using complex data to help uncover the leading causes of wild fire and how to use Machine Learning data to prevent the next wild fire!

## Topic
We are hoping to explore the relationship between CO2 and climate to predict future CO2 levels/temperatures and consequently understand the how these things will affect our habitat in the years to come. We chose this subject as climate change is an unavoidable part of life and being able to understand the ways in which this phenomenon will unfold will be important when planning for the future. With this exploration we plan to understand how climate and  CO2 emissions affect our habitat. 

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

Once we had the datasets we wanted to use, we now could endeavor to join them together for the machine learning model. Before joining them with SQL, we had to reframe the “Global Land Temperatures” dataset. The “Global Land Temperatures” dataset recorded its information by year and month (ie. 199002, 199003,...) and by state in the USA; the “C02 and Greenhouse Gas Emissions” dataset recorded their information by year and by country. This discrepancy prevented us from simply joining the two tables via SQL. The decision was made first: to convert the metric of time from "year and month" to simply "year" and second: to convert the data from being recorded by state to being recorded simply by country. This code can be found in the github and the following are images from this process: <br/>

![image](https://user-images.githubusercontent.com/72320203/160339892-1461afb0-f662-42a3-9faf-aec5734e7807.png) 
![image](https://user-images.githubusercontent.com/72320203/160340006-fff351e2-92a4-4ee5-85a8-75091608b112.png)




[insert picture of the jupyter notebook here]

The decision was made to convert the metric of time from "year and month" to simply "year" and a

[we have to convert states, to a country, and months into their respective years so we can join for the machine]


Now that we have our datasets, we then joined them with SQL. Before doing so, we had to clean up the temperature data from Berkeley Earth so both datasets shared the same metric of time - in this case that metric was by year. The Berkeley Earth temperature dataset recorded data by every month of a specified year (ie.199002 = February 1990) while the “C02 and Greenhouse Gas Emissions” dataset



 <“Updated_GlobalLandTemperaturesByState.csv”> so the data could be joined with the data taken from < “Updated_USA-co2-data.csv”>. The former tracked their data by 

