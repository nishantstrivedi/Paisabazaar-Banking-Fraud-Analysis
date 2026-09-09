# 🏦 Bank Fraud Risk Analysis Dashboard | Power BI

> An interactive Power BI dashboard analyzing 40,959 bank customer records to segment credit risk, detect fraud/default behavioural red flags, and support evidence-based lending and collections decisions.

---

## 📌 Project Overview

This project is a complete Business Intelligence solution developed in **Power BI** to transform raw customer financial data into clear, interactive visual insights for a bank's underwriting, compliance, and fraud-prevention teams. The report segments customers by credit quality, quantifies the debt/interest/delay burden carried by each risk tier, and profiles risk by age, occupation, and payment behaviour.

The report is organized into **6 pages** and lets users dynamically explore data by **credit score tier, age group, income bracket, and occupation**.

---

## 🎯 Business Objectives

- Identify and segment customers by credit quality — Good, Standard, and Poor
- Detect high-risk behavioural patterns associated with payment default and fraud
- Analyse the relationship between income, debt, interest rate, and credit score
- Provide occupation-wise and age-wise credit risk profiling
- Enable business stakeholders to make faster, evidence-based lending decisions

---

# 📊 Dashboard Pages

| Page | What it shows |
|---|---|
| **Dashboard Insights** | Narrative summary tiles distilling the key finding from each of the other 5 pages |
| **Overview** | Total customers, credit-mix quality, credit-score distribution donut, average income by credit score, minimum-payment behaviour donut |
| **Credit Analysis** | Credit score by age group, credit score by income bracket, credit-count KPI cards by tier |
| **Risk & Debt** | Average outstanding debt, interest rate, payment delay days, and EMI — all segmented by credit score tier |
| **Customer Behaviour** | Payment-behaviour segmentation (6 spend × value combos), credit utilisation ratio, average monthly balance by credit tier |
| **Income Analysis** | Average income by credit tier, total customers by occupation and credit score |

---

### Executive KPIs

- Total Customers
- Credit Score Distribution (Good / Standard / Poor)
- Average Income by Credit Tier
- Average Outstanding Debt by Credit Tier
- Average Interest Rate by Credit Tier
- Average Payment Delay (Days)
- % Paying Minimum Amount Only

### Interactive Filters

Users can filter the report by:

- Credit Score (Good / Standard / Poor)
- Age Group
- Income Bracket
- Occupation
- Payment Behaviour Type

### Visualizations

The dashboard includes:

- 🥧 Credit Score Distribution (donut)
- 📊 Credit Mix Quality (bar)
- 💰 Average Income by Credit Score (bar)
- 📈 Credit Score by Age Group / Income Bracket (grouped bars)
- 💳 Average Debt, Interest Rate, Payment Delay, EMI by Credit Tier
- 🎯 Payment Behaviour Breakdown (6-segment bar)
- 🍩 Credit Utilisation Ratio (donut)
- 👤 Total Customers by Occupation and Credit Score (100% stacked bar)
- KPI Cards & narrative insight tiles

---

# 📈 Key Metrics (from the current dataset)

- **Total Customers:** 40,959
- **Credit Score Split:** Standard 52.8% (21,608) · Poor 29.4% (12,034) · Good 17.9% (7,317)
- **Average Income:** Good ₹67,268 · Standard ₹50,686 · Poor ₹41,117
- **Average Outstanding Debt:** Good ₹783 · Standard ₹1,263 · Poor ₹2,073 (2.6× higher for Poor)
- **Average Interest Rate:** Good 7.58% · Standard 13.68% · Poor 19.96% (2.6× higher for Poor)
- **Average Payment Delay:** Good 10.9 days · Standard 19.8 days · Poor 29.6 days (2.7× higher for Poor)
- **Minimum-Payment Skippers:** 47.5% of customers do NOT pay their minimum amount

---

# 🧮 Risk Segmentation

The dashboard segments customers into three credit tiers:

- **Good** — lowest debt, lowest interest rate, lowest payment delay, highest income
- **Standard** — the largest segment; middle-tier across every risk metric
- **Poor** — highest debt, highest interest rate, longest payment delays, lowest income — the primary fraud/default watch segment

---

# 👤 Customer Behaviour Segments

Six payment-behaviour types (spend × value combinations) are tracked:

| Behaviour | Customers | Share |
|---|---|---|
| Low-spent / Small-value payments | 11,783 | 28.8% |
| High-spent / Medium-value payments | 8,101 | 19.8% |
| High-spent / Large-value payments | 5,920 | 14.5% |
| Low-spent / Medium-value payments | 5,908 | 14.4% |
| High-spent / Small-value payments | 4,884 | 11.9% |
| Low-spent / Large-value payments | 4,363 | 10.7% |

---

# 💡 Business Insights

- **Only 1 in 6 customers (17.9%) holds a Good credit score** — nearly 1 in 3 (29.4%) falls into the high-risk Poor category
- **Income is a strong predictor of credit quality** — Good-credit holders earn 63% more than Poor-credit holders on average
- **Poor-credit customers are caught in a debt-trap cycle**: high debt → high interest rate → payment delays → further credit damage — these three metrics together are the strongest fraud-risk signal in the dataset
- **Occupation alone is not a decisive risk factor** — credit-score distribution is broadly similar across all 12 professions, with only minor variation (Journalists/Lawyers skew slightly better, Scientists/Doctors skew slightly worse)
- **Younger customers (under 25) carry disproportionately higher Poor-credit rates** than the 45+ group, suggesting financial maturity correlates with credit quality
- **Skipping the minimum payment is the single strongest behavioural red flag** for default/fraud risk and should be a primary filter in any fraud-screening workflow

