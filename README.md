# Credit Card Fraud Detection System

## Objective
Credit card fraud is a significant problem, with billions of dollars lost each year. Machine learning can be used to detect credit card fraud by identifying patterns that are indicative of fraudulent transactions. Credit card fraud refers to the physical loss of a credit card or the loss of sensitive credit card information .This project proposes to develop a machine-learning model to detect credit card fraud. The model will be trained on a dataset of historical credit card transactions and evaluated on a holdout dataset of unseen transactions.

## Goal of the Project:

The goal of this project is to build a predictive model to determine whether a given transaction will be fraudulent or not. Also, analyze reversed and multi-swipe transactions to identify patterns, outliers, and significant trends across merchants and account numbers over time, as it is essential to figure out the fraudulent transactions so that customers do not get charged for the purchase of products that they did not buy.

## Data Source

The dataset was retrieved from an open-source website, Kaggle.com. It contains data on transactions made in 2013 by European credit card users in two days only. Transaction dataset has total of 786363 entries, with total of 29 coulmns.

The key steps involved in the file are:
1. Exploratory data analysis
2. Data Visualization
3. Model Developement
4. Performance metrics and model evaluation
5. Summary and recommendation

Dataset: kaggle Dataset

## Algorithm

Random Forest
Logistic Regression (L.R.)
SMOTE Analysis

## Conclusion
Account Number, PostEntry Mode, and Merchant Name emerge as key indicators of potential fraud. Accounts 380680241 and 882815134 show unusually high reversal counts (907 and 384), indicating the need for closer review of their transaction timelines. High reversal volumes from merchants like Lyft (692), Uber (689), Alibaba.com (499), and eBay.com (491)—primarily in e-commerce and ride-sharing—highlight platforms requiring enhanced monitoring due to elevated risk.
