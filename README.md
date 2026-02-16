# 📉 Churn Prediction Analysis
## 📌 Project Overview

This project focuses on building a customer churn prediction model to identify customers who are likely to stop using a service. By leveraging machine learning, feature engineering, and business-driven insights, the solution enables organizations to take proactive retention actions and reduce revenue loss.

The project includes:

- End-to-end data preprocessing

- Exploratory data analysis (EDA)

- Feature engineering

- Model training & evaluation

- Business-focused churn insights

- Optional dashboard or app integration


## 🎯 Business Objectives

- Identify high-risk customers before churn occurs

- Reduce customer acquisition replacement costs

- Improve retention strategies

- Enable targeted intervention campaigns

- Increase customer lifetime value (CLV)

## 🧠 Problem Statement

Customer churn significantly impacts profitability. Retaining existing customers is often cheaper than acquiring new ones. This project aims to:

- Predict the probability of churn

- Understand key drivers behind churn

- Segment customers by churn risk

- Provide actionable recommendations

## 📂 Project Structure
```
Churn-Prediction-Analysis/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   └── EDA.ipynb
│
├── scripts/
│   ├── load_data.py
│   ├── clean_data.py
│   ├── feature_engineering.py
│   ├── train_model.py
│   └── app.py
│
├── models/
│   └── churn_model.pkl
│
├── sql/
│   ├── 01_create_tables.sql
│   ├── 02_cleaning.sql
│   ├── 03_feature_engineering.sql
│   ├── 04_kpi_metrics.sql
│   └── 05_views_for_powerbi.sql
│
├── dashboard/
│   └── PowerBI_Report_Spec.md
│
├── reports/
│   └── model_performance.md
│
├── requirements.txt
└── README.md
```
## 🔄 Workflow Summary
### 1️⃣ Data Collection

- Customer demographic data

- Subscription details

- Usage behavior

- Billing history

- Support interactions

### 2️⃣ Data Cleaning

- Handle missing values

- Remove duplicates

- Normalize categorical variables

- Detect outliers

### 3️⃣ Feature Engineering

- Tenure length

- Monthly spending

- Average usage

- Payment behavior

- Support ticket frequency

Engagement score

### 4️⃣ Model Development

Models evaluated:

- Logistic Regression

- Random Forest

- Gradient Boosting

- XGBoost

### 5️⃣ Model Evaluation

- Key metrics:

- Accuracy

- Precision

- Recall

- F1-Score

- ROC-AUC

- Confusion Matrix

### 6️⃣ Insights & Retention Strategy

- Identify top churn drivers

- Segment customers by risk

- Recommend retention interventions

## 📊 Power BI Dashboard Overview
### 📄 Pages Included
### 1️⃣ Executive Summary

- Total Customers

- Churn Rate

- Active vs Churned Customers

- Revenue at Risk

### 2️⃣ Churn Risk Analysis

- Risk Distribution (Low/Medium/High)

- Probability Score Distribution

- Top Predictive Features

### 3️⃣ Behavioral Insights

- Usage patterns by churn status

- Tenure vs churn trend

- Payment behavior analysis

### 4️⃣ Revenue Impact

- Revenue loss by churn segment

- High-value customers at risk

- CLV comparison

### 5️⃣ Retention Strategy Planner

- Target list of at-risk customers

- Suggested intervention type

- Priority scoring

## 📈 Key KPIs

- Churn Rate

- Customer Retention Rate

- Revenue at Risk

- Average Tenure

- Average Monthly Revenue

- Intervention Success Rate (optional)

## 🛠️ Tools & Technologies

- **Python** (pandas, numpy, scikit-learn, XGBoost)

- **SQL** (data preparation & KPI metrics)

- **Power BI** (interactive dashboards)

- **Streamlit** (optional web app)

- **Jupyter Notebook** (EDA & experimentation)

## 🚀 How to Run
Install dependencies
pip install -r requirements.txt
Train model
python scripts/train_model.py
Launch app (optional)
streamlit run scripts/app.py
## 🧩 Key Insights Example

Customers with short tenure are more likely to churn

High support ticket frequency correlates with churn

Contract type significantly affects retention

Price sensitivity impacts churn probability

## 📌 Future Improvements

Deploy as REST API (FastAPI)

Real-time churn scoring

Automated retention campaign triggers

Deep learning models

Customer lifetime value prediction

## 🎯 Business Impact

This project enables:

Early churn detection

Data-driven retention strategy

Reduced revenue leakage

Improved marketing ROI

## 👤 Author
**Bahre Hailemariam**  
📍 *Data Analyst & BI Developer \| 4+ Years Experience*\
📩 [Email Adress](bahre.hail@gmail.com) | 🌐[Portfolio](https://bahre-hailemariam-data-analyst.crd.co/) |💼[LinkedIn](https://www.linkedin.com/in/bahre-hailemariam/) | 📊[GitHub](https://github.com/BahreHailemariam)


---

## 🪪 License
Licensed under the **MIT License** — free to use and modify.
