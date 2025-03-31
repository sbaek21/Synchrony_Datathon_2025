
## **Team 101**  
📽️ _Link to presentation video: **[https://youtu.be/K3RXS6xk-6U]**_

---

## 📌 Overview

This project focuses on preparing enriched financial features and applying various machine learning techniques for forecasting, anomaly detection, and credit limit analysis. It includes four major components:

1. **`feature_engineering.ipynb`** – Generate account-level financial features.
2. **`forecast.ipynb`** – Predict quarterly spending using XGBoost and ARIMA.
3. **`Autoencoder_Team101.ipynb`** – Detect anomalies using autoencoders.
4. **`Cluster.ipynb`** –  Perform customer segmentation (clustering + PCA) and build a regression model to predict credit line adjustments.

---
## ⚙️ Setup & Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Jeybird248/Synchrony_Datathon_2025.git
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Start Jupyter**:
   ```bash
   jupyter notebook
   ```

---

## 📂 Notebooks Description

### `feature_engineering.ipynb`
- **Goal**: Prepare clean and enriched features from multiple raw financial datasets.
- **Data Sources**:  
  - `account_dim`, `transaction_fact`, `statement_fact`, `fraud_claim_case`, `wrld_stor_tran_fact`
- **Output**: `enriched_account_information.csv`

---

### `forecast.ipynb`
- **Goal**: Forecast Q4 spending using hybrid models.
- **Models Used**:
  - `XGBoost` for regression  
  - `ARIMA` for time-series forecasting  
  - Combined for better accuracy in volatile segments
- **Output**: `q4_spending_forecast.csv`

---

### `Autoencoder_Team101.ipynb`
- **Goal**: Detect account-level anomalies using risk-related features.
- **Approach**:
  - Build a deep autoencoder model
  - Evaluate reconstruction loss (Euclidean distance)
- **Output**:
  - Anomaly scores with scatter plot visualization

---

### `Cluster.ipynb`
- **Goal**: Segment customers using clustering and PCA, and predict credit line adjustments using regression.

#### Part 1: Customer Segmentation (Classification Model)
- PCA used to reduce dimensionality of numeric risk and spending features
- K-Means clustering applied to identify distinct customer segments
- Customers categorized into four key groups:
  - High Spending, High Risk
  - High Spending, Low Risk
  - Low Spending, High Risk
  - Low Spending, Low Risk

#### Part 2: Credit Line Adjustment Prediction (Regression Model)
- Linear regression trained using both selected and full numeric features
- Performance evaluated with metrics such as R², MAE, RMSE, and MAPE
- Helped identify feature importance and risk-adjusted recommendations

---



## 📊 Results Summary

### Clustering & Segmentation

- PCA Visualization and K-Means Clustering used to segment customers based on risk and spending scores.
- Segmentation resulted in four clear customer groups:
  - High Spending, High Risk  
  - High Spending, Low Risk  
  - Low Spending, High Risk  
  - Low Spending, Low Risk  
- Plots included in results show distinct cluster separations and insights into customer profiles.


### Regression Performance

| Model Type           | MAE     | RMSE    | R² Score | MAPE   |
|----------------------|---------|---------|----------|--------|
| Selected Features    | 192.98  | 421.20  | 0.9618   | 20.78% |
| All Numeric Features | 103.63  | 549.79  | 0.9919   | 6.09%  |


### Anomaly Detection: Effectively flagged outlier accounts with high reconstruction error.

### Clustering: Segmented users into meaningful groups such as *High Risk, Low Spending*, enabling personalized strategies.

---

## ✅ Key Takeaways
- Enriched features significantly improved prediction accuracy.
- Regression models are effective for estimating credit limits using spending and risk metrics.
- PCA and clustering provided interpretable customer segments useful for strategic targeting.
- Autoencoder helped identify anomalies that rule-based systems may miss.
- Feature selection vs. full feature modeling offered a balance between accuracy and interpretability.
