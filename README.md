## Credit Card Fraud Detection System

### objective
Credit card fraud is a significant problem, with billions of dollars lost each year. Machine learning can be used to detect credit card fraud by identifying patterns that are indicative of fraudulent transactions. Credit card fraud refers to the physical loss of a credit card or the loss of sensitive credit card information .This project proposes to develop a machine-learning model to detect credit card fraud. The model will be trained on a dataset of historical credit card transactions and evaluated on a holdout dataset of unseen transactions.


### Goal of the Project:

The goal of this project is to build a predictive model to determine whether a given transaction will be fraudulent or not. Also, analyze reversed and multi-swipe transactions to identify patterns, outliers, and significant trends across merchants and account numbers over time, as it is essential to figure out the fraudulent transactions so that customers do not get charged for the purchase of products that they did not buy.

### Data Source

The dataset was retrieved from an open-source website, Kaggle.com. It contains data on transactions made in 2013 by European credit card users in two days only. Transaction dataset has total of 786363 entries, with total of 29 coulmns.

The key steps involved in the file are:
1. Exploratory data analysis
2. Data Visualization
3. Model Developement
4. Performance metrics and model evaluation
5. Summary and recommendation

Dataset: kaggle Dataset

### Algorithm

Random Forest
Logistic Regression (L.R.)
Support Vector Machine (SVM)

### Future Work

There are many ways to improve the model, such as using it on different datasets with various sizes and data types or by changing the data splitting ratio and viewing it from a different algorithm perspective. An example can be merging telecom datato calculate the location of people to have better knowledge of the location of the card owner while his/her credit card is being used; this will ease the detection because if the card owner is in Dubai and a transaction of his card was made in Abu Dhabi, it will easily be detected as Fraud.



Conclusion

In conclusion, the main objective of this project was to find the most suited model for creditcard fraud detection in terms of the machine learning techniques chosen for the project. It was met by building the four models and finding the accuracies of them all; the best in terms of accuracy is KNN and Decision Tree, which scored 100 on credit card fraud and increased the customer’s satisfaction as it will provide themwith a better experience and feeling secure.
