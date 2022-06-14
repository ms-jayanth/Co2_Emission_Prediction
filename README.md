# Co2 Emission Prediction

## User Interface:
https://share.streamlit.io/ms-jayanth/co2_emission_prediction/main/Co2_Emission_Streamlit.py

## Introduction:
Global warming is one of the biggest challenges currently being faced by the human race, although correlation is not causation a likely cause of global warming is due to increased atmospheric carbon dioxide from human activities. 

Passenger cars produced approximately three billion metric tons of carbon dioxide emissions worldwide in 2020. The emissions produced by passenger cars have been steadily rising over the past two decades, increasing from 2.2 billion metric tons in 2000 to a peak of 3.2 million metric tons. Emissions fell roughly six percent in a 2020 as a result of the COVID-19 pandemic, which caused major disruptions to transportation.

## Objective:
The goal of this project is to predict CO2 emissions in g/km produced by any vehicle based on several car engine features.


## Dataset:
https://drive.google.com/file/d/1Ayearcq9sard1wan-vZ8z56Tcjaz5Lg-/view?usp=sharing

## About Dataset:

### Content
This dataset captures the details of how CO2 emissions by a vehicle can vary with the different features. The dataset has been taken from Canada Government official open data website. This is a compiled version. This contains data over a period of 7 years.<br>
There are total 7385 rows and 12 columns. There are few abbreviations that has been used to describe the features. I am listing them out here. The same can be found in the Data Description sheet.

Model
- 4WD/4X4 = Four-wheel drive
- AWD = All-wheel drive
- FFV = Flexible-fuel vehicle
- SWB = Short wheelbase
- LWB = Long wheelbase
- EWB = Extended wheelbase

Transmission
- A = Automatic
- AM = Automated manual
- AS = Automatic with select shift
- AV = Continuously variable
- M = Manual

Gears
- 3 - 10 = Number of gears

Fuel type
- X = Regular gasoline
- Z = Premium gasoline
- D = Diesel
- E = Ethanol (E85)
- N = Natural gas

Fuel Consumption
City and highway fuel consumption ratings are shown in litres per 100 kilometres (L/100 km) - the combined rating (55% city, 45% hwy) is shown in L/100 km and in miles per gallon (mpg)

CO2 Emissions
The tailpipe emissions of carbon dioxide (in grams per kilometre) for combined city and highway driving

## Acknowledgements:
The data has been taken and compiled from the below Canada Government official link<br>
https://open.canada.ca/data/en/dataset/98f1a129-f628-4ce4-b24d-6f16bf24dd64#wb-auto-6

## Project Summary:
1. **EDA**<br>
From the data I came to know that:<br>
There are some dupluicate values in the dataset<br>
There are no null values<br>
Quantitative data consists of outliers<br>
There is multicollinearity problem in the data<br>

    EDA Report: https://share.streamlit.io/ms-jayanth/co2_emission_prediction_deployment/main/EDA_Report.py

2. **Data Preprocessing**<br>
In this script<br>
I have removed the duplicate values.<br>
I have detected the outliers with the help of Z-Score and IQR method and treated them by Quantile based flooring and capping.<br>

    After preprocessing, data looks like:<br>
    https://drive.google.com/file/d/1XqVzFJG0ztKhHq43_8uS6Nu1c27nM8k4/view?usp=sharing

3. **Feature Engineering**<br>
Since data is highly correlated within explanatory variables I have used SelectKBest method and RFM method for feature selections<br>
After Feature Engineering, data looks like:<br>
https://drive.google.com/file/d/1ZFjnjPOhAPSo7jTdYboy05kZD8R1D0mB/view?usp=sharing


4. **Model Building and Evaluation**<br>
I have build the model with 8 different ML algorithms
- Linear Regression
- Ridgr Regression
- Lasso Regression
- Decision Tree Regressor
- Random forest regressor
- Gradiant Boosting
- Xtreme Gradiant Boosting
- Support Vector Machine<br>

   and also build with
- Artificial Neural Networks

  Among these Xtreme Gradient Boosting and ANN fits the best with R2 score of 99.8%

5. **Deployment**<br>
I have deployed Xtreme Gradient Boosting Model in Streamlit Cloud<br>
Script: https://github.com/ms-jayanth/Co2_Emission_Prediction_Deployment


## Conclusion:
From the model performance metrics, it appears that 99.8% of the variance in the CO2 Emissions can be determined by the features within our model. While this model has good performance, we simplified the model by omitting several key categorical variables. It would be interesting to see if there is way to retain them within the model, and gain further insights.
