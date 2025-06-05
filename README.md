# Credit Card Fraud Detection System

## Overview

This project builds a machine learning model to detect fraudulent credit card transactions using historical data. Fraud detection is critical for minimizing financial loss and protecting customer trust.

## Business Problem

Credit card fraud can result in significant financial and reputational damage. The objective is to flag fraudulent transactions accurately while minimizing false negatives, enabling banks to act quickly and efficiently.

## Dataset

- **Source**: Kaggle – Credit Card Fraud Detection
- **Records**: 786,363 transactions
- **Features**: 28 anonymized numerical features and target label `Class` (0 = legit, 1 = fraud)

## Approach

1. **EDA & Visualization**: Understand transaction patterns, reversals, and merchant behavior
2. **Data Preprocessing**:
   - Data Description, data cleaning, data scaling, label encoding and data visualization
   - Data Quality and accuracy, whitespaces, empty strings and removing non relevant data. 
   - Stastical Significance using A/B Testing (Chi Square and ANOVA for features importance and validation)
   - Fraud rates for numerical features and their thresolds.  
3. **Modeling**:
   - Logistic Regression
   - Random Forest Classifier
   - Random Forest with thresold using ROC AUC Curve. 
   - Handled class imbalance with SMOTE. 
4. **Evaluation Metrics**:
   - Precision, Recall, F1-score, ROC-AUC
   - Focused on Recall to reduce missed fraud cases, achieved 68% of Recall in final model, reducing false negatives. 

## Key Insights

- Certain accounts and merchants (e.g., Uber, Lyft, Alibaba) show high reversal patterns
- Fraud often follows reversed transactions and less crucial in multiswipe transactions. 
- Class imbalance is severe (<0.2% fraud), required careful handling using class weights and SMOTE. 

## Limitations

- Only 2 days of data; lacks seasonal/long-term patterns, time based features did not give much insights on fraud detection. 
  
## Tech Stack

- Python, scikit-learn, imbalanced-learn, pandas, matplotlib 
- Jupyter Notebook, Collab, AWS S3 

## Author

Shivani Kanodia  
[GitHub Portfolio](https://github.com/Shivanikanodia)  
[Tableau Dashboards](https://shorturl.at/hGzDx)


