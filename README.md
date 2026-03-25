# 🚗 Web Scraping OLX Jakarta & Car Price Prediction Modeling

## 📌 Project Overview

This project aims to develop a **machine learning model to predict used car prices in Indonesia** using data collected from OLX Jakarta through web scraping. The dataset captures a highly diverse range of vehicles, from affordable entry-level sedans such as the **Honda City (~65M IDR)** to premium luxury SUVs like the **Toyota Land Cruiser (~2.5B IDR)**.

Such a wide price distribution introduces significant challenges in modeling, particularly in terms of:
- Handling **high variance and outliers**
- Ensuring **model generalization across different market segments**
- Capturing **non-linear relationships in heterogeneous data**

The goal of this project is not only to build an accurate predictive model, but also to understand the **limitations of global models** and explore strategies to improve real-world applicability.

---

## 🔎 Exploratory Data Analysis (EDA)

A comprehensive exploratory analysis was conducted to uncover patterns in the Indonesian used car market.

### Key Findings:

- **Market Dominance**
  - **Toyota** emerges as the most dominant brand in both listing frequency and model variety.
  - This reflects strong brand trust and resale value in the Indonesian market.

- **Fuel Type & Transmission Preferences**
  - Consumers show a strong preference for **automatic transmission vehicles**.
  - **Petrol-powered cars dominate**, while diesel, hybrid, and electric vehicles remain niche.
  
- **Mileage Distribution**
  - Most vehicles fall within the **low-to-medium mileage range**, indicating buyer preference for relatively well-maintained used cars.

- **Emerging Trends**
  - Although still limited, there is a gradual increase in **hybrid and electric vehicle adoption**, suggesting early market transition.

---

## 🧪 Model Development & Experimentation

To identify the most suitable predictive model, multiple regression algorithms were benchmarked:

- Linear Regression
- Support Vector Regression (SVR)
- Decision Tree Regressor
- XGBoost Regressor
- Ridge Regression

---

### 🔹 Before Hyperparameter Tuning

Initial model evaluation revealed:

- **Ridge Regression achieved the best performance**
  - Test RMSE: **144M IDR**
  - Demonstrated strong **generalization capability**
  - Robust against multicollinearity

- **Tree-based models (Decision Tree, XGBoost)**
  - Achieved very low training error
  - Showed clear signs of **overfitting**

- **Linear & SVR models**
  - Underperformed due to inability to capture complex relationships in data

---

### 🔹 After Hyperparameter Tuning

Hyperparameter optimization was performed on the Ridge model:

```python
{
  'alpha': 0.774,
  'fit_intercept': True,
  'max_iter': 1000,
  'solver': 'auto',
  'tol': 0.001
}
