## Summary of what I did and what it means

I built two models on this data.

**Model 1: Linear Regression to predict MonthlyCharges**
This model got an R2 of 0.999 which is almost perfect. This makes sense because monthly charges are mostly just based on which services a customer has like internet type, phone, and streaming. It is not really a prediction model in a useful sense, it is more like it confirms the pricing structure of the company. It could maybe be used to check if a customer bill looks wrong compared to what they actually pay for.

**Model 2: Logistic Regression to predict Churn**
This is the more useful model out of the two. I used StandardScaler to fix a convergence warning and I used class_weight balanced to catch more churners. Final model has recall of 0.78 for the churn class and ROC AUC of 0.84.

From the feature importance chart, tenure is the biggest reason someone stays. Longer customers churn less. Contract_TwoYear also helps keep customers. On the other side, InternetService_FiberOptic is the biggest reason someone churns.

**What the retention team could do with this**
They could run this model every month on active customers and use predict_proba to get a churn risk score instead of just yes or no. Then they can focus on the highest risk customers first, especially new customers, month to month contract customers, and fiber optic customers. This way they are not wasting time on customers who are already going to stay.