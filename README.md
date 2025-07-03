# Company Bankruptcy Prediction :

###  Using Logistic Regression and Support Vector Machine (SVM)

This project implements and compares two classification algorithms — Logistic Regression and Support Vector Machine (SVM) — for predicting company bankruptcy based on financial indicators. The objective is to assist in early risk identification by building models that can classify companies as **bankrupt (1)** or **not bankrupt (0)** using structured financial data.

---

## Dataset Overview

- **Source**: [UCI Machine Learning Repository – Taiwanese Bankruptcy Prediction](https://archive.ics.uci.edu/ml/datasets/Taiwanese+Bankruptcy+Prediction)
- **Instances**: 6819 companies
- **Attributes**: 95 financial indicators
- **Target Variable**: `Bankrupt?` (binary classification)
- **Nature**: Highly imbalanced (majority of samples are non-bankrupt)

---

## Project Pipeline

1. **Data Loading and Exploration**
   - Dataset dimensions, null value check, data summary statistics.
   - Class distribution visualized using seaborn.
   
2. **Preprocessing**
   - Dropping missing records.
   - Splitting into train/test sets using stratification.
   - Feature scaling using `StandardScaler`.

3. **Model Implementation**
   - Logistic Regression (`class_weight='balanced'`, `max_iter=1000`)
   - Support Vector Machine with RBF kernel and balanced class weight

4. **Evaluation**
   - Confusion Matrix
   - Accuracy, Precision, Recall, F1 Score
   - Classification Report
   - Metric Summary Table

---

## Evaluation Metrics

### Logistic Regression

| Metric     | Value    |
|------------|----------|
| Accuracy   | 87.83%   |
| Precision  | 18.56%   |
| Recall     | 81.82%   |
| F1 Score   | 30.25%   |

---

### Support Vector Machine (SVM)

| Metric     | Value    |
|------------|----------|
| Accuracy   | 89.96%   |
| Precision  | 18.79%   |
| Recall     | 63.64%   |
| F1 Score   | 29.02%   |

---

## Observations

- **Accuracy** is slightly higher in SVM, indicating overall correct classifications are marginally better.
- **Recall** is significantly higher in Logistic Regression, meaning it detects more actual bankrupt companies.
- **Precision** is low in both models due to class imbalance — many predicted positives are false alarms.
- **F1 Score** remains modest, emphasizing the trade-off between high recall and low precision.

---

## Conclusion

Both models demonstrate competent performance for bankruptcy prediction on imbalanced financial data:

- Logistic Regression performs better in terms of **recall**, making it more suitable when identifying as many bankrupt firms as possible is a priority.
- SVM provides a **slightly better accuracy**, but at the cost of lower recall.

---

