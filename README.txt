The following project is about predicting the closing value
of the upcoming 2 months. In the Jupyter Notebook provided,
you can find all the code for predicting December 2025 and
January 2026 monthly closing values of 3M Company (MMM).

This work was completed as part of the university assignment
“Statistical Methods in Machine Learning – Project 1”.
The goal is to forecast the average monthly closing price
of a stock using historical data, lag-based features and
several regression models.

===============================================================
                    PROJECT DESCRIPTION
===============================================================

The project focuses on forecasting the next month’s average
closing value using the previous monthly closing prices and
trading volumes. Historical daily data were collected using
the yfinance library and then aggregated into monthly values.

The main steps of the project include:
Data collection and preprocessing
Creation of lag features (close_t-1, close_t-2, close_t-3
and volume_t-1, volume_t-2, volume_t-3)
Gaussian smoothing to reduce noise
Splitting the dataset into training (before 2024)
and validation (2024–2025)
Building and evaluating multiple regression models
Forecasting December 2025 and January 2026

===============================================================
                    MODELS USED
===============================================================

A: Linear Regression
A simple linear model was trained using lagged closing prices
and volumes. It produced stable predictions and served as
the baseline approach. Evaluation metrics (MSE, MAE) were
calculated for both the training and validation set.

B: Polynomial Regression with Regularization
Polynomial features (degree 2) were used together with:
– Ridge Regression (L2 regularization)
– Lasso Regression (L1 regularization)
These models helped capture nonlinear relationships and
reduced overfitting through alpha regularization parameters.

C: Dimensionality Reduction
Three different methods were tested:
– PCA (Principal Component Analysis)
– CFA (Factor Analysis)
– RFE (Recursive Feature Elimination – wrapper method)
RFE performed best on this dataset, selecting close_t-1
as the most informative feature.

===============================================================
                    RESULTS & PREDICTIONS
===============================================================

The notebook includes predictions for:
– December 2025
– January 2026 (recursive forecasting)

The exact numeric results may vary if the notebook is executed again,
since financial data update over time.

===============================================================
                    FILES INCLUDED
===============================================================

- data_acquisition.ipynb
Contains all the code for data collection, feature creation,
preprocessing, model training and forecasting.
- MMM_close_prices.csv / MMM_monthly.csv 
Datasets with daily and monthly closed prices required for the training
- stocks.json
A json file that has every value for each day, created from the code
- ergasia_1_1097449.pdf
The report for my project written in Greek
- README.txt
This document.

===============================================================
                    REQUIREMENTS
===============================================================

You need Python 3.10+ and the following libraries:

numpy
pandas
matplotlib
sklearn
yfinance
scipy

===============================================================
                    NOTES
===============================================================
The project uses yfinance instead of Alpha Vantage because it
provides complete historical data without a 100-day limit.
The company examined is 3M (MMM).
MMM is scheduled to distribute a dividend in December, which may
slightly affect the stock’s actual future price.
All results included correspond to the latest execution of the
notebook at the time of submission.