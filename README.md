# Retail Sales Forecasting

# Project Overview

Business Problem: Forecast weekly retail sales across multiple stores.
Objective: Build a model to predict sales using historical data & external factors (holidays, CPI, unemployment, etc.).
End Goal: Help management in planning, staffing, and inventory decisions.

# Dataset Description

| Column         | Description                                           |
| -------------- | ----------------------------------------------------- |
| Store          | Store ID (categorical)                                |
| Date           | Date of observation                                   |
| Weekly\_Sales  | Target variable – sales for the given week & store    |
| Holiday\_Flag  | Whether the week had a holiday (1 = holiday, 0 = not) |
| Temperature    | Temperature in the region                             |
| Fuel\_Price    | Fuel price in the region                              |
| CPI            | Consumer Price Index                                  |
| Unemployment   | Unemployment rate                                     |
| year, month... | Extracted time-based features                         |
| is\_weekend    | Derived binary feature (1 if weekend, else 0)         |

# Exploratory Data Analysis (EDA)

Trend Analysis: Sales increase in November–December (holiday shopping season).
Seasonality: Weekly sales show spikes near major US holidays (Thanksgiving, Christmas).
Correlations: CPI and Unemployment slightly negatively correlated with sales.
Store-Level Insights: Some stores consistently outperform others.

📊 Used Plotly for interactive graphs:
Time series plots of sales
Store-wise comparison
Holiday vs Non-Holiday sales
Heatmaps of correlations

# Feature Engineering

Date converted to year, month, week, dayofweek, is_weekend.
Store encoded (if categorical).
Created lag features (previous week’s sales) — optional for advanced models.

# Modeling

| Model             | RMSE    | MAE     | R²     |
| ----------------- | ------- | ------- | ------ |
| Linear Regression | 497,566 | 417,462 | 0.13   |
| Random Forest     | 165,499 | 94,654  | 0.90   |
| Gradient Boosting | 132,198 | 100,095 | 0.94   |
| XGBoost           | 120,511 | 90,722  | 0.95 ✅ |

# Conclusion

XGBoost is the best model (R² = 0.95).
Model captures seasonality & holiday effects well.
Deployed API enables real-time sales forecasting.

# Future Work

Add deep learning models (LSTM, Prophet) for time-series forecasting.
Include external factors (promotions, competitor pricing).
Build interactive dashboard for business users.
