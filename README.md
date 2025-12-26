# Fraud Detection with Explainable Machine Learning

## Project Overview
This project focuses on detecting fraudulent transactions using machine learning while ensuring **model interpretability**. In addition to building high-performing models, we apply **SHAP (SHapley Additive exPlanations)** to understand *why* transactions are classified as fraudulent and translate insights into **actionable business recommendations**.

---

## Objectives
- Analyze fraud patterns through exploratory data analysis (EDA)
- Train and evaluate multiple fraud detection models
- Handle extreme class imbalance appropriately
- Explain model predictions using SHAP
- Provide business-ready fraud prevention recommendations

---

## Dataset
The project uses three datasets:
- **Fraud_Data.csv** – E-commerce transaction data
- **IpAddress_to_Country.csv** – IP range to country mapping
- **creditcard.csv** – Credit card transaction dataset

**Target variable**
- `class` (1 = Fraud, 0 = Non-Fraud)

---

## Project Structure
fraud-detection/
│
├── data/
│ ├── raw/ # Original datasets
│ └── processed/ # Cleaned and feature-engineered data
│
├── notebooks/
│ ├── task1_eda.ipynb
│ ├── task2_modeling.ipynb
│ └── task3_explainability.ipynb
│
├── models/
│ └── best_model.joblib # Saved best-performing model
│
├── src/
│ └── preprocessing.py
│
├── README.md
└── requirements.txt


---

## Task 1 – Exploratory Data Analysis
- Data cleaning and validation
- Fraud vs non-fraud pattern analysis
- Feature engineering:
  - `time_since_signup`
  - transaction timing (hour/day)
  - transaction velocity
- IP-to-country geolocation mapping
- Identification of strong class imbalance

**Key Insight:**  
Fraud is highly imbalanced and strongly linked to behavioral and temporal patterns.

---

## Task 2 – Model Building & Evaluation
**Models trained**
- Logistic Regression (baseline)
- Random Forest
- XGBoost

**Techniques**
- Pipeline-based preprocessing
- Stratified train-test split
- Class imbalance handling
- Evaluation using PR-AUC, ROC-AUC, and F1-score

**Outcome:**  
An ensemble model achieved the best performance and was saved for further analysis.

---

## Task 3 – Model Explainability (SHAP)
To ensure transparency and trust:
- Extracted built-in feature importance
- Generated SHAP summary plots (global explanations)
- Explained individual predictions:
  - True Positive
  - False Positive
  - False Negative

### Top Fraud Drivers (from SHAP)
1. Time since signup  
2. Purchase value  
3. IP-related features  
4. Transaction hour  
5. User behavior patterns  

**Key Insight:**  
Fraud is driven more by **behavior and timing** than by transaction amount alone.

---

## Business Recommendations
- **Post-signup verification:** Apply additional checks shortly after account creation.
- **Velocity monitoring:** Flag rapid consecutive transactions.
- **Context-aware reviews:** Evaluate transaction amount together with behavioral signals.
- **Time/IP-based risk scoring:** Increase scrutiny for unusual timing or risky IP ranges.

---

## Tools & Libraries
- Python
- pandas, numpy
- scikit-learn
- XGBoost
- SHAP
- matplotlib, seaborn

---

## Conclusion
This project demonstrates an end-to-end fraud detection pipeline that is:
- Accurate
- Interpretable
- Business-actionable

By combining strong predictive performance with explainability, the solution supports both **risk mitigation** and **customer trust**.
