# 🚜 Heavy Equipment Selling Price Prediction

An end-to-end **machine learning regression project** focused on predicting the transaction value of heavy equipment using historical structured data, with emphasis on feature engineering, robust preprocessing, model comparison, and hyperparameter optimization.

🏆 Achieved a **Competition Leaderboard RMSLE of 0.19656** using an optimized XGBoost regression model.

---

## 📌 Overview

This project focuses on predicting the selling price of heavy equipment from historical transaction data.

The workflow covers the complete machine learning pipeline — from **exploratory data analysis and feature engineering to preprocessing, model selection, hyperparameter tuning, and final prediction generation**.

The project emphasizes handling real-world tabular data challenges such as missing values, high-cardinality categorical variables, temporal features, and skewed target distributions.

---

## 🏆 Achievement

* Achieved **0.19656 RMSLE** on the competition leaderboard
* Developed an end-to-end tabular regression pipeline
* Compared multiple machine learning regression approaches
* Applied feature engineering based on equipment and transaction characteristics
* Optimized the final model using iterative hyperparameter tuning

---

## 🚀 Features

* 📊 Exploratory data analysis and target distribution analysis
* 🔧 Domain-informed feature engineering
* 🧹 Robust missing-value handling
* 🔤 One-Hot and Ordinal Encoding for categorical variables
* 📅 Temporal feature extraction from transaction dates
* 🌲 Multiple regression model comparison
* ⚙️ Hyperparameter optimization using GridSearchCV
* 🚀 XGBoost-based final prediction model
* 📈 RMSLE-based model evaluation
* 🔄 Reusable scikit-learn preprocessing pipeline

---

## 🧠 Feature Engineering

Created domain-informed features to improve predictive performance:

* **EquipmentAge** — calculated using transaction year and manufacture year
* **UsagePerYear** — operational hours normalized by equipment age
* **Frequency Encoding** — applied to high-cardinality categorical features
* **Temporal Features** — extracted year, month, day, quarter, day of week, and day of year from `TransactionDate`
* **Equipment Indicators** — represented attributes such as cabin and fork availability
* **Specification Hierarchy** — combined base and subclass equipment information
* **Ordinal Features** — represented `AssetScaleFactor` according to its natural ordering

---

## ⚙️ Preprocessing

Implemented a reusable preprocessing pipeline using **scikit-learn `ColumnTransformer`**.

### Numerical Features

* Median imputation

### Low-Cardinality Categorical Features

* Most-frequent imputation
* One-Hot Encoding

### High-Cardinality Categorical Features

* Most-frequent imputation
* Ordinal Encoding
* Explicit handling of unseen categories

### Target Transformation

Applied `log1p` transformation to the target variable to reduce skewness and better align the training objective with **RMSLE evaluation**.

---

## 🤖 Model Development

Three regression approaches were evaluated:

| Model             | Validation RMSLE |
| ----------------- | ---------------: |
| Linear Regression |           ~0.451 |
| Random Forest     |           ~0.220 |
| XGBoost           |           ~0.200 |

### Models Used

**Linear Regression**

Used as a baseline model to establish initial predictive performance.

**Random Forest Regressor**

Used to capture nonlinear relationships through an ensemble of decision trees.

**XGBoost Regressor**

Used as the final model due to its strong performance on structured/tabular data.

---

## 🔬 Hyperparameter Optimization

### Random Forest

Optimized using **3-Fold GridSearchCV**.

### XGBoost

Iteratively tuned across parameters including:

* Tree depth
* Learning rate
* Number of estimators
* Row subsampling
* Column subsampling
* Minimum child weight
* L1 regularization
* L2 regularization

The final XGBoost configuration used **histogram-based tree construction**, controlled tree complexity, subsampling, column sampling, and regularization.

---

## 📈 Results

The models showed significant improvement as model complexity and nonlinear learning capabilities increased.

**Validation Performance:**

* Linear Regression → **~0.451 RMSLE**
* Random Forest → **~0.220 RMSLE**
* XGBoost → **~0.200 RMSLE**

🏆 **Final Competition Leaderboard RMSLE: 0.19656**

XGBoost provided the strongest performance and was retrained on the complete training dataset before generating final test predictions.

---

## 🛠️ Tech Stack

### Programming Language

* Python

### Data Processing & Analysis

* NumPy
* Pandas

### Machine Learning

* Scikit-learn
* XGBoost

### Visualization

* Matplotlib

---

## 📊 Methodology

The overall workflow followed:

```text
Raw Dataset
     ↓
Exploratory Data Analysis
     ↓
Data Cleaning
     ↓
Feature Engineering
     ↓
Categorical & Numerical Preprocessing
     ↓
Target Transformation
     ↓
Model Comparison
     ↓
Hyperparameter Optimization
     ↓
Model Validation
     ↓
Final XGBoost Model
     ↓
Test Prediction
```

---

## 💡 Applications

The techniques used in this project can be applied to:

* 🚜 Heavy equipment price estimation
* 💰 Used equipment valuation
* 📊 Market price analysis
* 📈 Asset valuation
* 🔮 Transaction price prediction
* 🏗️ Construction equipment analytics

---

## 👨‍💻 Author

Developed by **Bhaven Gupta**

If you found this project useful, consider giving it a ⭐ on GitHub.

**© 2026 Bhaven Gupta. All Rights Reserved.**


