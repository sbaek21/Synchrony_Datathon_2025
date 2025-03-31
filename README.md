# Synchrony_Datathon_2025
Link to video: https://youtu.be/K3RXS6xk-6U
# Financial Data Feature Engineering and Forecasting

## Overview

This repository contains Jupyter notebooks:
1. **`feature_engineering.ipynb`**: Prepares enriched account-level features for financial data analysis, including fraud detection and forecasting.
2. **`forecast.ipynb`**: Implements a hybrid forecasting model combining machine learning (XGBoost) and time-series techniques (ARIMA) to predict quarterly spending.
3.  **Autoencoder_Team101.ipynb**: Implement the autoencoder model to detect the anomalies in the dataset using the risk features.
4.  **Clusster.ipynb**: Implement the credit line increase prediction model using the feature engineered dataset using both cluster model and regression model.

---

## Notebooks Description

### 1. `feature_engineering.ipynb`
This notebook processes raw financial data from multiple sources to create enriched features for downstream analysis:
- **Data Sources**:
  - Account information, transactions, statements, fraud claims, and world transactions.
- **Key Features Created**:
  - Velocity and acceleration metrics for quarterly spending.
  - Fraud risk scores based on delinquency trends, utilization rates, and credit grades.
  - Cash flow metrics such as cash-to-debt ratio and buffer ratios.
  - Customer lifecycle segmentation (e.g., New, Established, Mature accounts).
- **Output**: A CSV file (`enriched_account_information.csv`) containing all processed features.

### 2. `forecast.ipynb`
This notebook predicts quarterly spending using a hybrid ensemble model:
- **Feature Engineering**:
  - Extracts rolling averages, lagged spending values, and growth rates from historical data.
- **Modeling Approach**:
  - Base model: XGBoost regressor trained on all accounts.
  - Segment models: Separate XGBoost models trained on account segments (e.g., high-volatility or high-utilization accounts).
  - Time-series adjustment: ARIMA forecasts integrated with machine learning predictions for enhanced accuracy.
- **Output**: A CSV file (`q4_spending_forecast.csv`) with predicted spending values for Q4.

### 'Autoencoder_Team101.ipynb'
This notebook utilizes the autoencoder model to detect the anomalies
- **Anomaly Detection**:
- Use an autoencoder-based model to detect the anomalies in the dataset
- **Evalutation**:
- Use Euclidean Distance and a scatter plot to evaluate the results that the model predicted. The Euclidean distance shows how close each data point is to each others.

---

## Installation

To run the notebooks, install the required Python packages:

pip install -r requirements.txt
