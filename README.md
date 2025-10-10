# Bitcoin Price Prediction

This project focuses on **predicting Bitcoin’s daily market price** using data from the **previous 3 days**.  
It explores a variety of statistical and machine learning models to understand how key blockchain and network variables influence Bitcoin’s price dynamics.

---

## 🧭 Objective

- Predict **Bitcoin market price** for a given day using lag features (1-day, 2-day, 3-day lags).  
- Compare multiple modeling techniques to capture both linear and nonlinear relationships.  
- Address issues such as **multicollinearity**, **scaling**, and **feature interactions**.

---

## 📊 Dataset Overview

- Historical Bitcoin data including metrics such as:
  - `btc_market_price` (target)
  - `btc_trade_volume`
  - `btc_market_cap`
  - `btc_difficulty`
  - `btc_hash_rate`
  - `btc_miners_revenue`
  - `btc_transaction_fees`
  - `btc_total_bitcoins`, and others.
- Data cleaning included removing rows with missing values or zero market price.
- Lag features were generated for each variable (1, 2, and 3 days).
- Final dataset prepared for supervised learning with:
  - `X` = past 3 days’ features
  - `y` = next day’s Bitcoin price

---

## ⚙️ Data Processing Steps

1. **Cleaning** – remove invalid or missing observations.  
2. **Feature Engineering** – generate lag-1, lag-2, and lag-3 versions of features.  
3. **Scaling** – standardize numeric variables for regularized models.  
4. **Train/Test Split** – use the first 80% of data for training and the last 20% for testing.  
5. **Target Transformation** – apply log transformation to stabilize price variance in some models.

---

## 🤖 Models Implemented

The project evaluates multiple models to balance bias–variance trade-off and handle multicollinearity:

### 1. **Linear Models**
- **Ordinary Least Squares (OLS)** – baseline linear regression model.  
- **Ridge Regression** – L2-regularized model to handle multicollinearity.  
- **Lasso Regression** – L1-regularized model for feature selection.  

### 2. **Transformed & Polynomial Models**
- **Log-transformed Response Model** – predicts `log(price)` to reduce skewness and stabilize variance.  
- **Polynomial Regression** – adds nonlinear interaction terms to capture complex feature relationships.

### 3. **Tree-Based Models**
- **Decision Tree Regressor** – interpretable nonlinear model to capture threshold effects.  
- **Random Forest Regressor** – ensemble of trees to improve generalization and reduce overfitting.

---

## 🧪 Model Evaluation

Each model was assessed using:
- **Train/Test split** based evaluation  
- **RMSE** and **R²** metrics (where applicable)  
- Visual inspection of predicted vs. actual prices
- Fitted vs Residual plot

