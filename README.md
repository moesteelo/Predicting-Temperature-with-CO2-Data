# Predicting Temperature Using CO2 Data

## Topic
We are hoping to predict temperature from levels of CO2. Changes in temperature cause frequent severe weather events, droughts, heat waves, rising sea levels. It's important to understand how temperature and the climate because it can help us prepare for the future. With this exploration we plan to understand how climate and CO2 emissions affect our habitat.

## Question We Would Like to Answer:
- Can we predict temperature using data of CO2 emissions.

## Sources of Data:
- [Kaggle: Earth Surface Temperature Data](https://www.kaggle.com/datasets/berkeleyearth/climate-change-earth-surface-temperature-data)
- [Github: CO2 Emissions](https://github.com/owid/co2-data)

## Preliminary Data Preprocessing
- Temperature Data
    - A year column was added.
    - The data was filtered to only include US.
    - The temperature was averaged per year.
    - The "dt" and "state" columns were removed.

- CO2 Emissions Data
    - Columns with more than 90% NaN values were dropped.
    - The data was filtered to only include US.
    - Over 40 unnecessary columns were dropped.

## Database Preparation
After the datasets were cleaned, they were merged using SQL. The temperature data and CO2 data share key values: country and year. 

## Communication Protocols:
- Use pandas to clean and perform exploratory analysis on the datasets. Visualize the data to understand relationships between variables, highlight trends, and identify potential outliers or unnecessary data.
- Select and train machine learning model.
- Evaluate the model and determine its accuracy. 
- Use Google Slides and Tableau to communicate analysis.
