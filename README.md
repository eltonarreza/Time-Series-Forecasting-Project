# Time Series Forecasting Project

## Contents

This repository contains a time series forecasting project using multiple modeling approaches, including Facebook Prophet, classical regression models, LightGBM, and hybrid methods. The focus is on predicting product sales across different stores using historical data.

### Data

- `train.csv`: Daily historical sales data for each store-product pair from 2010 to 2018.
- `test.csv`: Data for 2019, used for testing the models.

---

## EDA (Exploratory Data Analysis)

Performed general exploratory data analysis to investigate:

- Trends and seasonality in the time series data.
- Differences in sales patterns across different `(store, product)` pairs.

**Key Insight**: Time series behavior varies significantly across different store/product combinations, indicating the need for per-group modeling or flexible models.

---

## Prophet Model

- Used Facebook Prophet to train forecasting models on each `(store, product)` pair.
- Fine-tuned Prophet hyperparameters using a manual grid search.
- Forecasts evaluated on the `test.csv` set using RMSE.

---

## Regression Models

Developed and evaluated several regression-based forecasting models:

- **Ridge Regression**
  - GridSearchCV fine-tuning
  - Hyperopt fine-tuning
- **Random Forest Regressor**
  - GridSearchCV fine-tuning
  - Hyperopt fine-tuning
- **LightGBM Regressor**
  - Hyperopt fine-tuning with early stopping

All models were evaluated using RMSE metric.

---

## Hybrid Models

Two hybrid strategies were implemented:

1. **Weighted Average Ensemble**
   - Combined predictions from the best regression model and Prophet using a weighted average.
2. **Stacked Model**
   - Used Prophet model predictions as an input feature for a regression model.

---

## MLflow Integration

### Prophet Model with MLflow
- Converted the Prophet modeling process into a script.
- Tracked model parameters, metrics, and artifacts using MLflow.

### Regression Models with MLflow
- Replicated the regression modeling process in script form.
- Tracked model parameters, metrics, and artifacts using MLflow.
