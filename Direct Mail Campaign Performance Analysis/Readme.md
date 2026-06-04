# 📬 Prospect Direct Mail Analytics
### An end-to-end analytics project inspired by American Express's Global Commercial Services

---

## 📌 Project Overview

This project simulates the analytics workflow of a **Prospect Direct Mail Analytics team** within a commercial banking environment. The goal is to analyze a 50,000-record direct mail campaign dataset to uncover insights around acquisition efficiency, ROI, wasted spend, and high-value customer profiling — and present findings through an executive Power BI dashboard.

> **Business Problem:** Only ~2% of prospects mailed convert into customers. The remaining 98% represents wasted budget. This project answers: *Who should we mail? What offer works best? Where is money being lost?*

---

## 🗂️ Project Structure

```
amex-direct-mail-analytics/
│
├── data/
│   ├── direct_mail_campaign.csv     # Raw simulated dataset (50,000 records)
│   └── cleaned_dataset.csv              # Cleaned dataset used for analysis
│
├── 01_EDA.ipynb                         # Data cleaning + exploratory data analysis
├── 02_sql_queries.ipynb                 # SQL queries using SQLite
│
├── dashboard/
│   └── direct_mail_dashboard.pbix       # Power BI dashboard file
│
└── README.md
```

---

## 📊 Dataset Summary

The dataset was synthetically generated to mirror real-world commercial direct mail campaigns.

| Field | Description |
|---|---|
| `prospect_id` | Unique identifier per prospect |
| `industry` | Business sector (Retail, Healthcare, Technology, etc.) |
| `business_size` | Micro / Small / Medium / Large |
| `region` | US region (Northeast, West, Midwest, Southeast, Southwest) |
| `offer_type` | Offer mailed (Cash Back 2%, 0% Intro APR, Travel Miles 2x, etc.) |
| `acquisition_channel` | Lead source (Cold List, Partner Referral, Lookalike Audience, Past Inquiry) |
| `credit_score_band` | Prospect's credit band |
| `years_in_business` | Business age bracket |
| `mailer_sent_date` | Date mailer was physically sent |
| `response_date` | Date prospect responded (null if no response) |
| `response_flag` | 1 = Responded, 0 = No response |
| `acquisition_flag` | 1 = Acquired as customer, 0 = Not acquired |
| `mailing_cost_usd` | Cost of mailing this prospect |
| `estimated_monthly_charge_volume_usd` | Monthly card spend if acquired |
| `roi` | Return on investment per mailer |
| `prospect_value_tier` | High / Mid / Low Value or Not Acquired |

**Dataset Stats:**
- 50,000 records across 2 years (2023–2024)
- Overall Response Rate: ~3.2%
- Overall Acquisition Rate: ~2.1%
- Total Mailing Cost: ~$97,500
- Total Charge Volume Generated: ~$21.5M

---

## 🔧 Tools & Technologies

| Tool | Purpose |
|---|---|
| **Python (Pandas, NumPy, Plotly)** | Data cleaning, EDA, trend analysis |
| **SQL (SQLite)** | Campaign KPI queries, segmentation |
| **Power BI + DAX** | Executive dashboard and visual storytelling |

---

## 🐍 Python Analysis — `01_EDA.ipynb`

### Data Cleaning
- Converted date columns to `datetime` format
- Created `days_to_respond` column (response lag in days)
- Added `year_month` column for time trend analysis
- Validated ROI sanity — confirmed `-1.0` ROI only exists for non-acquired prospects

### Exploratory Analysis Performed
- **Response & Acquisition Rate** — by offer type, industry, region, business size, and industry × offer type cross-analysis
- **ROI Analysis** — average ROI by offer type, industry, and acquisition channel
- **Charge Volume Analysis** — average monthly spend by business size (acquired customers only)
- **Waste Analysis** — total wasted spend on non-acquired prospects, broken down by offer type, industry, region, and region × industry combination
- **Pareto Analysis** — identified that ~79% of acquired customers drive 80% of total monthly charge volume
- **Time Trend Analysis** — monthly mailers sent, acquisitions, total mailing cost, and acquisition rate over 2023–2024

---

## 🗄️ SQL Analysis — `02_sql_queries.ipynb`

Dataset loaded into a SQLite database. Three analytical queries written:

1. **Overall Campaign Summary** — Total mailers, responses, acquisitions, response rate, acquisition rate, total mailing cost, and total charge volume in a single query
2. **Offer Type Performance** — Response rate, acquisition rate, average ROI, and total charge volume grouped by offer type
3. **Wasted Spend by Region & Offer** — Total mailing cost on non-acquired prospects, segmented by region and offer type, ordered by highest waste

---

## 📈 Power BI Dashboard

A 2-page interactive dashboard built using DAX measures on the cleaned dataset.

### DAX Measures Created
- Total Mailers Sent, Total Responses, Total Acquisitions
- Response Rate %, Acquisition Rate %
- Total Mailing Cost, Total Charge Volume
- Total Wasted Spend, Average ROI

### Page 1 — Executive Summary
- KPI cards: Total Mailers Sent, Total Acquisitions, Acquisition Rate, Total Mailing Cost, Total Charge Volume, Total Wasted Spend
- Bar chart: Acquisition Rate by Offer Type
- Bar chart: Average ROI by Industry
- Donut chart: Mailers Sent by Region
- Slicers: Region, Offer Type, Business Size, Year-Month

### Page 2 — Segment Deep Dive
- Matrix heatmap: Industry × Offer Type — Acquisition Rate (most insightful visual)
- Bar chart: Average Monthly Charge Volume by Business Size
- Bar chart: Acquisition Rate by Acquisition Channel
- Slicers: Region, Offer Type, Business Size, Year-Month

---

## 💡 Key Insights

- **0% Intro APR** drives the highest acquisition rate across nearly all industries — optimal offer for most campaigns
- **Travel Miles 2x** generates the highest wasted spend with the lowest acquisition rate — candidate for budget reduction
- **Partner Referral** channel outperforms Cold List with nearly 3x the acquisition rate
- **Large and Medium businesses** account for the majority of charge volume despite being a small share of total prospects
- **79% of acquired customers** are responsible for 80% of total monthly charge volume — targeting high-value segments more precisely could significantly improve campaign ROI

---

## 🚀 How to Run

1. Clone the repository
```bash
git clone https://github.com/yourusername/amex-direct-mail-analytics.git
cd amex-direct-mail-analytics
```

2. Install dependencies
```bash
pip install pandas numpy plotly sqlite3
```

3. Run notebooks in order
```
01_EDA.ipynb          → Data cleaning and analysis
02_sql_queries.ipynb  → SQL queries on cleaned data
```

4. Open `dashboard/direct_mail_dashboard.pbix` in Power BI Desktop

---

## 📁 Data Note

The dataset used in this project is **synthetically generated** for learning purposes and does not represent any real customer or campaign data from American Express. It is designed to reflect realistic distributions and patterns found in commercial direct mail campaigns.

---

## 👤 Author

**Your Name**
[LinkedIn](https://linkedin.com/in/yourprofile) • [GitHub](https://github.com/yourusername)
