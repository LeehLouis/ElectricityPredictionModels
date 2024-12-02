# Electricity Prediction Models
This project aims to predict the usage of electricity based on the daily data extracted from MyTNB.

The features used in the models were of the data recorded throughout 29 days period and 35 days period.


## The data sources are:
MyTNB android app

ERA-5 Land Daily retrieved using Google Earth Engine

## The results of modelling:

### Linear Regression (35 Lines of Historical Data)

By using more data values, the MAE and RMSE have decreased a lot.

Model Performance with Normalized Data and Day Encoding:

Mean Absolute Error (MAE): 0.33

Root Mean Squared Error (RMSE): 0.39

![Untitled](https://github.com/user-attachments/assets/12c4c977-4836-4bf3-b957-5c4984cf3330)

| Feature            | Coefficient |
|--------------------|-------------|
| Tariff_Rates       | 0.617047    |
| People_at_Home     | 0.138632    |
| Time_Out           | 0.075371    |
| Fans_in_Use        | 0.045280    |
| daily_rainfall     | 0.033366    |
| Day                | 0.008618    |
| Avg_Temperature    | -0.019930   |
| Went_Out           | -0.147944   |




### Linear Regression (29 Lines of Historical Data)

Model Performance with Normalized Data and Day Encoding:

Mean Absolute Error (MAE): 0.53

Root Mean Squared Error (RMSE): 0.56

![image](https://github.com/user-attachments/assets/ad1b2fc3-881e-482f-870e-24d9a29af22b)

### Feature Importance

| Feature            | Coefficient  |
|--------------------|--------------|
| People_at_Home     | 0.786704     |
| Tariff_Rates       | 0.492046     |
| Went_Out           | 0.186248     |
| daily_rainfall     | 0.041503     |
| Avg_Temperature    | -0.022611    |
| Day                | -0.079370    |
| Time_Out           | -0.278116    |
| Fans_in_Use        | -0.614044    |



### Removing Negative Coefficients from Linear Regression 
Model Performance with Normalized Data and Day Encoding:

Mean Absolute Error (MAE): 0.31

Root Mean Squared Error (RMSE): 0.34

![image](https://github.com/user-attachments/assets/9063742b-6162-44eb-ace6-ceaf2861f164)

### Feature Importance

| Feature          | Coefficient  |
|------------------|--------------|
| Tariff_Rates     | 0.577625     |
| People_at_Home   | 0.154573     |
| daily_rainfall   | 0.049043     |
| Went_Out         | -0.106671    |

## Current Project Limitations
### 2/12/2024 Revision

Updated to 35 Lines of Historical Data

By adding another 6 lines of data, the model improved from:

MAE: 0.53

RMSE: 0.56

To: 

MAE: 0.33

RMSE: 0.39


MyTNB only provides the most recent 29 days of daily usage data, this restricts the model to only having the most recent daily data to be processed.

Another significant limitation related to data availability is associated with ERA5-Land data. The most recent data is consistently delayed by five days relative to the current date, as it requires pre-processing by Copernicus.
