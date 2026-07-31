# teleco-churn-prediction
# Telco Customer Churn Prediction

This project is my practice with regression and classification models using the Telco Customer Churn dataset.

## What I did
- Cleaned and prepared the data (fixed data types, encoded categorical columns)
- Built a Linear Regression model to predict MonthlyCharges (R2 = 0.999)
- Built a Logistic Regression model to predict Churn
- Used StandardScaler to fix a convergence warning on the logistic regression
- Used class_weight balanced to improve recall on the churn class
- Looked at feature coefficients to see which features matter most for both models
- Compared precision and recall and picked the better metric for this business case

## Results
- Regression model R2: 0.999
- Classification model recall (churn class): 0.78
- Classification model ROC AUC: 0.84

## Dataset
[Telco Customer Churn dataset](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)

## What I learned
Scaling matters a lot for logistic regression because it uses an iterative solver, but it does not matter for linear regression. Also accuracy is not always the best metric to look at. For this churn problem, recall mattered more than precision because missing a churner costs more than a false alarm.
