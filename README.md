# Minimizing Risk, Maximizing Profit: Advanced Credit Scoring with Explainable AI (XAI)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-XGBoost%20%7C%20SHAP%20%7C%20Scikit--Learn-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview
**Home Credit Indonesia** strives to provide financial inclusion for the unbanked population. However, expanding credit access comes with the risk of **Non-Performing Loans (NPL)**. 

This project goes beyond standard predictive modeling. We engineered a robust **Credit Scorecard Model** using **XGBoost** and **Domain-Driven Feature Engineering** to accurately predict repayment probabilities. Crucially, we implemented **SHAP (SHapley Additive exPlanations)** to interpret the "Black Box" model, ensuring that every credit decision is transparent, explainable, and actionable for business stakeholders.

### 🎯 Business Objective
To minimize financial losses due to default while maximizing loan approval volume for creditworthy customers.
- **Metric:** ROC-AUC (Primary), F1-Score (Optimized Threshold).
- **Impact:** Reduction in False Negatives (Bad loans accepted) and strategic risk-based pricing.

---

## 🚀 Key Highlights (The "Next Level" Approach)
Unlike basic implementations, this project features:

1.  **Domain-Knowledge Feature Engineering:**
    - Created financial ratios such as `PAYMENT_RATE` (Annuity/Income) and `GOODS_TO_LOAN_RATIO` to capture borrower's liquidity and intent.
    - Aggregated external credit scores (`EXT_SOURCE_MEAN`) which proved to be the strongest predictor.
2.  **Champion vs. Challenger Modeling:**
    - **Logistic Regression (Baseline):** For linearity checks.
    - **XGBoost (Champion):** Tuned with `scale_pos_weight` to handle extreme class imbalance (92:8).
3.  **Explainable AI (XAI) with SHAP:**
    - Moved beyond simple "Feature Importance" charts. Used SHAP values to explain *why* specific applicants were rejected (Local Interpretability).
4.  **Profit-Driven Threshold Tuning:**
    - Shifted the decision threshold from the default 0.5 to an optimal point derived from the F1-Score and business cost simulations.

---

## 📊 Model Performance

We compared the stability and accuracy of the baseline against the advanced model.

| Metric | Logistic Regression (Baseline) | **XGBoost (Champion)** | Improvement |
| :--- | :---: | :---: | :---: |
| **ROC-AUC** | 0.740 | **0.765** | **+2.5%** |
| **Precision** | Low | **Optimized** | High |
| **Recall** | Moderate | **High** | High |

> **Result:** The XGBoost model significantly outperforms the baseline, offering a better trade-off between capturing defaulters and approving good customers.

---

## 💡 Key Business Insights
Derived from SHAP analysis and EDA:

1.  **External Scores are Critical:** `EXT_SOURCE_1`, `_2`, and `_3` are the most reliable predictors. A low score in these external bureaus is a massive red flag.
2.  **The "Youth" Risk:** Applicants aged **20-30 years** exhibit a significantly higher default rate compared to older demographics.
    * *Recommendation:* Implement stricter DTI (Debt-to-Income) limits for this age group.
3.  **Cross-Reference Matters:** Discrepancies between `REG_CITY` and `WORK_CITY` correlate with higher fraud/default risk.
    * *Recommendation:* Require additional address verification for these anomalies.

---

## 📂 Repository Structure


```

├── Final_Task_Home_Credit_Scorecard_Model.ipynb   # Main Notebook (End-to-End Analysis)
├── ppt hci project.pdf                            # Business Presentation Slide
├── README.md                                      # Project Documentation
└── dataset/                                       # (Not included in repo due to size)
├── application_train.csv
├── bureau.csv
└── ...

```

---

## 🛠️ How to Run
This project is optimized for **Google Colab**.

1.  **Clone this repository:**
    ```bash
    git clone [https://github.com/username/home-credit-scoring.git](https://github.com/username/home-credit-scoring.git)
    ```
2.  **Upload Data:**
    Ensure `application_train.csv` and `bureau.csv` are in your Google Drive or local directory.
3.  **Install Dependencies:**
    ```python
    !pip install shap xgboost
    ```
4.  **Run the Notebook:**
    Open `Final_Task_Home_Credit_Scorecard_Model.ipynb` and execute all cells.

---

## 🤝 Connect
Feel free to discuss this project or give feedback!
* **LinkedIn:** [https://www.linkedin.com/in/jerico-christianto]
* **Email:** [Your Email Address]

---
*Disclaimer: This project is part of a Virtual Internship Experience at Rakamin Academy x Home Credit Indonesia.*

```
