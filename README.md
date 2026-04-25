# 🧬 Metabolic Syndrome Classification

## 📌 Overview
This project tackles the **Metabolic Syndrome Challenge**, where the objective is to predict whether a patient is at risk (`1`) or not (`0`) using clinical features.

---

## 🎯 Objectives
- Build and compare two classification models:
  - k-Nearest Neighbors (kNN)
  - Naive Bayes (NB)
- Perform robust preprocessing:
  - Handle missing values
  - Encode categorical variables
  - Scale numerical features (for kNN)
- Optimize models using hyperparameter tuning
- Evaluate using:
  - Confusion Matrix
  - Accuracy, Precision, Recall, F1-score, Specificity
  - ROC Curve & AUC
- Achieve strong ROC-AUC performance on Kaggle leaderboard

---

## 🧠 Project Pipeline

```text
Raw Data
   ↓
Data Cleaning (missing values, outliers)
   ↓
Feature Encoding (OneHotEncoder)
   ↓
Train / Validation Split
   ↓
Model Pipelines (kNN & NB)
   ↓
Hyperparameter Tuning (GridSearchCV)
   ↓
Evaluation (Metrics + ROC-AUC)
   ↓
Final Model Selection
   ↓
Test Prediction → submission.csv
```

---

## ⚙️ Models

### 1. k-Nearest Neighbors (kNN)
- Instance-based learning
- Distance-driven classification
- Sensitive to feature scale

**Tuned Parameters:**
- `n_neighbors` (k)
- `metric` (euclidean / manhattan)

---

### 2. Naive Bayes (GaussianNB)
- Probabilistic classifier
- Based on Bayes’ Theorem
- Assumes feature independence

**Tuned Parameter:**
- `var_smoothing`

---

## ⚠️ Key Data Challenges

- Missing values in clinical variables
- Different feature scales (critical for kNN)
- Outliers affecting distance calculations
- Correlated features (violates NB independence assumption)
- Possible class imbalance

---

## 📊 Evaluation Metrics

Models are evaluated using:

- Confusion Matrix (TP, TN, FP, FN)
- Accuracy
- Precision
- Recall (Sensitivity)
- Specificity
- F1-score
- ROC Curve
- AUC (Area Under Curve)

> **Primary metric: ROC-AUC**

Accuracy alone is not reliable, especially with imbalanced data.

---

## 🧪 Model Selection Strategy

Naive Bayes assumes:
> Features are independent

In this dataset:
- Clinical features are often correlated (e.g., BMI, glucose)

This leads to:
- Imperfect probability estimates

However:
- NB often performs well in **ROC-AUC**
- kNN is sensitive to noise and scaling

Final model is selected based on:
> **Validation ROC-AUC performance**

---