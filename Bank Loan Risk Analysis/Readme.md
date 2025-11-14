# 💰 Bank Loan Portfolio Performance & Risk Analysis — SQL + Power BI

## 📝 Executive Summary
Banks manage thousands of loans across different customer segments, states, and risk grades. Without clear analytics, it becomes difficult to identify **which borrowers are defaulting**, **which loan products carry the highest risk**, and **where to focus collections efforts**.

This project performs an end-to-end **exploratory data analysis (EDA)** using **SQL** and **Power BI** on a dataset of **38,576 loans**.  
The analysis uncovers:

- 📊 Portfolio-level default rate  
- 🏷️ High-risk grades (E, F, G)  
- 🧭 State-wise loan distribution  
- 💸 Concentration of losses among large defaulted loans  
- 🎯 Purpose categories driving majority of defaults  

All results were visualized using an interactive Power BI dashboard.

---

## 💼 Business Problem
The lending team needed a clear, centralized view of:

- What is the overall **default rate**?  
- Which **loan grades** have the highest default probability?  
- Which **loan purposes** contribute the most to charge-offs?  
- Are losses concentrated in a few large loans or spread across the portfolio?  
- How should the bank **prioritize collections** and refine credit policy?

This project answers these questions using structured SQL queries and Power BI dashboards.

---

## 🧭 Methodology

### 1. Data Loading (SQL)
- Imported `financial_loan.csv` into SQL Server.  
- Verified schema and row count (**38,576 rows**).  

### 2. Data Cleaning (SQL)
- Standardized `loan_status` values (Charged Off, Default, Late).  
- Converted numeric fields (`loan_amount`, `int_rate`, `annual_income`).  
- Created `is_default` flag using SQL `CASE` logic.  

### 3. Exploratory Data Analysis (SQL)
#### ✔ Portfolio Overview
- Total loans, average loan amount, median loan amount  
- Average interest rate  

#### ✔ Default Analysis
- Default count and default rate  
- Grade-wise default risk (A → G)  
- Purpose-wise default contribution  
- State-wise loan distribution  

#### ✔ Concentration Analysis
- Total defaulted principal  
- Share of losses contributed by the top 10% largest defaulted loans  

### 4. Visualization (Power BI)
- KPI cards (default rate, total loans)  
- Bar charts for grade-wise default rate  
- Tree maps for loan purpose impact  
- Maps for geographic exposure  
- Drill-through pages for risk segmentation  

---

## 🧠 Skills Demonstrated

| Skill Area | Techniques Used |
|------------|----------------|
| **SQL** | CTEs, aggregations, CASE logic, data cleaning, segmentation |
| **Power BI** | Data modeling, DAX, KPI cards, bar charts, maps, drill-downs |
| **Analytics** | Default rate analysis, risk segmentation, concentration analysis |
| **Storytelling** | Business-ready insights tailored for credit & collections teams |

---

## 📈 Results & Insights

### 1️⃣ Portfolio Summary
- **Total loans analyzed:** 38,576  
- **Average loan amount:** **$11,296**  
- **Median loan amount:** **$10,000**  
- **Average interest rate:** **12.05%**  

### 2️⃣ Default Analysis
- **Total defaulted loans:** **5,333**  
- **Overall default rate:** **13.82%**  

#### 🔥 Default Rate by Grade
| Grade | Default Rate |
|-------|--------------|
| G | **31.31%** |
| F | **30.25%** |
| E | **24.80%** |
| D | Above portfolio average |
| A–C | Lowest risk group |

> Grades **E, F, and G** represent the highest-risk tiers and require stricter underwriting rules.

#### 🎯 Top Default-Contributing Loan Purposes
| Purpose | Default Count |
|---------|---------------|
| Debt Consolidation | **2,651** |
| Other | 587 |
| Credit Card | 508 |
| Small Business | 455 |

> **Debt Consolidation** alone contributes nearly **half of all defaults**.

### 3️⃣ Geographic Exposure
Top U.S. states by loan volume:

- CA — **6,894 loans**  
- NY — **3,701 loans**  
- FL — **2,773 loans**  
- TX — **2,664 loans**  

### 4️⃣ Loss Concentration
- **Total defaulted principal:** **$65.53 million**  
- **Top 10% largest defaulted loans = 24.6% of total losses**

> Losses are heavily concentrated in a small number of large borrowings, making them priority targets for recovery teams.

---

## 🚀 Next Steps
- 📅 Automate monthly Power BI refresh  
- 🧾 Add outstanding balance data for dollar-value DPD analysis  
- 🧭 Create borrower-level risk tiers using income, DTI, and employment  
- 🚨 Build rule-based Early Warning Indicators (EWIs) for proactive alerts  
- 📊 Deploy self-service dashboard for credit and collections teams  

---

## 🧰 Tech Stack
- **SQL Server**  
- **Power BI**  
- **Dataset:** `financial_loan.csv`  

---

## 📌 Repository Structure

Bank-Loan-Portfolio-Analysis/
├── Bank Loan Portfolio Dashboard.pbix
├── Loan Portfolio Analysis.sql
├── financial_loan.csv
└── README.md


---

## 👤 Author
**Tabish Shamim**  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?logo=linkedin&style=flat-square)](https://www.linkedin.com/in/tabish-shamim-2818h)  
[![Email](https://img.shields.io/badge/Email-Contact-red?logo=gmail&style=flat-square)](mailto:tabishshamim94@gmail.com)

---

⭐ If you found this project insightful, consider **starring the repository** — it helps support more analytics case studies like this.


