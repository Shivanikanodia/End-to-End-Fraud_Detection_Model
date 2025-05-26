💳 Credit Card Fraud Detection System

📌 Overview

Credit card fraud results in billions of dollars in losses each year. This project leverages machine learning to detect fraudulent transactions by identifying behavioral patterns and anomalies in historical credit card data. The model is designed to flag suspicious activity in near real-time, helping financial institutions reduce fraud risk and protect customers.

🎯 Business Problem

Fraudulent transactions lead to:

Direct financial losses through chargebacks
Customer dissatisfaction and loss of trust
Compliance and regulatory challenges
The goal is to develop a robust predictive model that:

Accurately identifies fraudulent transactions
Minimizes false positives (avoiding unnecessary transaction blocks)
Provides insights into high-risk accounts, merchants, and behaviors
🧠 Project Goals

Build a classification model to detect fraudulent transactions.
Analyze transaction patterns, reversals, and multi-swipes to uncover suspicious activity.
Visualize trends across merchants, accounts, and time.
Ensure model interpretability and handle class imbalance.
📂 Dataset

Source: Kaggle – Credit Card Fraud Detection
Timeframe: Two days of credit card transactions by European users (2013)
Size: 786,363 transactions
Features:
Time: Seconds since the first transaction
Amount: Transaction amount
V1–V28: PCA-anonymized numerical features
Class: 0 = Legitimate, 1 = Fraudulent
⚠️ Note: All features are anonymized and numeric, which limits domain-level interpretability.
📈 Workflow

Exploratory Data Analysis (EDA)
Distribution of transaction amounts and times
Reversal and multi-swipe analysis
Fraud frequency by merchant and account
Data Preprocessing
Handling missing values
Standardization of Amount
Addressing severe class imbalance using SMOTE
Model Development
Logistic Regression (baseline model)
Random Forest Classifier (handles non-linearity and feature importance)
Class balancing with SMOTE
Evaluation Metrics
Precision: Minimize false positives
Recall: Maximize detection of fraudulent cases
F1-Score: Balance precision and recall
ROC-AUC: Threshold-independent model performance
⚙️ Algorithms Used

Model	Why Chosen
Logistic Regression	Simple, interpretable baseline
Random Forest	Handles complex feature interactions, robust to overfitting
SMOTE	Mitigates extreme class imbalance (~0.17% fraud cases)
📊 Key Insights

High-Risk Accounts: Accounts 380680241 and 882815134 had excessive reversal activity (907 and 384 respectively).
Suspicious Merchants: Lyft, Uber, Alibaba, and eBay showed disproportionately high reversal counts.
Pattern Detection: Multi-swipe and reversed transactions often preceded fraudulent labels, suggesting a behavioral sequence.
📉 Limitations

Aspect	Limitation
Time Window	Only 2 days of data; not representative of seasonality or long-term trends
Anonymization	PCA-transformed features limit interpretability and domain-based feature engineering
Class Imbalance	<0.2% of transactions are fraudulent — requires synthetic sampling
Lack of Categorical Data	No transaction type, location, device, or channel data
🚀 Business Impact

By identifying fraud patterns across accounts and merchants:

Institutions can proactively flag high-risk behaviors
Customers are protected from unauthorized charges
Fraud detection accuracy improvements of even 1–2% can save millions annually
📁 Folder Structure

├── data/                   # Raw and processed datasets
├── notebooks/              # EDA and model-building notebooks
├── models/                 # Trained model files
├── src/                    # Source code for training, preprocessing, etc.
├── visuals/                # Charts, graphs, and EDA results
├── README.md               # Project overview and documentation
✅ Next Steps

Integrate temporal features (time since last transaction, transaction velocity)
Add explainability using SHAP values or LIME
Test with real-time streaming data (e.g., Kafka + Spark)
Explore ensemble methods like XGBoost or LightGBM for better accuracy
👨‍💻 Tech Stack

Python (pandas, scikit-learn, imbalanced-learn, matplotlib, seaborn)
Jupyter Notebooks
Git + GitHub
