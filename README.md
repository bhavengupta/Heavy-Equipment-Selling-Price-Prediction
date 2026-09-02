# Heavy-Equipment-Selling-Price-Prediction

## Overview

An end-to-end machine learning project for predicting the transaction value of heavy equipment from structured historical data. The project focuses on robust preprocessing, feature engineering, categorical feature handling, model comparison, and hyperparameter optimization for tabular regression.

## Technical Approach

Exploratory Data Analysis
Analyzed dataset dimensions, feature types, descriptive statistics, missing-value patterns, cardinality, and target distribution.
Examined numerical relationships and target skewness to guide preprocessing and feature engineering decisions.
Removed features with excessive missingness and identifier columns that were not useful for prediction.
Feature Engineering

## Created domain-informed features including:

EquipmentAge from transaction year and manufacture year.
UsagePerYear from operational hours and equipment age.
Frequency-based features for high-cardinality categorical variables.
Temporal features from TransactionDate, including year, month, day, quarter, day of week, and day of year.
Equipment attribute indicators such as cabin and fork availability.
Specification hierarchy features combining base and subclass information.
Ordinal representation of AssetScaleFactor based on its natural ordering.
Preprocessing

## Implemented a reusable scikit-learn preprocessing pipeline using ColumnTransformer.

Numerical features: median imputation.
Low-cardinality categorical features: most-frequent imputation + One-Hot Encoding.
High-cardinality categorical features: most-frequent imputation + Ordinal Encoding with explicit handling of unseen categories.
Target: log1p transformation to reduce skewness and align the training objective with RMSLE-based evaluation.
Model Development

## Compared three regression approaches:

Linear Regression — baseline linear model.
Random Forest Regressor — ensemble of decision trees using bagging to capture nonlinear relationships.
XGBoost Regressor — gradient-boosted decision trees used as the final model.

Random Forest hyperparameters were optimized using 3-fold GridSearchCV. XGBoost was tuned iteratively across parameters including tree depth, learning rate, number of estimators, row/column subsampling, minimum child weight, and L1/L2 regularization.

## Final Model

The final XGBoost configuration used histogram-based tree construction along with controlled tree complexity, subsampling, column sampling, and regularization. After validation, the model was retrained on the complete training dataset before generating test predictions.

## Results

Model	Validation RMSLE
Linear Regression	~0.451
Random Forest	~0.220
XGBoost	~0.200

Competition leaderboard RMSLE: 0.19656

## Tech Stack
Python · Pandas · NumPy · Scikit-learn · XGBoost · Matplotlib
