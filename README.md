## Credit Card Fraud Detection System: 

###  Overview: 

This project builds a machine learning model to detect fraudulent credit card transactions using historical data. Fraud detection is critical for minimizing financial loss and protecting customer trust.

----

## Business Problem: 

Credit card fraud can result in significant financial damage.  The objective is to flag fraudulent transactions accurately while minimizing false negatives and enabling banks to act quickly and efficiently, minimizing loss. 

----

## Dataset: 

- **Source**: Kaggle – Credit Card Fraud Detection Dataset. 
- **Records**: **786,363** transactions
- **Features**: **28 features** and target label `Class` (0 = legit, 1 = fraud)

 ----

1. #### DATA PREPROCESING:
   
- Used **isnull().sum()** function to check missing values and there was no missing values present across all records.
- Used **nunique()** to check unique values present in the dataset.
     
**Insights:** **CurrentBalance, TransactionDatetime and Available_Money has highest unique values b/w (10,0000 - 14,0000).** 
Followed by transaction_amount with approx **40,000 unique values.** Lastly, **Merchant_Name with 2300 and CardLast4digits with 1225 unique values.** 
     
- Checked Data Quality and if there are any whitespaces & empty strings present in dataset.  

**Insights:** (Dropped coulmns  - 'echoBuffer', 'merchantCity', 'merchantState','merchantZip', 'posOnPremises', 'posConditionCode',  'recurringAuthInd' which were empty strings). 

- Performed **Statastical testing** using **A/B Testing (Chi-Square and ANOVA)** for feature importance and validation. It tells us whether the association between a feature and the target is likely due to chance or not. A low p-value indicates that the relationship is statistically significant and not random.

**Insights:**  Columns such as **PosEntryMode, CurrentExpDate, TransactionType, AcqCountry, and MerchantCountryCode** shows low Chi-Square statistics and high p-values, indicating a lack of statistical significance in distinguishing between fraudulent and non-fraudulent transactions. As a result, these features can be safely excluded from further analysis.

---

- #### FRAUD RATE FOR CURRENT_BALANCE, TRANSACTION_AMOUNT, AVAILABLE_MONEY AND CREDIT_LIMIT:**

Calculated the average fraud rate for each category within these variables and their thresolds.

<img width="693" height="415" alt="Screenshot 2025-09-13 at 01 37 38" src="https://github.com/user-attachments/assets/6f62c563-9e88-4cdf-b515-948adf525d4d" />

<img width="691" height="422" alt="Screenshot 2025-09-13 at 01 37 45" src="https://github.com/user-attachments/assets/2cad7477-ed3f-46ba-8538-68e3f722817f" />

  <img width="682" height="414" alt="Screenshot 2025-09-13 at 01 37 55" src="https://github.com/user-attachments/assets/65068dd0-c6dd-4ea3-bdac-f301ab7ce609" />

  <img width="681" height="430" alt="Screenshot 2025-09-13 at 01 38 01" src="https://github.com/user-attachments/assets/45359274-bbc7-4905-b0ad-27c37ddbca26" />

This means you’re only looking at the top X% of values for that feature and the proportion of fraudulent transactions within that slice of the data. So, essentially we are testing: “If we only focus on the higher values of this feature, does fraud happen more often or less often?" 

For **Credit Limit,** fraud rate is mostly flat around **1.3–1.5%,** regardless of the threshold. This suggests credit limit doesn’t strongly influence fraud likelihood. Fraud is spread evenly across both low and high credit limits.

Fraud rate decreases slightly as **Available Money** increases, with **10% threshold**  we see **1.52% fraud rate** and with **80 threshold** we see **1.21% fraud Rate.** People with lower available money balances show slightly higher fraud rates.

*Fraud rate increases steadily as transaction amounts get larger, with **10% threshold,** we see **1.6% fraud rate** and with **90% threshold** we see **3.4% fraud rate.** There is strong upward trend: Higher-value transactions are much more likely to be fraudulent.*

These results can be potentially because of imbalance dataset and could lead to bias results, we cannot solely rely on these findings without using SMOTE or class weightage techniques.

----

### Data Visualization:

Lets understand transaction patterns, reversed transactions & multiswipe transactions, and merchant behavior using data visualization. 

Number of reversed_transactions  3345
Total value of reversed_transactions $466263.25


   
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


