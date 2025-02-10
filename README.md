# Sales Forecasting and Predictive Modeling for Retail Business using XGBoost 
# Overview
This project aims to predict sales for stores in the Rossmann retail chain using historical sales data, store information, and promotional data. The dataset contains sales data for 1,115 stores, including features such as competition, promotions, holidays, and store characteristics.
The primary objective is to build a robust machine learning model that accurately predicts sales, helping retail businesses optimize inventory, staffing, and promotional strategies. The XGBoost Regressor is selected due to its efficiency in handling structured data and superior predictive performance.
# Dataset Description
The dataset consists of sales data from multiple stores and includes features such as: 
  * Store ID : Unique identifier for each store
  * Date : Date of sales record
  * Sales : Target variable (daily sales)
  * Customers : Number of customers on a given day
  * Promo : Whether a store is running a promotion
  * StateHoliday : Indicates if the day is a public holiday
  * SchoolHoliday : Indicates if a school holiday affects store operation
  * StoreType : Type of store (A, B, C, D)
  * Assortment : Level of product variety offered
  * CompetitionDistance : Distance to the nearest competitor store
  * Promo2 : Whether the store is running a continuing promotion
 Target Variable
  * Sales: The objective is to predict daily sales values based on historical data and various influencing factors.
# Steps in the Project Workflow
# 1. Data Import and Merging
  * Imported necessary libraries: pandas, numpy, matplotlib, seaborn, sklearn, xgboost.
  * Uploaded and merged datasets (train.csv, test.csv, store.csv) using the common column Store.
  * Ensured that both training and test data contain relevant store characteristics.
# 2. Exploratory Data Analysis (EDA)
Performed various statistical analyses and visualizations:
   * Sales Trend Analysis: Line plots to examine seasonality and trends.
     ![image](https://github.com/user-attachments/assets/7240ea48-011f-4b64-970d-7452c3676b73)
   * Data Distribution & Outliers Finding: Histograms and boxplots.
     ![image](https://github.com/user-attachments/assets/f700f35e-a207-4a3f-90b5-c6028bf4b752)
     ![image](https://github.com/user-attachments/assets/248c35cb-c8be-4510-bfc7-6942f2e7821a)
   * Handling Missing Values: Checked Null values in multiple columns (e.g., CompetitionDistance, PromoInterval) aand filled with appropriate strategies such as mean imputation or mode imputation.
   * Outlier Detection & Handling: Outliers are capped using the Interquartile Range (IQR) method to avoid data loss.
# 3. Data Cleaning & Feature Engineering
  * Converted Date column to datetime format and extracted features: Year, Month, Week, Quarter, Day of Week
  * Encoded categorical variables using Label Encoding for: StateHoliday, StoreType, Assortment, PromoInterval
  * Checking correlation between features and the target variable
     ![image](https://github.com/user-attachments/assets/efa4956c-dd84-48dc-9361-086eec864a4a)
     ![image](https://github.com/user-attachments/assets/4fc08272-a112-47af-9448-83ac75167501)
    * Feature scaling applied to: CompetitionDistance, Promo2SinceYear, Promo2SinceWeek
# 4. Model Selection and Training
The dataset is split into training and test sets. Two models are used to predict sales:
  * Linear Regression: Served as a benchmark for performance comparison.
  * XGBoost Regressor: A more advanced model using gradient boosting to improve accuracy
Splitting data: 80% training, 20% validation.   
Both models are evaluated using metrics such as Root Mean Squared Error (RMSE) and R² score.
Model Performance Comparison:
 Model                                       RMSE              R² Score
 Linear Regression                          2993.55              0.39
 XGBoost Regressor                          1836.03              0.77
  * XGBoost performed significantly better, achieving a lower RMSE and a higher R² score.
# 5. Feature Importance Analysis
Feature importance is assessed using correlation analysis and mutual information. This helps identify which features are most relevant to predicting sales and provides insight into the model's behavior.
![image](https://github.com/user-attachments/assets/d4c8cf65-5a22-48dc-8fa3-904356f028aa)
# 6. Residual Error Analysis
Residuals (differences between actual and predicted values) are analyzed to check if the model is biased and to ensure that it generalizes well on unseen data.
![image](https://github.com/user-attachments/assets/3cf6b15e-4af5-4c45-9799-5e2b0945f0ec)
# 7. Model Deployment
The trained model is saved using joblib, making it ready for future predictions or deployment.
# . Prediction on Test Data
   * Applied the trained XGBoost model on the test dataset.
   * Saved the final predictions in a CSV file.
# Tools and Technologies Used:
  * Python: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, XGBoost
  * Visualization: Matplotlib, Seaborn
  * Google Colab
  * Machine Learning Models: Linear Regression, XGBoost Regressor
  * Data Handling & Cleaning: Pandas, NumPy 
# Conclusion
This project demonstrates the process of predicting retail sales using historical data. It highlights the importance of data cleaning, feature engineering, and model selection in creating an effective predictive model. The model can be deployed to predict future sales, optimize inventory management, and assist in strategic decision-making for retail stores.
This project demonstrates an end-to-end data science workflow, from data cleaning to building a machine learning model for sales forecasting. 
Key takeaways:
  * XGBoost significantly outperformed Linear Regression, proving its strength in structured datasets.
  * Feature engineering, data preprocessing, and model evaluation were crucial for improving performance.
  * The model can be used for real-time predictions, aiding in inventory management, staffing, and promotional strategies.
# References
  * Kaggle Rossmann Store Sales Dataset
  * XGBoost Official Documentation
  * Python Machine Learning Libraries
