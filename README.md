![Stock Predictor](static/images/image2.jpg)

# Final Research project: Predicting stock prices with Machine Learning

## INTRODUCTION

The popularity of cryptocurrencies over the past few years has exploded. More and more people are investing their money into Bitcoin, Litecoin and Ethereum. What makes cryptocurrencies so appealing? Their popularity seems just as mysterious as their existence with new currencies emerging everyday and prices soaring uncontrollably especially in recent times. Our aim is to build a supervised regression model that would be able to predict the changes and trends in stock prices based on historical data (prices) using the Bitcoin historical data. 

## METHODOLOGY

![Stock Predictor](static/images/BTC_Logo.svg.png)
In this project, we attempt to conduct technical analysis using price trend and volume indicators. We rely on these variables, based on the assumption that they capture and reflect all public available information and hence focus on statistical analysis of price movements. The objective for our final project is to create a machine learning model to discover and take advantage of trends that can help us predict the future outcome of Bitcoin. Our dataset was obtained from Kaggle.com and it will feed our model over 3.6 million datapoints to learn from. Our work with this model and Bitcoin will become the foundation for future applications. Theoretically, our model can be applied to other cryptocurrencies and equities to help make savvy financial decisions.

The visualizations and dashboard for our project were created using JavaScript and the Plotly.js and D3 libraries. For the machine learning and analysis portion of our project, we used python and jupyter notebook. To view our work and analysis, you can run the included notebooks. 
•	bitcoin_models.ipynb contains the our work to train and create our model along with a view different machine learning libraries that were used to see which gave us the best result. We ultimately used Scikit Learns built in model to perform our linear regression.
•	Regression_model.sav is the model that we created from bitcoin_models.ipynb. We saved our model so that it could be loaded into other notebooks for analysis.
•	Model_testing.ipynb was created to run our model with current data on bitcoin. Our intentions were to use the model we created to predict other stock symbols based on the price and volume indicators.
•	get_data.ipynb was an additional notebook created to make API calls to Quandl and is not associated with the machine learning section of our project. The data obtained from Quandl and this notebook were saved and stored local for visualizations on our dashboard.



