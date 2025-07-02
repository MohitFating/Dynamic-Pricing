Hotel Pricing Prediction Model
________________________________________
Hotel Pricing Prediction - Model Documentation
Overview
This project focuses on predicting hotel room prices using machine learning, specifically comparing XGBoost and Random Forest regressors. It includes:
• Data preprocessing
• Hyperparameter tuning using Optuna
• Model training & evaluation
• Feature importance analysis
________________________________________
1. Model Setup & Libraries
Key libraries used:
• scikit-learn, xgboost, lightgbm
• optuna for hyperparameter optimization
• matplotlib, pandas, numpy for data manipulation and visualization
________________________________________
2. Hyperparameter Tuning with Optuna
XGBoost model was tuned over 50 trials using TPESampler. The objective was to minimize Mean Absolute Error (MAE) via 5-fold cross-validation.
Best Parameters Found:
{
  "n_estimators": 851,
  "max_depth": 5,
  "learning_rate": 0.0268,
  "subsample": 0.632,
  "colsample_bytree": 0.689,
  "min_child_weight": 1,
  "reg_alpha": 0.200,
  "reg_lambda": 0.963
}
Best XGBoost MAE during tuning: 49.70
________________________________________
3. Final Model Training
Two models were trained:
• XGBoost (best-tuned)
• Random Forest (baseline with 100 estimators)
________________________________________
4. Performance Comparison
Metric	XGBoost	Random Forest
MAE	36.19	51.28
RMSE	48.17	79.97
R² Score	0.9977	0.9938
MAPE	1.60%	2.20%
Winner: XGBoost
Visual (suggested):
A bar chart comparing MAE and RMSE values between the models.
________________________________________
5. Feature Importance
Top 10 impactful features (based on model importance scores) were visualized for both models.
Notable Features:
• room_type
• check-in day
• booking lead time
________________________________________
6. Summary & Takeaways
• Hyperparameter tuning with Optuna significantly improved XGBoost’s performance.
• XGBoost outperformed Random Forest on all metrics.
• Understanding feature importance is essential for model explainability and real-world deployment.
________________________________________