---

# 🛠️ Tech Stack

- Microsoft Power BI Desktop
- Power Query (data cleaning & transformation)
- DAX (calculated columns and measures)
- Data Modeling
- Interactive Visualizations

---

# 📂 Dataset

**File:** `pb_bank_fraud_detection_project-dataset.csv`
**Records:** 40,959 customers
**Columns:** 28 attributes per customer

## Key Columns

| Column | Type | Description | Used In |
|---|---|---|---|
| `Credit_Score` | Text | Target — Good / Standard / Poor | All pages |
| `Annual_Income` | Decimal | Yearly income in INR | Overview, Credit Analysis |
| `Outstanding_Debt` | Decimal | Total current debt in INR | Risk & Debt |
| `Interest_Rate` | Integer | Annual interest rate (%) | Risk & Debt |
| `Delay_from_due_date` | Integer | Days delayed past due date | Risk & Debt |
| `Occupation` | Text | Customer's profession | Credit Analysis |
| `Age` | Integer | Customer age in years | Credit Analysis |
| `Payment_Behaviour` | Text | Spend + payment value category | Customer Behaviour |
| `Payment_of_Min_Amount` | Text | Yes / No — minimum payment made | Overview |
| `Credit_Mix` | Text | Good / Standard / Bad portfolio mix | Overview |
| `Credit_Utilization_Ratio` | Decimal | % of available credit used | Customer Behaviour |
| `Total_EMI_per_month` | Decimal | Monthly EMI obligation (INR) | Risk & Debt |
| `Monthly_Balance` | Decimal | Average monthly account balance | Customer Behaviour |
| `Num_of_Delayed_Payment` | Integer | Count of delayed payments | Risk & Debt |

## Data Cleaning (Power Query)

- Set `Age`, `Num_Bank_Accounts`, `Num_Credit_Card`, `Num_of_Loan`, `Delay_from_due_date` → Whole Number
- Set `Annual_Income`, `Outstanding_Debt`, `Monthly_Balance`, `Total_EMI_per_month` → Decimal Number
- Set `Credit_Utilization_Ratio`, `Interest_Rate` → Decimal Number
- Removed errors/nulls from `Credit_Score` — only Good/Standard/Poor retained
- Trimmed whitespace from `Occupation` and `Payment_Behaviour`
- Created 2 calculated columns: `Age Group` and `Income Bracket` (DAX `SWITCH()`)
- Created sort-order columns: `Credit Score Order` and `Age Group Order` for correct chart sequencing

---

# 📷 Dashboard Preview

> Add screenshots here

![Dashboard](assets/screenshots/Dashboard_Insights.png)
![Dashboard](assets/screenshots/Overview.png)
![Dashboard](assets/screenshots/Credit_Analysis.png)
![Dashboard](assets/screenshots/Risk_and_Debt.png)
![Dashboard](assets/screenshots/Customer_Behaviour.png)
![Dashboard](assets/screenshots/Income_Analysis.png)

---

# 📁 Project Structure

```
Bank-Fraud-Risk-Analysis-Dashboard/
│
├── Bank_Fraud_Analysis_Dashboard.pbix
├── README.md
├── pb_bank_fraud_detection_project-dataset.csv
├── PB_Dashboard_Report.pdf
├── Bank_Fraud_Problem_Statement.docx
└── assets/
    └── screenshots/
        ├── Dashboard_Insights.png
        ├── Overview.png
        ├── Credit_Analysis.png
        ├── Risk_and_Debt.png
        ├── Customer_Behaviour.png
        └── Income_Analysis.png
```

---

# 🚀 How to Use

1. Clone or download this repository.
2. Open the `.pbix` file using **Power BI Desktop**.
3. Refresh the dataset from `pb_bank_fraud_detection_project-dataset.csv` if required.
4. Explore the dashboard using the credit-score, age-group, income-bracket, and occupation filters.

---

# 🚩 Recommended Actions (from the analysis)

- Implement an automated fraud alert for customers with delay > 25 days **and** debt > ₹1,800
- Create a minimum-payment monitoring workflow for the 47.5% of customers who skip it
- Apply tiered interest rates formally aligned to the three credit tiers
- Develop a targeted financial wellness / stricter underwriting program for customers under 25
- Use this dashboard monthly as part of the credit committee review process
- Integrate the Power BI report with the loan origination system for real-time scoring

---

# 📊 Skills Demonstrated

- Business Intelligence
- Data Cleaning & Transformation (Power Query)
- Data Modeling
- DAX Calculations (calculated columns, sort-order columns, segmentation logic)
- KPI Design
- Dashboard Design
- Data Visualization
- Credit Risk / Fraud Analytics
- Business Analytics & Reporting

---

# ⭐ Business Value

This dashboard enables the bank to:

- Proactively flag the 29.4% high-risk (Poor credit) portfolio segment before losses occur
- Target collections and minimum-payment monitoring at the customers most likely to default
- Apply evidence-based, tiered interest-rate and underwriting policy by credit segment
- Reduce credit-decision turnaround time with a self-service, portfolio-wide view
- Support compliance reporting on fair lending practices across income and occupation groups

---

# 📬 Connect With Me

**Nishant Shaileshkumar Trivedi**

- LinkedIn: https://www.linkedin.com/in/nstrivedi
- GitHub: https://www.github.com/nstrivedi

---

## ⭐ If you found this project useful, don't forget to Star this repository!
