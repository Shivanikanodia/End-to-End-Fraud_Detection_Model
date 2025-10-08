

## Identifying Fraudulent Transactions:

#### Objective of the Project:

The objective of this project is to build a predictive model that classifies whether a given transaction is fraudulent or legitimate. Detecting fraudulent transactions is critical in the financial and banking sectors to minimize monetary losses, protect customers, and maintain trust.

#### Business Goal:

Maximize fraud detection accuracy (high recall) while maintaining a low false positive rate (balanced precision-recall trade-off).


---- 


### Data Preparation and Missing Values:


<img width="664" height="607" alt="Screenshot 2025-10-07 at 17 17 45" src="https://github.com/user-attachments/assets/7b37e9d7-cc4f-4df0-832a-d7200e420ebf" />


**Skewness and Outliers in Dataset:**


<img width="477" height="578" alt="Screenshot 2025-10-07 at 17 06 19" src="https://github.com/user-attachments/assets/1338cc30-6e7d-44b8-8d0b-38855e264222" />



<img width="488" height="531" alt="Screenshot 2025-10-07 at 17 06 27" src="https://github.com/user-attachments/assets/88bdd595-a414-42e4-a152-369c3a203112" />

---

## Data Visualisation - EDA: 


**Top Merchants detected based on Fraud Rate, Fraud Amount, Fraud Count and Temporal trends:**.

### Top 10 Merchants by FRAUD RATE:

<img width="665" height="371" alt="Screenshot 2025-10-07 at 17 07 36" src="https://github.com/user-attachments/assets/e3d67dc7-7891-4113-816f-4e6ef2d62669" />

### TOP 10 Merchants by FRAUD AMOUNT:


<img width="667" height="353" alt="Screenshot 2025-10-07 at 17 07 46" src="https://github.com/user-attachments/assets/3853b6e8-1a54-4920-9cf3-9e26a7ed8a18" />


### TOP 10 MERCHANTS BY FRAUD COUNT:


<img width="723" height="355" alt="Screenshot 2025-10-07 at 17 07 51" src="https://github.com/user-attachments/assets/8cde7064-916e-4aa5-99db-56fb1c58f79a" />


### PEAK HOURS WHERE FRAUD OCCURENCE IS HIGHEST: 

<img width="520" height="409" alt="Screenshot 2025-10-07 at 17 07 59" src="https://github.com/user-attachments/assets/1df3cc98-c25f-4c4a-b9c2-026f1deb73ff" />




<img width="656" height="118" alt="Screenshot 2025-10-07 at 17 08 16" src="https://github.com/user-attachments/assets/c9415778-6ad3-4cde-bfa4-16ed5cf3e44c" />


-----

## Feature Engineering:


 <img width="957" height="630" alt="Screenshot 2025-10-07 at 17 05 53" src="https://github.com/user-attachments/assets/9846a1c8-f6b1-4eb7-ad24-e4551d7285bb" />




 <img width="1320" height="324" alt="image" src="https://github.com/user-attachments/assets/4a72641e-b71f-4749-ac45-528fc6bde1b3" />
 



<img width="610" height="120" alt="Screenshot 2025-10-07 at 17 06 54" src="https://github.com/user-attachments/assets/ab5053e9-4cdb-446d-9417-00a87fcf3a16" />




### Data Transformation using Coulmn transfoer and Pipeline. 


<img width="1234" height="906" alt="image" src="https://github.com/user-attachments/assets/d3687817-566d-4d29-94bf-b4a1e58a0c6e" />


-----

## Model Developement and Evaluation: 

### 1.Results from Logistic Regression with a tuned Thresold:


<img width="655" height="633" alt="Screenshot 2025-10-07 at 17 11 34" src="https://github.com/user-attachments/assets/9c1b155b-50f3-4dec-bbd4-cf6119ea356a" />


### 2.Results from Xgboost:


<img width="658" height="743" alt="Screenshot 2025-10-07 at 17 08 46" src="https://github.com/user-attachments/assets/4ab63ff0-8596-429e-8c6c-368186d8fd31" />


------


### Which models to Deploy in Production: 

XGBoost performs best for this problem, primarily because it achieves the lowest number of false negatives, which aligns with our business goal of minimizing missed fraudulent transactions.

Missing a fraudulent transaction (false negative) can lead to substantial financial losses. Therefore, maximizing recall — the proportion of actual frauds correctly identified — is critical. XGBoost successfully maximizes recall while still maintaining a reasonable balance with precision, with around 900 false positives, which is an acceptable trade-off for improved fraud detection.

Additionally, XGBoost’s ability to handle non-linear relationships, missing values, and class imbalance makes it a strong candidate for production deployment. Its performance consistency and scalability also make it suitable for real-time predictions in fraud detection systems.

As a rollback option, Logistic Regression with a 0.5 threshold can serve as a backup model. Although it achieves slightly fewer false negatives, it results in over 11,000 false positives, which could cause unnecessary alerts and damage customer trust.

Hence, XGBoost is the optimal choice — it effectively minimizes false negatives (the most costly error type) while keeping false positives within an acceptable range, offering a strong balance between business risk and user experience.

-----

### TOP PREDICTORS OF FRAUD:

**Merchants and peak hours to Watch out:**

Fresh Flowers, Uber, Lyft, Ebay.com, Sears consistently appeared in list where Fraud transaction volume, fraud rate and fraud counts were high. This evidented from the temporal analysis where hours like 12:00 AM, 06:Q0 AM and 03:00 PM were targeted and these specific merchants showed fraudulent activity indicating low monitoring hours or weak verification system.

Walmart, Alibaba, Target and small merchants grouped as others also showed small number of transaction volume as fradulent indicating gift card attacks or bot testing.
