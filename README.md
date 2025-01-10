# Credit-Default-Prediction
Credit card defaults can lead to billions in losses annually. Predicting default probabilities helps financial institutions minimize losses, maintain profitability, and allocate resources effectively.  

 

Customer Insights:  


This project allows institutions to better understand customer behaviors and risk profiles. These insights are essential for creating personalized financial products and services.  

In summary, this project addresses an issue of universal importance in the financial sector. By leveraging machine learning techniques on anonymized data, we aim to contribute to a more sustainable and equitable credit ecosystem. 

 

 

DATA OVERVIEW 

The dataset sourced from Kaggle contains information about customer profiles and is used to predict whether a customer will default. It includes anonymized and normalized features collected from multiple statement dates. The dataset has 1,107,069 rows and 190 columns, with the features organized into the following categories: 

D_ (Delinquency Variables): Information about past due payments. 

S_ (Spend Variables): Details of customer spending habits. 

P_ (Payment Variables): Records of customer payment activity. 

B_ (Balance Variables): Data on outstanding balances. 

R_ (Risk Variables): Indicators of the likelihood of default. 

Kaggle Link - https://www.kaggle.com/c/amex-default-prediction/data 

MODEL SELECTION 

Logistic Regression 
Logistic Regression is simple, interpretable, and effective for establishing a baseline in binary classification tasks with linear relationships. 

Random Forest 
Random Forest is robust against overfitting, handles non-linearity well, and provides feature importance insights for better interpretability. 

XGBoost 
XGBoost is highly efficient, scalable, and excels at handling imbalanced datasets with advanced regularization techniques. 

LightGBM 
LightGBM is optimized for speed and memory efficiency, making it ideal for large datasets and high-dimensional features and we have tuned this model using Grid Search  

This model uses GridSearchCV to optimize the LightGBM Classifier by tuning max_depth (tree depth) and learning_rate (step size) to achieve the best performance based on the F1-score, ideal for imbalanced datasets. The parameter grid tested values of max_depth as -1 (unlimited) and 15 (moderate depth), and learning_rate as 0.1 and 0.3. Using 5-fold cross-validation ensures robust evaluation, while parallel processing (n_jobs=-1) accelerates computation. The best model, identified through the search, balances precision and recall effectively and is ready for evaluation on unseen test data. This approach ensures the classifier is fine-tuned for maximum reliability and performance in real-world scenarios. 

Voting Classifier Method 
The Voting Classifier combines the strengths of multiple weak models to improve overall accuracy and reduce variance in predictions. 
