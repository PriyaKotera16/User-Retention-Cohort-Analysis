# User Retention & Transaction Analysis

## Project Overview

An end-to-end data analysis project focused on understanding user retention, cohort behavior, transaction performance, and churn patterns using Python and Pandas.

The project analyzes a synthetic dataset containing 5,000 users, 150,000 activity records, and 50,000 transaction records to identify retention patterns, revenue trends, and user segments associated with different churn rates.

---

## Business Objectives

The analysis focuses on answering the following questions:

- How does user activity change after activation?
- How does retention vary across user cohorts?
- When do significant retention drops occur?
- How is revenue changing over time?
- Is revenue movement driven by transaction volume or transaction value?
- How do transaction behaviors differ between churned and non-churned users?
- Which subscription and acquisition segments show higher observed churn?
- Which user segments may require further retention investigation?

---

## Dataset

The project uses a synthetic Excel dataset containing multiple related tables.

| Table | Records | Description |
|---|---:|---|
| Users | 5,000 | User demographics, subscription and churn information |
| User Activity | 150,000 | User activity records |
| Transactions | 50,000 | Transaction, payment and refund information |
| Support Tickets | 18,000 | Customer support interactions |
| Marketing Campaigns | 5,000 | Marketing campaign data |
| Subscription History | 20,000 | Subscription history records |

The Excel dataset is excluded from the GitHub repository using `.gitignore`.

---

## Tools & Technologies

- Python
- Pandas
- Matplotlib
- Seaborn
- Excel
- Jupyter Notebook
- Git & GitHub

---

## Analysis Performed

### 1. Data Validation

Performed initial data quality checks including:

- Dataset dimensions
- Missing values
- Duplicate records
- Primary key validation
- Foreign key validation
- Date range checks
- User-to-activity relationship checks

All 5,000 users had associated activity records.

---

### 2. Cohort & Retention Analysis

Two cohort approaches were explored:

#### Signup Cohorts

Users were grouped according to their signup month and their subsequent monthly activity was analyzed.

#### Activation Cohorts

Users were grouped according to their first recorded activity month to measure retention after activation.

A retention matrix and heatmap were created to identify retention patterns across months since activation.

M6 retention across mature activation cohorts was approximately 50–70% in the analyzed dataset.

---

### 3. Transaction & Revenue Analysis

Transactions were analyzed using successful, non-refunded transactions as the revenue-eligible transaction definition.

Key results:

- Total transactions: **50,000**
- Successful transactions: **46,988**
- Successful non-refunded transactions: **45,529**
- Revenue from successful non-refunded transactions: **1.91M**
- Overall AOV: **41.97**

Monthly analysis was performed for:

- Revenue
- Successful transaction volume
- Average order value
- Active transacting users
- Transactions per buyer
- Payment methods
- Transaction failures
- Refunds
- Coupon usage

The analysis showed that monthly revenue movement was primarily associated with changes in transaction volume, while AOV remained relatively stable.

---

### 4. Churn Analysis

User-level transaction behavior was compared between churned and non-churned users.

| Metric | Non-Churned | Churned |
|---|---:|---:|
| Transactions/User | 9.13 | 9.05 |
| Spend/User | 382.98 | 380.52 |
| AOV/User | ~42.00 | ~42.00 |

The analysis did not show a clear difference in transaction frequency, total spend, or AOV between churned and non-churned users.

---

### 5. User Segmentation

Churn was analyzed across:

- Subscription type
- Acquisition channel
- Device
- Age group
- Country
- Subscription × acquisition channel

The highest observed churn segment was:

**Free + Ads → 52.3% churn rate**

This segment was identified as an area for further retention investigation. The analysis shows an association and does not establish that the acquisition channel caused churn.

---

## Key Visualizations

The project includes:

1. Activation Cohort Retention Heatmap
2. Monthly Revenue Trend
3. Monthly Successful Transaction Volume
4. Churned Users by Acquisition Channel
5. Churned Users by Subscription Type
6. Subscription × Acquisition Churn Rate Heatmap

---

## Key Business Insights

### Retention

Activation cohort analysis showed a substantial decline in retention around the six-month mark across mature cohorts, suggesting a potential retention point that warrants further investigation.

### Revenue

Revenue increased during the first part of 2024 and subsequently declined during 2025. AOV remained relatively stable, indicating that changes in transaction volume were more closely associated with revenue movement than major changes in transaction value.

### Customer Behavior

Churned and non-churned users showed very similar transaction frequency, total spend, and AOV in the analyzed dataset.

### Segmentation

Churn rates varied more noticeably across subscription and acquisition combinations than across device, age group, or country.

The Free + Ads segment had the highest observed churn rate at 52.3%.

---

## Project Structure

```text
User-Retention-Cohort-Analysis/
│
├── User_Retention_Cohort_Analysis.ipynb
├── README.md
└── .gitignore
