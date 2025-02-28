# Machine Learning Final Project - Problematic Internet Use 💻

## Our group: Team Mong

- **Lai Hoang Hiep** - 22028295  
- **Hoang Duc Duong** - 22028259  
- **Pham Mai Anh** - 22028225  

---

## 📃 Introduction

This repository showcases the collaborative efforts of our team in the Kaggle competition, focusing on predicting problematic internet usage among young individuals.  
**Kaggle Competition**: [Child Mind Institute — Problematic Internet Use](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use)

---

## 🔍 Problem

The main aim of this competition is to use the given training data to predict the **Severity Impairment Index (SII)**.  
The target variable is originally derived from the field **PCIAT-PCIAT_Total**. Our task is to train a model based on other features to predict **SII** effectively.

---

## 🚀 Solution

### Machine Learning Techniques

#### Data Processing
- Remove NaN columns.
- Fill missing values with a constant (using `SimpleImputer` from sklearn).
- KNN Imputation (`KNNImputer` from sklearn).
- Remove outliers.
- Feature engineering (e.g., pulse pressure, fat-to-muscle ratio).
- Correlation-based feature removal.
- Neural network encoder-decoder for time-series data.

#### Modeling
- Tree-based algorithms: Random Forest, LightGBM, LightGBM Regressor, XGBoost, CatBoost.
- Optimization: Grid Search, Bayesian Optimization, K-Fold Cross-Validation, threshold rounder optimization.

#### Evaluation
- `confusion_matrix`,`classification_report` from `sklearn`
- Quadratic Weighted Kappa (QWK).

### Three Highlighted Versions

We developed our models with approximately 40 versions, marked by 3 outstanding milestone versions.  

#### 1. Baseline
- **Data**: Drop unlabeled records, remove columns with >50% missing values, fill missing values with -1, process Parquet data by averaging columns and merging into CSV by ID, and split data into 80% training, 20% testing.
- **Metric**: Evaluate with `confusion_matrix`,`classification_report` from `sklearn`
- **Model**: Random Forest with grid search for hyperparameter tuning.
- **Result**: Model shows strong bias toward class 0, struggles with class 1 and 2, and demonstrates prediction imbalance; accuracy and scores indicate room for improvement.

#### 2. 1st Improvement
- **Data**: Replace missing values using the KNN algorithm. Use an adversarial neural network with an encoder-decoder structure.
- **Metric**: Evaluate with `confusion_matrix`,`classification_report` from `sklearn`
- **Model**: Implement LightGBM. Use L1/L2 regularization and early stopping to mitigate overfitting.
- **Result**: Improved accuracy with better focus on minority classes (class 1). However, submission scores remain low, highlighting potential issues with feature usage or evaluation strategies.

#### 3. 2nd Improvement (Final Version)
- **Data**: Retain the previous data processing approach but engineer new features (e.g., pulse pressure, fat-to-muscle ratio) based on medical metrics to enhance feature informativeness.
- **Metric**: Evaluate with `confusion_matrix`,`classification_report` from `sklearn`, and Quadratic Weighted Kappa (QWK) as the optimization metric.
- **Model**: LGBMRegressor for ordinal classification, implement threshold rounding, apply K-Fold Cross-Validation for generalization, and optimize hyperparameters using Bayesian Optimization.
- **Result**: Submission scores improve significantly, achieving the highest private test score and a bronze medal rank (364). Model shows improved awareness of ordinal class relationships, reducing extreme misclassifications.

---

## 🎯 Performance of Final Version

| Metric                    | Value                  |
|---------------------------|------------------------|
| **Weighted Kappa (test)** | `0.5407461505690463`   |
| **Weighted Kappa (train)**| `0.8167463778309185`   |

![Performance Chart](https://github.com/user-attachments/assets/3dbfc366-fc83-4189-9b65-da839e8d36ab)

---

## 🗂 Repository Structure

1. **FINAL**: `2nd-improvement.ipynb`: The final version submitted to the Kaggle competition.
2. **Other Versions**:
   - `Baseline.ipynb`: Baseline version.
   - `1st-Improvement.ipynb`: 1st improvement version.
   - **Other**: Notable versions implemented with high scores but not submitted.

---

## 🏆 Conclusion

Our hard work and dedication are reflected in the results. After implementing 46 versions, we achieved a rank of 364 with an official private score of **0.439**, achieving the bronze medal.  
We are especially proud that all of our work was implemented independently. While we explored ideas from others for inspiration, we ensured a thorough understanding and executed everything ourselves, staying true to our commitment to originality and integrity.
