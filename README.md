# Machine Learning Final Project - Problematic Internet Use 💻 

## Our Group: Team Mong
- **Lai Hoang Hiep** - 22028295  
- **Hoang Duc Duong** - 22028259  
- **Pham Mai Anh** - 22028225  

---

## Introduction  
This repository showcases the collaborative efforts of Team Mong in the Kaggle competition, focusing on predicting problematic internet usage among young individuals.  

**Kaggle Competition**: [Child Mind Institute — Problematic Internet Use](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use)

---

## Problem  
The primary goal of this competition is to predict the **Severity Impairment Index (SII)** using the provided training data.  
The target variable is derived from the field `PCIAT-PCIAT_Total`. Our task involves training a model on the given features to accurately predict the **SII**.

---

## Solution  

### Machine Learning Techniques  
Machine Learning techniques mentioned in the presentation, summarized below:

- **Data Processing**:  
  - Remove NaN columns.  
  - Fill missing values with constants using `SimpleImputer` and KNN Imputation with `KNNImputer`.  
  - Remove outliers and engineer features (e.g., pulse pressure, fat-to-muscle ratio).  

- **Modeling**:  
  - Tree-based algorithms: Random Forest, LightGBM, LGBM Regressor, XGBoost, and CatBoost.  

- **Optimization**:  
  - Grid Search, Bayesian Optimization, K-Fold Cross-Validation, and threshold rounding.  

- **Feature Extraction**:  
  - Correlation-based feature removal.  
  - Neural network encoder-decoder for time-series data.  

- **Evaluation**:  
  - Confusion matrix, `classification_report`, and Quadratic Weighted Kappa (QWK).

---

### Highlighted Versions  

Our work included approximately 40 versions, with three key milestones:

1. **Baseline**  
   - **Data**:  
     - Drop unlabeled records.  
     - Remove columns with >50% missing values.  
     - Fill missing values with -1.  
     - Process Parquet data by averaging columns and merging into a CSV by ID.  
     - Split data: 80% training, 20% testing.  
   - **Metric**: Evaluate with confusion matrix and `classification_report`.  
   - **Model**: Random Forest with Grid Search for hyperparameter tuning.  
   - **Result**:  
     - Strong bias toward class 0.  
     - Poor handling of classes 1 and 2.  
     - Imbalanced predictions and suboptimal scores.

2. **1st Improvement**  
   - **Data**: Replace missing values using the KNN algorithm.  
   - **Metric**: Evaluate with confusion matrix and `classification_report`.  
   - **Model**: LightGBM with L1/L2 regularization and early stopping.  
   - **Result**:  
     - Improved accuracy for minority classes.  
     - Submission scores highlighted potential issues with feature selection or evaluation.

3. **2nd Improvement (Final Version)**  
   - **Data**: Retain previous processing but engineer new features (e.g., pulse pressure, fat-to-muscle ratio).  
   - **Metric**: Evaluate with confusion matrix, `classification_report`, and QWK.  
   - **Model**:  
     - LGBM Regressor for ordinal classification.  
     - Threshold rounding.  
     - K-Fold Cross-Validation.  
     - Bayesian Optimization for hyperparameters.  
   - **Result**:  
     - Significant improvement in submission scores.  
     - Achieved a private test score of **0.439** and a bronze medal rank (364).  

---

### Performance of Final Version  

| **Metric**         | **Train**    | **Test**     |  
|---------------------|--------------|--------------|  
| Weighted Kappa      | 0.8167       | 0.5407       |  

![Final Version Screenshot](https://github.com/user-attachments/assets/3dbfc366-fc83-4189-9b65-da839e8d36ab)

---

### Repository Structure  

- `FINAL: 2nd-Improvement.ipynb`: The final version submitted to the competition.  
- `Baseline.ipynb`: Baseline version.  
- `1st-Improvement.ipynb`: 1st improvement version.  
- `Other`: Additional high-scoring versions not submitted.  

---

## Conclusion  

Through dedicated teamwork and independent implementation, Team Mong developed and tested 46 versions to achieve a rank of **364** with an official private score of **0.439**, equivalent to a bronze medal. We are proud of our originality and understanding, ensuring that all solutions were implemented with integrity while drawing inspiration from existing ideas.
