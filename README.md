
## 🚗 Web Scraping OLX Jakarta and Building Car Price Prediction Models

### 📌 Project Overview

This project aimed to **predict used car prices in Indonesia** using machine learning models. The dataset contained a wide range of vehicles — from affordable sedans like the **Honda City (65M IDR)** to premium SUVs like the **Toyota Land Cruiser (2.5B IDR)**. Such a diverse dataset posed unique challenges for building a generalizable predictive model.

### 🔎 Exploratory Data Analysis (EDA)

* **Toyota dominates** the Indonesian used car market in both brand and model presence.
* Buyers show a strong preference for **automatic and petrol-powered cars**, while diesel, hybrid, and EVs remain niche.
* Most cars listed had **low-to-medium mileage**, aligning with buyer expectations.
* A slow but noticeable rise of **hybrid and electric vehicles** is emerging in the market.

### 🧪 Model Experiments

I benchmarked multiple models — **Linear Regression, SVR, Decision Tree, XGBoost, and Ridge Regression** — to identify the best-performing approach.

#### **Before Hyperparameter Tuning**

* **Ridge Regression** outperformed all other models with the lowest **Test RMSE: 144M**, demonstrating strong generalization and robustness.
* Non-linear models (Decision Tree, XGBoost) showed signs of **overfitting**, while Ridge remained stable.

#### **After Hyperparameter Tuning**

* Optimized Ridge model with parameters:

  ```python
  {'alpha': 0.774, 'fit_intercept': True, 'max_iter': 1000, 'solver': 'auto', 'tol': 0.001}
  ```
* **Train RMSE improved to 122M**, but **Test RMSE worsened to 200M**, indicating reduced generalization.
* Key issue: **over-tuning led to higher variance**, sacrificing robustness.

### 📊 Key Insights

* **Ridge Regression was the most reliable model**, showing excellent generalization before tuning.
* The **high RMSE values** are largely due to the dataset’s **wide price range and presence of outliers** (e.g., luxury cars vs. budget cars).
* A single global model struggles to capture such diverse pricing patterns.

### 🛠️ Recommendations

1. **Expand Hyperparameter Search** – explore broader `alpha` values (log scale) and alternative solvers.
2. **Improve Cross-Validation** – adopt stratified or grouped CV with more folds for stable results.
3. **Segmented Modeling** – build brand-specific or segment-based models (luxury vs. economy, SUV vs. sedan) for more accurate predictions.
4. **Try ElasticNet** – balance Ridge’s stability with Lasso’s feature selection to improve bias-variance trade-off.

### ✨ Conclusion

This project highlights the challenges of **predicting car prices in highly diverse markets**. Ridge Regression provided the best baseline performance, but hyperparameter tuning introduced overfitting. The key learning is that **data segmentation and regularization strategies** are crucial for improving real-world predictive performance in heterogeneous datasets.

---

Would you like me to make this **shorter and more portfolio-style (like a 3–4 paragraph summary with highlights)** or keep it in this **detailed report format**?
