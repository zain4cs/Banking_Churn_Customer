# Banking Customer Churn Prediction

Predicting which bank customers are likely to leave using machine learning. Three models were trained and compared on real banking data.

---

## The Problem

Banks lose revenue when customers leave. If we can predict who is about to churn, the bank can act early and retain them. This project builds a model that does exactly that.

---

## Dataset Overview

10,000 bank customers with features like credit score, age, balance, number of products, and activity status. The target is whether the customer left the bank or not.

One key challenge: the data is imbalanced. 80% of customers stayed and only 20% churned. This directly affects which metric we trust.

---

## Steps Followed

**Data Cleaning** — Dropped RowNumber, CustomerId, and Surname since they carry no predictive value.

**Encoding** — Gender was mapped to 0 and 1. Geography had three categories with no order so One Hot Encoding was used.

**Scaling** — StandardScaler was applied on numerical features. Fitted only on training data to prevent data leakage.

**Modeling** — Three models were trained and compared: Logistic Regression, Random Forest, and XGBoost.

---

## Results

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| Logistic Regression | 0.811 | 0.552 | 0.201 | 0.295 |
| Random Forest | 0.866 | 0.766 | 0.458 | 0.573 |
| XGBoost | 0.870 | 0.717 | 0.555 | 0.626 |

XGBoost won with 87% accuracy and F1 Score of 0.63.

F1 Score was the main metric here because accuracy is misleading on imbalanced data. A model that always predicts "stayed" would still score 80% without learning anything useful.

---

## Key Findings

NumOfProducts and IsActiveMember were the two most important features. Customers with 3 or 4 products and inactive members were far more likely to churn. Age and Balance also had strong influence.

---

## Tech Stack

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, XGBoost

---

## What I Learned

Accuracy alone is not enough on imbalanced datasets. F1 Score gives the real picture. XGBoost consistently outperforms simpler models on structured data and feature importance turns model output into actual business insight.

---

## Author

Zain Ali — zainzulfiqar.cs@gmail.com
