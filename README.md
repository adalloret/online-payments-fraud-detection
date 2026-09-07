# Online Payments Fraud Detection with Machine Learning

## Business Problem
Online payment platforms face significant financial losses due to undetected fraudulent transactions. This project builds a predictive end-to-end Machine Learning pipeline to identify fraud in real time using the [PaySim](https://www.kaggle.com/code/adalloret/creditcard-fraud-detection) dataset, focusing on minimizing False Negatives (uncovered fraud).

## Key Analytical Findings (EDA)
1. **Risk Concentration:** 100% of fraudulent activities were restricted to `TRANSFER` and `CASH_OUT` transaction types.
2. **Account Draining Pattern:** Attackers systematically empty origin accounts, leaving an exact ending balance of $0.00.
3. **Transaction Amount:** Fraudulent transactions averaged significantly higher transfer values compared to legitimate ones.

## Model Performance & Decision Threshold Tuning
Using a **Random Forest Classifier** with class weighting, we optimized the decision threshold to balance fraud detection against customer friction:

| Metric | Baseline (Threshold 0.50) | Optimized (Threshold 0.10) | Impact |
| :--- | :--- | :--- | :--- |
| **Recall (Class 1)** | 25.0% | **75.0%** | Captures 3/4 of all fraud cases |
| **False Negatives (FN)** | 3 undetected | **1 undetected** | Substantially reduces financial losses |
| **False Positives (FP)** | 0 false alarms | **1 false alarm** | Minimal customer operational friction |
| **ROC-AUC Score** | 0.87 | **0.87** | High overall class separation ability |

## Stack
* **Language:** Python (Pandas, NumPy, Scikit-Learn, Seaborn)
* **Model:** Random Forest Classifier
* **Dashboard:** Power BI / Tableau Ready (`fraud_detection_results.csv`)
