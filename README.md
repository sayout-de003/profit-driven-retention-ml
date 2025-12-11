# Profit-Driven Customer Retention System 🚀

### *Predicting Churn Risk & Customer Lifetime Value (CLV) to Optimize Retention Spend*

## 📌 Project Overview
Standard churn prediction models only answer **"Who will leave?"** This project goes a step further by answering **"Who is worth saving?"**

By combining a **Classification Model** (Churn Probability) with a **Regression Model** (Predicted CLV), this system segments customers into actionable groups based on their **financial risk**. This allows stakeholders to allocate retention budgets efficiently, targeting high-value at-risk customers ("VIPs") while avoiding wasted spend on low-value users.

## 📊 Business Value
* **Strategic Segmentation:** Moves beyond binary churn labels to a 4-quadrant Risk-Value matrix.
* **Revenue Protection:** Identifies the top **10% of customers** who account for **~40% of potential revenue loss**.
* **Actionable Insights:** Provides specific intervention strategies (e.g., "High Priority Retention" vs. "Upsell Opportunity") for each segment.

## 🗂️ Data Source
The dataset used is the **Telco Customer Churn** dataset.
* **Source:** [Kaggle - Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
* **File:** `WA_Fn-UseC_-Telco-Customer-Churn.csv`

## 🛠️ Solution Architecture
The solution pipeline consists of two parallel machine learning models:

1.  **Churn Probability (Classification):**
    * **Model:** Logistic Regression (tuned via GridSearchCV).
    * **Metric:** ROC-AUC Score (**0.86**).
    * **Goal:** Estimate the likelihood ($P$) of a customer leaving.

2.  **Customer Value (Regression):**
    * **Model:** ElasticNet Regression.
    * **Metric:** $R^2$ Score (**0.99**).
    * **Goal:** Forecast the future financial value ($V$) of the customer.

3.  **Decision Engine (Risk Matrix):**
    * Combines outputs to calculate **Expected Revenue Loss**:
        $$\text{Expected Loss} = P(\text{Churn}) \times \text{Predicted CLV}$$

## 📂 Repository Structure
```text
├── data/
│   └── Telco-Customer-Churn.csv    <-- Download dataset here
├── notebooks/
│   └── profit-driven-retention-ml.ipynb  <-- Main Project Notebook
├── images/
│   └── risk_matrix.png             <-- Strategy Matrix Plot
├── requirements.txt
└── README.md
