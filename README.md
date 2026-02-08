# 📘 **Default of Credit Card Clients — Group 6 Project**

This repository contains the implementation, analysis, and results of our project on **predicting credit card default risk** using machine learning techniques.
The work is based on the well-known **UCI Default of Credit Card Clients dataset**, containing 30,000 customer records with demographic, financial, and historical payment information.

---

## 📌 **Project Overview**

Credit card defaults represent a major risk for financial institutions.
The goal of this project is to **predict whether a customer will default next month**, and to identify the key factors associated with default risk.

**Key research questions:**

* Can default be reliably predicted using customer demographic and payment history data?
* Which variables are most strongly associated with high default risk?
* How can banks use these insights to improve credit risk management?

---

## 📂 **Dataset Description**

* **Source:** Credit card default dataset from Taiwan
* **Size:** 30,000 records × 24 variables
* **Target variable:**

  * `default.payment.next.month` (0 = No, 1 = Yes)

### **Main feature categories:**

* **Payment History:** `PAY_0` to `PAY_6`
* **Financial Behavior:** `LIMIT_BAL`, `BILL_AMT1–6`, `PAY_AMT1–6`
* **Demographics:** `SEX`, `EDUCATION`, `MARRIAGE`, `AGE`

The dataset required minimal cleaning and contained no missing values.

---

## 📊 **Exploratory Data Analysis**

Key findings from the EDA:

* The dataset is **highly imbalanced** (≈22% defaults).
* Recent payment status (`PAY_0`) shows a strong relationship with default.
* Demographic variables such as **education** and **marriage status** also show relevant trends.

Figures include:

* Distribution of the target variable
* Variable relationships with default
* Confusion matrix and ROC curve

---

## 🤖 **Modeling Approach**

### ✔️ **Chosen Model: Logistic Regression**

We selected logistic regression for its:

* Interpretability
* Strong theoretical foundation
* Probability-based output
* Computational efficiency
* Suitability for binary classification

### ✔️ **Feature Selection**

A **forward selection approach using AIC** was used:

* Initial model AIC: **28,535.57**
* Final model AIC: **27,917.81**
* **18 features** selected
* ~618 AIC improvement

This allowed the model to balance complexity and predictive power.

---

## 📈 **Model Results**

### **Key Predictors of Default**

* **PAY_0** (recent payment behavior)

  * Odds Ratio: **1.78**
  * Customers with delayed recent payments have significantly higher risk.
* **Marriage**

  * Married customers show reduced default risk.
* **Education**

  * Higher education levels correspond to lower odds of default.
* **Payment Amounts**

  * Larger recent payments reduce risk.

### **Performance Metrics**

| Metric          | Value  | Interpretation                      |
| --------------- | ------ | ----------------------------------- |
| **Accuracy**    | 81.20% | Correct overall predictions         |
| **Sensitivity** | 24.72% | Ability to detect defaulters        |
| **Specificity** | 97.23% | Correctly identifies non-defaulters |
| **Precision**   | 71.72% | Reliability of positive predictions |
| **AUC**         | 0.7250 | Decent discrimination ability       |

The model performs well at identifying **non-defaulters**, but struggles with detecting **high-risk clients** due to class imbalance.

---

## 📉 **Limitations**

* Low sensitivity (many defaults missed)
* Class imbalance impacts model performance
* Logistic regression may not capture complex non-linear patterns

---

## 🚀 **Future Work**

To improve performance, we plan to:

* Test alternative thresholds to improve sensitivity
* Use advanced models (Random Forest, XGBoost, Neural Networks)
* Apply resampling techniques (SMOTE, undersampling)
* Experiment with time-series approaches (trend analysis)
* Build an early-warning risk scoring system
* Integrate more real-world financial indicators

---

## 👥 **Team**

**Group 6 — AIMS Rwanda**

* Yan Kevin Ze
* Arnaud Foubeuda Bozahbe
* Olusola Timothy Ogundepo
* Consolee Nisingizwe

Project presented in **November 2025**.
