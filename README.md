# Solar-Generation-Forecasting
A random forest regression model trained on solar generation data for 24 hour ahead forecasting.

This model was my final project for CS 458 - Intro to Data Mining. The goal of this project to create a 24 hour ahead forecasting model for solar power generation at three solar plants in Australia. 

We were given the freedom to choose any model or method to achieve a low error score. 

This particular solution implements a random forest regressor (scikit-learn library) trained on hourly measurements that I converted to time-series data.

## Overview:

### Feature Reduction:
 • Used for decreasing training time/hyperparameter tuning time
 • Only used with features that had either very low correlation with solar generation or had another feature with a very high correlation with another feature
 • Determined using a correlation matrix
 
### Data Formating:
 • Normalize the data (between 0 and 1)
 • Prepare in a Pandas dataframe
 • Convert to time series
 • Split data into training set and testing set
 
### Model Selection:
 • Many models were trained and tested
 • Model selection was based on resulting MAE (mean absolute error) and RMSE (root mean squared error) scores for the test set
 • Best model before hyperparameter optimization was the **random forest regressor** 

### Hyperparameter optimization: 
 • Gridsearch (scikit-learn)
 
 ### Results:
 
 ZONEID |     1     |     2     |     3     |  Total  |
 -------|-----------|-----------|-----------|---------|
 MAE    |0.05475    |0.06205    |0.06218    |0.05966  |
 RMSE   |0.11053    |0.11933    |0.11919    |0.11635  |

