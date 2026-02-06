Customer Churn Prediction Using Product & Behavioral Data

Project Overview
Customer churn is a critical challenge in the banking and fintech industry, as acquiring new customers is significantly more expensive than retaining existing ones. This project builds an end-to-end machine learning pipeline to predict customer churn using product usage, behavioral, and demographic data.

The final solution helps businesses proactively identify high-risk customers and take targeted retention actions.

---

Problem Statement
Many businesses struggle to detect early warning signs of customer churn, especially when disengagement occurs gradually through reduced activity rather than explicit complaints.  
This project aims to predict whether a customer is likely to churn based on inactivity patterns and product usage behavior.

---

Objectives
- Extract and preprocess customer data
- Define churn using real-world business logic
- Perform exploratory data analysis (EDA)
- Engineer meaningful behavioral features
- Build and evaluate machine learning models
- Interpret results using feature importance
- Align predictions with business KPIs

---

Dataset Description
The dataset contains **25,000 customers** with the following feature groups:

Customer Demographics
- Age, gender, state
- Employment status

Product & Account Information
- Account type
- Account age (months)
- Average monthly balance
- Monthly transactions
- Failed transactions
- Loan and credit card status
- KYC level
- Alert preferences

Behavioral Data
- Last login date
- Last transaction date

---

Churn Definition
Since churn was not explicitly labeled, it was defined using business rules:

> A customer is considered **churned (1)** if they have:
- No login for **90 days or more**
- AND no transaction for **90 days or more**

Otherwise, the customer is marked as **retained (0)**.

---

Feature Engineering
Key engineered features include:
- `days_since_last_login`
- `days_since_last_transaction`
- `transaction_failure_rate`
- `low_balance_flag`
- `tenure_bucket`

These features capture disengagement and customer lifecycle behavior.

---

Modeling Approach
Two models were trained and evaluated:

1. Logistic Regression
   - Baseline, interpretable model
   - Class-weighted to handle churn sensitivity

2. Random Forest Classifier
   - Captures non-linear relationships
   - Used for feature importance and final predictions

---

Model Evaluation (KPIs)

Business KPIs
- Churn Rate
- Retention Rate
- High-Risk Customer Count

Model KPIs
- Accuracy
- Precision
- Recall (prioritized)
- F1-Score
- ROC-AUC

> Recall was emphasized because missing a churner is more costly than incorrectly flagging a loyal customer.

---

Explainability
Feature importance from the Random Forest model revealed that:
- Behavioral features (inactivity and usage) are stronger churn predictors than demographics
- Days since last login and transaction are the most influential features

---

Key Insights
- Customer inactivity is the strongest indicator of churn
- Declining transaction volume and failed transactions increase churn risk
- Engagement through alerts (SMS/email) is associated with lower churn
- New and low-balance customers churn more frequently

---

Tools & Technologies
- Python (pandas, numpy, scikit-learn)
- SQL (for KPI computation and business queries)
- Jupyter Notebook
- GitHub for version control

---

Future Improvements
- Integrate social media or review sentiment data
- Deploy model via a Streamlit dashboard
- Save predictions and risk scores to a database
- Apply SHAP for customer-level explainability

---

Author
Echezona Victor Okweleze
(Data Science & Machine Learning Project)
