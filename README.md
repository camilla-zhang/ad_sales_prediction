# Supervised Learning and Time Series Forecasting for Advertisement Sales

## Project Overview
___
The objective of this study is to build models that can accurately predict the advertising sales made based on impressions and views from the media with three regression models. I also predict the sales for future periods through time-series forecasting. 

This study served two purposes. First, by generating a series of models, I have determined which parameters and algorithms are better at predicting sales than others. More interestingly, this study uncovers the time trends of ad sales and which media channels should be focused more on to increase ad sales. 

### Data and Methods
___
The ![data](https://www.kaggle.com/datasets/yugagrawal95/sample-media-spends-data) contains 3,051 observations of advertisement sales and six media channels from the calendar weeks between 2018 and 2020. The media sales are used as the target variable. Meanwhile, the six media channels, month, year, and region/division are the feature variables. 

For the machine learning segment, I run three models to predict the feature variables on ad sales. I first choose to run the linear regression, becasue it is easy to train and interpret, and to serve as a baseline comparison for other models. We also use this model to show the most significant features in our data. The second model of choice is the random forest classifier, can control overfitting with its random feature subsetting and bootstrapping technique and can work well with imbalanced data. The XGBoost Regression is the final model, and is known to outperform its bagging counterpart when there is high data imbalance and takes less time to train. In both the bagging and boosting methods, we hypertune their more significant parameters (number of trees and number of splits) with RandomizedSearchCV. For the data preprocessing, I encode the categorical data (Months, Years, and Region). I also assign the continuous target variable into bins to stratify the data in our training and testing data. Finally, I scale the data before fitting the data into the models. The results focus on the best parameters and accuracy score for each model.

In the time series analysis, I predict total ad sales from 113 time periods. I test the assumption that our series is stationary by visualizing the trends and checking for unit roots from the Augmented Dickey Fuller Test. I also plot the autocorrelation function and partial autocorrelation function to determine if we should include moving averages or an autocorrelation process into our ARIMA model. Finally, I fit the training data into the auto-generated ARIMA model, and generate predictions with the test data.

### Exploratory Data Analysis
___

Based on the series of scatterplots, we notice that advertisement sales are most highly correlated with impressions, especially those from Google or Affiliate Impressions. On the other hand, they are less correlated with views.
![image]()

The figure below demonstrates that of the regions in the data, the ads showing in regions B, E, and O incur the most sales.
![image]()

The ad sales also show a clear seasonal trend, especially between the months from October to January.
![image]()

### Results
___

*Supervised Learning*

The linear regression model shows that of the feature variables, we found ______ to be the most significant indicators for media sales. The results from our supervised machine learning models are as follows:

1. Linear Regression: 78.5%
2. Random Forest: 89.7%
3. XG Boost: 92.4%

*Time Series Forecasting*

We see that there is a clear indication of seasonality in our series. Particularly, the months from Oct to Jan tend to encounter large sale shocks. Thus, there is an indication of non-stationarity which is accounted for by differencing. Our automated arima model finds the optimal orders for our time series, which appears to be SARIMAX (0,1,0). Thus, while the data does not include moving averages or autocorrelation processes, I difference the data once to remove seasonal trends and make it stationary. The predictions for the last 28 weeks are quite accurate, as indicated by the figure below 
![image]()





