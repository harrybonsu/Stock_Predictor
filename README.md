# Final Research project: Predicting stock prices with Machine Learning

![Stock Predictor](static/images/BTC_Logo.svg.png)

## INTRODUCTION

The popularity of cryptocurrencies over the past few years has exploded. More and more people are investing their money into Bitcoin, Litecoin and Ethereum. What makes cryptocurrencies so appealing? Their popularity seems just as mysterious as their existence with new currencies emerging everyday and prices soaring uncontrollably especially in recent times. Our aim is to build a supervised regression model that would be able to predict the changes and trends in stock prices based on historical data (prices) using the Bitcoin historical data. 

## METHODOLOGY

![Stock Predictor](static/images/image2.jpg)
In this project, we attempt to conduct technical analysis using price trend and volume indicators. We rely on these variables, based on the assumption that they capture and reflect all public available information and hence focus on statistical analysis of price movements. The objective for our final project is to create a machine learning model to discover and take advantage of trends that can help us predict the future outcome of Bitcoin. Our dataset was obtained from Kaggle.com and it will feed our model over 3.6 million datapoints to learn from. Our work with this model and Bitcoin will become the foundation for future applications. Theoretically, our model can be applied to other crypto currencies and equities to help make savvy financial decisions.

The visualizations and dashboard for our project were created using JavaScript and the Plotly.js and D3 libraries. For the machine learning and analysis portion of our project, we used python and jupyter notebook. To view our work and analysis, you can run the included notebooks. 
•	bitcoin_models.ipynb contains the our work to train and create our model along with a view different machine learning libraries that were used to see which gave us the best result. We ultimately used Scikit Learns built in model to perform our linear regression.
•	Regression_model.sav is the model that we created from bitcoin_models.ipynb. We saved our model so that it could be loaded into other notebooks for analysis.
•	Model_testing.ipynb was created to run our model with current data on bitcoin. Our intentions were to use the model we created to predict other stock symbols based on the price and volume indicators.
•	get_data.ipynb was an additional notebook created to make API calls to Quandl and is not associated with the machine learning section of our project. The data obtained from Quandl and this notebook were saved and stored local for visualizations on our dashboard.

## DATA RETRIEVAL AND PREPROCESSING

The data was obtained from Quandl.com and Kaggle. Quandl allows free API calls to retrieve the data on bitcoin for the period beginning April 2014 using their API and included information on High, Low, Mid, Last, Bid and Ask price, as well as the volume traded. This data was much smaller to work with and allowed us to create visualizations for our dashboard that we hope benefits the end user. 

The data we used for our machine learning model was obtained from Kaggle. The dataset contained minute to minute information from December 2011 to March 31, 2021, yielding over 3.6 million rows of information to build and train our model. Due to its size, the data was stored in an AWS S3 bucket and the URL was called to our jupyter notebooks to perform the analysis.The data preprocessing included checking NaN (Null) values, formatting the Timestamp column from timestamp to Datetime and renaming the required columns. 

## MODEL BUILDING AND PREDICTION

Now that we have prepared our data for analysis, we can begin to train our model so that it could make predictions. First, we need to define our independent and dependent variables. As indicated above, we are using a supervised learning model which means that we have data for what is expected from our model. We defined our independent variables as High price, Low price and Volume traded which will be held in the X variable. Our dependent variable, or the expected output from our model, will be the closing price stored in the y variable. 

Our next step is to split the data into a training dataset and a testing dataset. The reason we do this is so that the model can begin to learn from the training data before we test the accuracy of our model with the testing data. To remove any bias from the training and testing process, when the data is split, it is split randomly. Once this is complete, we can fit the data to our model and make our prediction. What you can see from our residual plot, which is a scatter plot that shows the dispersion of the data, is that our model’s predictions from the testing data is quite accurate compared to the training data. To provide a more concise visualization of our model’s prediction, we created another data-frame that shows the actual closing price versus the predicted price. 

In order to check the accuracy of our model, we fitted our data with several models (Linear regression, Lasso, Ridge and ElasticNet model) and selected the best model based on the r2 and mean squared error (MSE) scores. The selected model, Linear regression, had a r2 score and MSE of 0.9999 and 73.2997 respectively which produced the best predicted values. Now, let’s feed our model some current data and see what output our model returns.

## FURTHER TESTING AND MOVING AVERAGES

Although our model can be tested on any stock, we chose to do a further testing on Bitcoin data from April 2021 to July 1, 2021, and we plotted the predicted results against the actual results. It is worth noting that both lines appeared as we had suspected based on the r2 and MSE values obtained from training the model. We then calculated moving averages from the actual closing values. The reason for calculating the moving average of a stock is to help smooth out the price data over the specified period by creating a constantly updated average price and this helps mitigate the impacts of random, short-term fluctuations on the stock price. We calculated a 15-day and 30-day simple moving averages (SMAs) as well as an exponential moving average (EMA). We chose to plot the 30-day moving average against the exponential moving average and they both depict a similar trend to the actual closing price and hence gives users a fair idea of the general price trend of the stock.

