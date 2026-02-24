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
