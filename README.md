# Telco Customer Churn Analytics Pipeline

A full end-to-end churn analysis pipeline built on the IBM Telco Customer Churn dataset. Covers data ingestion, cleaning, exploratory analysis, cohort modeling, and an interactive Excel dashboard — structured for reuse on any subscription or SaaS dataset.

---

## Overview

Customer churn is one of the highest-leverage metrics in any subscription business. This pipeline answers three questions directly:

- **Who is leaving?** Churn rates segmented by contract type, tenure, internet service, payment method, and demographics.
- **When do they leave?** Cohort analysis across tenure bands reveals the critical first-6-month window.
- **What keeps them?** Retention drivers ranked by statistical impact, with actionable recommendations for each.

The dataset contains 7,043 customers with 21 features. Overall churn rate: **26.5%**.

---

## Repository Structure

```
telco-churn-pipeline/
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv   # Source dataset (IBM)
├── analysis/
│   └── churn_analysis.py                        # Full analysis script
├── output/
│   └── telco_churn_analysis.xlsx                # Excel workbook (6 sheets)
├── notebooks/
│   └── exploratory.ipynb                        # Optional EDA notebook
├── requirements.txt
└── README.md
```

---

## Requirements

```
pandas>=2.0
numpy>=1.24
openpyxl>=3.1
```

Python 3.9+ recommended.

---

## Excel Workbook — Sheet Guide

| Sheet | Contents |
|---|---|
| 📊 Executive Summary | KPI cards + 6 key findings with recommended actions |
| 📋 Customer Data | Cleaned, formatted source data (15 key columns) |
| 📉 Churn by Contract | Churn rates by contract type with bar chart |
| 📈 Churn by Tenure | Churn rate decay across tenure bands with line chart |
| 🎯 Churn Drivers Matrix | All dimensions ranked by churn rate vs. baseline |
| 🔢 Cohort Analysis | Heat map: tenure band × contract type churn rates |

---

## Key Findings

| Driver | Segment | Churn Rate |
|---|---|---|
| Tenure | 0–6 months | 53.3% |
| Payment | Electronic check | 45.3% |
| Contract | Month-to-month | 42.7% |
| Internet | Fiber optic | 41.9% |
| Support | No tech support | 41.6% |
| Demographics | Senior citizen | 41.7% |

Customers on two-year contracts churn at just **2.8%** — 15× lower than month-to-month.

---

## Recommendations

1. **Convert month-to-month customers** to annual plans with targeted incentives (discount, free add-ons).
2. **Launch a 90-day onboarding program** — the first 6 months have the highest churn risk by far.
3. **Investigate Fiber optic quality** — customers pay more but churn at the same rate as the highest-risk contract segment.
4. **Incentivize auto-pay enrollment** — a 1–2% billing discount would move electronic check users to a 3× lower churn cohort.
5. **Bundle basic Tech Support** into all plans or offer a free 30-day trial.
6. **Create a Senior customer plan** with simplified billing and priority phone support.

---

## Data Source

IBM Sample Dataset — [Telco Customer Churn](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)  
7,043 rows × 21 columns. No license restrictions for analytical use.

---

## Adapting to Your Own Data

The pipeline expects a CSV with at minimum:

- A binary churn label column (yes/no or 0/1)
- A tenure column (months)
- A contract or plan column
- A monthly charge or MRR column

