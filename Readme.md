# CO2 Emissions from Coal Based Power Plants #

## Introduction ##

Global Warming is a prominent issue and power plants add a significant carbon footprint to the
environment. These power plants lead to pollution and global warming. So we chose a dataset
which shows the carbon dioxide emissions from different power plants.
The dataset is of monthly carbon dioxide emissions from electricity generation available at the
Energy Information Administration and Jason McNeill. The dataset includes CO2 emissions
from each energy resource starting January 1973 to July 2016.

Data : https://www.kaggle.com/datasets/txtrouble/carbon-emissions

 In this project, we retrieved the above mentioned time series dataset, visualized it, and transformed it into
a time series format. We performed a stationarity test. We used PCF and ACF plots to get an
idea about the AR and MA values. We then used Seasonal Autoregressive Integrated Moving
Average (SARIMA) model to make predictions and forecast future CO2 emissions from power
generated from coal-based power plants.

## Exploratory Data Analysis ##

The dataset has 6 columns where 2 of which are integer data types and 4 objects and 5096 observations. It has emission data from 8 different types of power plants.

![image](https://user-images.githubusercontent.com/39477180/222527906-4b6e3edb-1c32-42c6-b6a5-c6fed1186571.png)

From the analysis, we figured out that most of the CO2 emissions is contributed by the coal-based power plants. So we mainly focused on forecasting the CO2 emission from the coal based power plants.
During our analysis, some of the key insights are noted down.
  - 6-month seasonality is observed in the data, there is a peak in the CO2 emissions during Jan and July of the year and a drop during Apr and Oct-Nov months.
  - There is a trend in the CO2 emission dataset with seasonal variation.
To verify the stationarity we used the AD-Fuller test.

## Hypothesis ##

* `Null Hypothesis` : CO2 emissions in the coal industry is non-stationary
* `Alternate Hypothesis` : CO2 emissions in the coal industry is stationary

### Test Results ### 
 ![image](https://user-images.githubusercontent.com/39477180/222530882-ee670b03-88de-4ac2-9ad2-bbb2d544eec6.png)

This implies that the data needs to be changed to stationary form. This was done by taking the
second difference.

## Inference ##

Now, after the analysis, it can be concluded that Seasonal ARIMA will be a good model for this
dataset. 
- There were a total of 523 data points for coal-based power plants. We used the first
480 points to build the model and the remaining data points from 480 for prediction. 
- For
validation, it can be observed in the plot that the actual values from 480 to 523 lies in the
confidence interval of the forecast.
- After several iterations and the observations we made earlier, the model we used was
SARIMA(1,0,1)(1,1,1,6)
- The Mean Squared Error (MSE) of the forecast comes out to be 275.64 and the Root Mean
Square Error (RMSE) of the forecast comes out to be 16.60.

## Conclusion ##

After the complete analysis it can be observed that despite the global concern over global
warming and pollution, Coal based power plants are still the major contributor to CO2 emissions
in the power sector. But a positive point can be observed that a decreasing trend is being
observed in recent years. The same is being observed in the forecast made using SARIMA, but
even after this decrease the carbon footprint from coal-based power plants is very significant
which can be tackled by the aggressive adoption of renewable and other non-conventional
energy resources.

