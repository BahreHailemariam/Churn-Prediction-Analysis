# Churn-Prediction-Analysis
## 📌 1. Dashboard Objective

This Power BI report provides:

- Customer churn monitoring

- Revenue at risk analysis

- Behavioral churn drivers

- Risk segmentation

- Retention campaign targeting

Designed for:

- Executive leadership

- Marketing & CRM teams

- Retention managers

- Data analysts

## 🧱 2. Data Model Overview
### Tables Used
**Fact Table**

- `fact_subscription`

  - customer_id

  - tenure_months

  - monthly_charges

  - total_charges

  - support_tickets

  - churn_flag

  - snapshot_date

**Dimension Tables**

- `dim_customers`

  - customer_id

  - region

  - contract_type

  - payment_method

  - internet_service

**Feature Table**

- `churn_features`

  - customer_id

  - recency_days

  - avg_monthly_spend

  - support_ticket_ratio

  - long_term_flag

  - churn_flag

Relationships:

- One-to-many: dim_customers → fact_subscription

- One-to-one: dim_customers → churn_features

## 📄 PAGE 1 — Executive Overview
### 🎯 Purpose

High-level churn monitoring & financial impact.

#### KPI Cards (Top Section)
**1️⃣ Total Customers**
```
Total Customers =
DISTINCTCOUNT(dim_customers[customer_id])
```
**2️⃣ Active Customers**
```
Active Customers =
CALCULATE(
    [Total Customers],
    churn_features[churn_flag] = 0
)
```
**3️⃣ Churned Customers**
```
Churned Customers =
CALCULATE(
    [Total Customers],
    churn_features[churn_flag] = 1
)
```
**4️⃣ Churn Rate**
```
Churn Rate =
DIVIDE(
    [Churned Customers],
    [Total Customers]
)
```
**5️⃣ Revenue at Risk**
```
Revenue At Risk =
CALCULATE(
    SUM(fact_subscription[monthly_charges]),
    churn_features[churn_flag] = 1
)
```
**Visuals**

- Donut: Active vs Churned

- Bar Chart: Churn by Contract Type

- Line Chart: Churn Trend Over Time

- Card: Revenue At Risk

## 📄 PAGE 2 — Churn Risk Analysis
### 🎯 Purpose

Segment customers by churn probability & behavioral signals.

**Risk Band (Calculated Column)**
```
Risk Band =
SWITCH(
    TRUE(),
    churn_features[recency_days] > 90, "High Risk",
    churn_features[recency_days] > 45, "Medium Risk",
    "Low Risk"
)
```
**Risk Distribution Measure**
```
Customers by Risk =
COUNTROWS(churn_features)
```
Used in:

Stacked Bar (Risk Band vs Count)

**Average Recency**
```
Avg Recency =
AVERAGE(churn_features[recency_days])
Avg Support Ticket Ratio
Avg Ticket Ratio =
AVERAGE(churn_features[support_ticket_ratio])
```
**Visuals**

- Bar Chart: Customers by Risk Band

- Scatter: Recency vs Monthly Spend

- Table: Top High-Risk Customers

- Matrix: Risk Band × Contract Type

## 📄 PAGE 3 — Behavioral Insights
### 🎯 Purpose

Identify churn drivers.

**Avg Monthly Spend**
```
Avg Monthly Spend =
AVERAGE(fact_subscription[monthly_charges])
Avg Tenure
Avg Tenure =
AVERAGE(fact_subscription[tenure_months])
Support Tickets per Customer
Avg Support Tickets =
AVERAGE(fact_subscription[support_tickets])
```
**Visuals**

- Box Plot: Tenure by Churn Flag

- Bar: Support Tickets by Churn Status

- Line: Spend Trend Over Time

- Matrix: Contract Type × Churn Rate

## 📄 PAGE 4 — Revenue Impact
### 🎯 Purpose

Financial implications of churn.

**Monthly Revenue**
```
Monthly Revenue =
SUM(fact_subscription[monthly_charges])
```
**Lost Revenue**
```
Lost Revenue =
CALCULATE(
    SUM(fact_subscription[monthly_charges]),
    churn_features[churn_flag] = 1
)
```
**Revenue Retention Rate**
```
Revenue Retention =
1 - DIVIDE([Lost Revenue], [Monthly Revenue])
```
**High Value Customers at Risk**
```
High Value At Risk =
CALCULATE(
    COUNTROWS(churn_features),
    churn_features[churn_flag] = 0,
    churn_features[avg_monthly_spend] > 100
)
```
**Visuals**

- Waterfall: Revenue Breakdown

- Bar: Revenue by Risk Band

- KPI Card: Revenue Retention %

📄 PAGE 5 — Retention Planner
🎯 Purpose

Actionable targeting list.

Retention Priority Score
Retention Priority =
churn_features[avg_monthly_spend] *
(1 + churn_features[support_ticket_ratio]) *
IF(churn_features[recency_days] > 60, 1.5, 1)
Visuals

Table:

Customer ID

Risk Band

Monthly Spend

Priority Score

Slicers:

Region

Contract Type

Risk Band

Bar: Priority by Segment

🎛 Global Slicers

Date Range

Region

Contract Type

Payment Method

Risk Band

📊 Color Logic

High Risk → Red

Medium Risk → Orange

Low Risk → Green

Revenue Loss → Dark Red

🧠 Executive Insights This Dashboard Enables

Identify early churn signals

Quantify revenue exposure

Target high-value at-risk customers

Optimize retention incentives

Track churn trend over time

🚀 Optional Advanced Enhancements

ML probability score column

SHAP explanation integration

Power Automate alert for high-risk VIP

Rolling 30-day churn forecast
