# 🏦 Bank Customer Churn Analysis
### End-to-End Analytics Project | Excel · MySQL · Power BI · Python

<div align="center">

![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![Excel](https://img.shields.io/badge/Excel-Advanced-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![PowerBI](https://img.shields.io/badge/Power_BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/Python-3.11.9-3776AB?style=for-the-badge&logo=python&logoColor=white)

<br/>

![Records](https://img.shields.io/badge/Records_Analysed-9%2C843-informational?style=flat-square)
![Churn](https://img.shields.io/badge/Churn_Rate-20.57%25-red?style=flat-square)
![Accuracy](https://img.shields.io/badge/ML_Accuracy-85%25-success?style=flat-square)
![AUC](https://img.shields.io/badge/ROC_AUC-0.84-success?style=flat-square)
![Charts](https://img.shields.io/badge/Charts_Generated-9-purple?style=flat-square)
![AtRisk](https://img.shields.io/badge/Assets_At_Risk-₹23.8_Crore-orange?style=flat-square)

</div>

---

## 👋 Introduction

Hi, I'm **Sanket Kumar** — a Data Analyst with a focus on banking and financial analytics. This repository contains my **end-to-end analytics project** built to solve a real customer retention crisis at a retail bank operating across three Indian cities: Bengaluru, Delhi, and Mumbai.

The project was built entirely from scratch using **four industry-standard tools** — Excel, MySQL, Power BI, and Python — covering every stage of the analytics lifecycle: raw data ingestion, cleaning, SQL analysis, interactive dashboards, and machine learning-based churn prediction.

What makes this project stand out is that it doesn't just analyse the past — it delivers a **deployable ML model** (85% accuracy, AUC 0.84) that can score every customer monthly and flag those most likely to leave before they do. The analysis also uncovered a previously unknown insight: **Mumbai Males churn at 37.8%** — the single highest-risk segment in the entire dataset, invisible until the Geography × Gender cross-analysis was performed in Python.

> This project demonstrates my ability to work end-to-end across the full data analytics stack — from messy raw CSV to production-ready dashboards and ML predictions — using real data with real business impact.

---

## 📌 Table of Contents

- [Business Context](#-business-context)
- [Problem Statement](#-problem-statement)
- [Measurable Impact](#-measurable-impact)
- [Tools & Outcomes](#-tools--outcomes)
- [Dataset Overview](#-dataset-overview)
- [Project Architecture](#-project-architecture)
- [Phase 1 — Excel](#-phase-1--advanced-excel)
- [Phase 2 — MySQL](#-phase-2--mysql)
- [Phase 3 — Power BI](#-phase-3--power-bi)
- [Phase 4 — Python & ML](#-phase-4--python--machine-learning)
- [Quantified Results](#-quantified-results)
- [Key Findings](#-key-findings)
- [Business Recommendations](#-business-recommendations)
- [Challenges Faced](#-challenges-faced)
- [Project Structure](#-project-structure)
- [How to Run](#-how-to-run)

---

## 💼 Business Context

A retail bank operating across **Bengaluru, Delhi, and Mumbai** was experiencing a growing customer attrition crisis. The bank's three-city operation served nearly **10,000 customers** across multiple product tiers — from basic 2-product account holders to high-value multi-product clients with account balances exceeding ₹39 Lakhs.

Despite the growing churn problem, the bank had **no analytical infrastructure** in place:
- No churn tracking dashboard
- No understanding of which customer segments were at highest risk
- No predictive system to flag at-risk customers before they left
- Retention efforts were generic, untargeted, and ineffective

The bank was bleeding its **wealthiest customers** — churned customers held an average balance of ₹11.74 Lakhs compared to ₹9.35 Lakhs for active customers — yet had no visibility into this fact until this project was built.

> **This project was built to give the bank exactly what it was missing: a complete, data-driven churn intelligence system from segment analysis to ML-based prediction.**

---

## ❓ Problem Statement

| Element | Detail |
|---|---|
| **The Problem** | 20.57% of customers are closing accounts — 1 in every 5 customers lost |
| **The Financial Gap** | ₹23.8 Crore in managed assets walking out the door undetected |
| **The Knowledge Gap** | No understanding of which customers are at risk or why they churn |
| **The Business Need** | Identify root cause segments + predict who will leave next |
| **The Solution Built** | 4-tool analytics system: cleaned data + SQL DB + 3-page dashboard + ML model |

---

## 📐 Measurable Impact

> These are the concrete, quantified outcomes this project delivered — not just analysis, but actionable intelligence.

| # | Impact Area | Before | After This Project |
|---|---|---|---|
| 1 | **Churn visibility** | Zero — no dashboard existed | Full 3-page interactive Power BI dashboard |
| 2 | **At-risk assets identified** | Unknown | ₹23.8 Crore in managed assets flagged |
| 3 | **Highest-risk city** | Unknown | Mumbai confirmed at 32.69% (2× national average) |
| 4 | **Highest-risk age group** | Unknown | 60+ confirmed at 48.51% churn rate |
| 5 | **Hidden risk segment uncovered** | Completely invisible | Mumbai Males = 37.8% — new critical finding |
| 6 | **Churn prediction capability** | None | Random Forest model: 85% accuracy, AUC 0.84 |
| 7 | **At-risk customer scoring** | Manual, impossible at scale | Model scores all 9,843 customers in seconds |
| 8 | **Cross-sell opportunity found** | Unknown | 2-product customers (28.1% churn) → 4-product sweet spot (7.6%) |
| 9 | **Query performance** | Raw CSV analysis | MySQL view + indexes enabling fast segmentation |
| 10 | **Reporting automation** | No automated pipeline | Full Python ETL pipeline — zero manual steps |

---

## 🛠 Tools & Outcomes

> Every tool was chosen deliberately. Here is what each one contributed and what it produced.

### Microsoft Excel — Office 365
**Used for:** First-pass data cleaning, formula-based KPI analysis, Pivot Table segmentation, XLOOKUP customer profile tool, interactive dashboard

| What Was Built | Outcome |
|---|---|
| 11 KPI formulas (COUNTIF, AVERAGEIF, COUNTA, MAX) | Baseline churn metrics: 20.57% rate, ₹39.85L max balance |
| 4 connected Pivot Tables with 3 shared slicers | Instant cross-filtering by city, gender, UPI status |
| XLOOKUP customer profile lookup tool | Any row number → full 10-field customer profile card |
| Interactive dashboard with 4 charts | Visual churn breakdown across all key dimensions |

---

### MySQL 8.0
**Used for:** Relational database storage, advanced SQL analysis, view creation for Power BI

| What Was Built | Outcome |
|---|---|
| bank_churn_db with customers table (9,843 records) | Structured, queryable data warehouse |
| 9 SQL queries — GROUP BY, CASE WHEN, CTEs, Window Functions | Churn rates by city, gender, age, products, profile comparison |
| RANK() OVER PARTITION BY for within-city rankings | Identified top churned customers by balance within each city |
| vw_churn_summary view (11 columns incl. age_group) | Live Power BI data source — no manual exports needed |

---

### Power BI Desktop — v1.108
**Used for:** Interactive visual dashboard connected live to MySQL

| What Was Built | Outcome |
|---|---|
| Direct MySQL connector to vw_churn_summary | Live data — refresh = instant updated dashboard |
| 7 custom DAX measures | Churn Rate %, Avg Age Churned, Avg Balance Active vs Churned |
| Page 1: Executive Summary (4 KPI cards + 3 charts + 3 slicers) | One-click filtering across all visuals |
| Page 2: Segmentation (Age × Geography matrix) | Mumbai 60+ segment = 65.09% churn uncovered |
| Page 3: Risk Profile (balance comparison + churned customer table) | ₹11.74L vs ₹9.35L balance gap quantified |

---

### Python 3.11.9 (VS Code + Pandas + Seaborn + Scikit-learn)
**Used for:** Advanced EDA, feature engineering, visualisation, ML model training

| What Was Built | Outcome |
|---|---|
| Full ETL pipeline — load, clean, validate, encode | 9,929 → 9,843 clean records, zero manual steps |
| 3 engineered features (Age_Group, Income_Segment, Balance_Income_Ratio) | Richer ML feature set |
| 9 publication-quality charts saved as PNG | Full visual story from KDE to heatmaps to ROC curve |
| Correlation heatmap | Age confirmed as #1 driver (r=0.32), UPI near zero (r=-0.01) |
| Geography × Gender heatmap | **Mumbai Males = 37.8% — new critical insight discovered** |
| Random Forest Classifier (100 trees, class_weight=balanced) | 85% accuracy, AUC 0.84, Age = 26.5% feature importance |

---

## 📂 Dataset Overview

| Property | Value |
|---|---|
| **Source File** | Dataset_master.csv |
| **Raw Records** | 9,929 rows |
| **Clean Records** | 9,843 rows |
| **Features** | 10 columns — 8 numerical, 2 categorical |
| **Target Variable** | `Closed` — 0 = Active, 1 = Churned |
| **Cities** | Bengaluru (50%), Mumbai (25%), Delhi (25%) |
| **Churn Rate** | **20.57%** — 2,025 out of 9,843 churned |

### All 10 Columns

| Column | Type | Range | Key Stat |
|---|---|---|---|
| Credit Score | Numerical | 285 – 692 | Avg 529.40 — weak churn predictor |
| Geography | Categorical | 3 cities | Mumbai 32.69% churn vs 16% others |
| Gender | Categorical | Male / Female | Males churn at 25.3% vs 16.6% females |
| Age | Numerical | 17 – 100 yrs | **#1 churn predictor — r=0.32** |
| Customer Since | Numerical | 0 – 8 yrs | Avg 4.42 yrs |
| Current Account | Numerical | ₹0 – ₹39.85L | Churned avg ₹11.74L vs Active ₹9.35L |
| Num of Products | Numerical | 2 – 7 | 7 products = 100% churn |
| UPI Enabled | Binary | 0 / 1 | 71% enabled — near-zero churn correlation |
| Estimated Yearly Income | Numerical | ₹32 – ₹5.47L | Avg ₹2.74L |
| **Closed** | **Binary** | **0 / 1** | **TARGET — 20.57% = 1** |

### Data Quality

| Issue Found | Count | Fix Applied |
|---|---|---|
| Blank rows | 2 | Dropped |
| Duplicate rows | 1 | Removed |
| Age outliers > 100 | ~86 | Filtered out |
| BOM encoding | Header | `encoding='utf-8-sig'` |

**Data Quality Score: 99.98%** ✅

---

## 🏗 Project Architecture

```
Raw CSV — Dataset_master.csv (9,929 rows)
            │
            ▼
 ┌──────────────────────┐
 │   PHASE 1 — EXCEL    │
 │  Clean + Formulas    │
 │  Pivot Tables + KPIs │
 │  XLOOKUP Tool        │
 │  Interactive Dash    │
 └──────────┬───────────┘
            │
            ▼
 ┌──────────────────────┐
 │   PHASE 2 — MySQL    │
 │  bank_churn_db       │
 │  9 SQL Queries       │
 │  CTEs + Window Fns   │
 │  vw_churn_summary    │
 └──────────┬───────────┘
            │  (live MySQL connection)
            ▼
 ┌──────────────────────┐
 │  PHASE 3 — POWER BI  │
 │  7 DAX Measures      │
 │  3-Page Dashboard    │
 │  Interactive Slicers │
 └──────────┬───────────┘
            │
            ▼
 ┌──────────────────────┐
 │  PHASE 4 — PYTHON    │
 │  ETL Pipeline        │
 │  Feature Engineering │
 │  9 Visualisations    │
 │  Random Forest ML    │
 └──────────────────────┘
            │
            ▼
   Business Insights + Churn Predictions + Recommendations
```

---

## 📊 Phase 1 — Advanced Excel

**What was built:** Cleaned table, 11 KPI formulas, XLOOKUP profile tool, 4 Pivot Tables with connected slicers, interactive dashboard.

```excel
Churn Rate      = COUNTIF(ChurnData[Closed],1)/COUNTA(ChurnData[Closed])*100  → 20.57%
Avg Age Churn   = AVERAGEIF(ChurnData[Closed],1,ChurnData[Age])                → 54.56 yrs
Avg Age Active  = AVERAGEIF(ChurnData[Closed],0,ChurnData[Age])                → 43.38 yrs
UPI Adoption    = COUNTIF(ChurnData[UPI Enabled],1)/COUNTA(...)*100            → 71%
XLOOKUP Tool    = XLOOKUP($B$1,ROW(ChurnData[Age])-ROW(ChurnData[#Headers]),ChurnData[Age])
```

### Excel Dashboard
![Excel Dashboard](screenshots/img_excel_dashboard.png)
*Figure 1 — Interactive Excel Dashboard: 4 charts (Geography, Gender, Age Group, Products) + 3 slicers all cross-filtering simultaneously*

### Pivot Tables
![Excel Pivots](screenshots/img_excel_pivots.png)
*Figure 2 — All 4 Pivot Tables with connected slicers. One click filters all tables and charts at once*

**Excel KPI Results:**

| KPI | Value |
|---|---|
| Total Customers | 9,843 |
| Total Churned | 2,025 |
| Churn Rate | **20.57%** |
| Avg Age (Churned) | **54.56 years** |
| Avg Age (Active) | 43.38 years |
| Avg Credit Score | 529.40 |
| Avg Yearly Income | ₹2,74,437 |
| Max Account Balance | ₹39,85,304 |
| UPI Adoption Rate | **71%** |

---

## 🗄 Phase 2 — MySQL

**What was built:** `bank_churn_db` database, `customers` table, 9 SQL queries using GROUP BY / CASE WHEN / CTEs / Window Functions, `vw_churn_summary` view.

### SQL Result — Churn by Geography
![MySQL Geo](screenshots/img_mysql_geo.png)
*Figure 3 — SQL query result: Mumbai 32.69% vs Delhi 16.91% vs Bengaluru 16.33%. Mumbai is almost exactly double the others.*

### SQL Result — Churned vs Active Profile
![MySQL Profile](screenshots/img_mysql_profile.png)
*Figure 4 — Profile comparison: Churned customers are 11.8 years older on average and hold ₹2.39L more in their accounts*

### Advanced SQL Techniques

| Technique | Purpose | Finding |
|---|---|---|
| GROUP BY | Segment-level churn rates | City, gender, product group breakdowns |
| CASE WHEN | Inline age group creation | 4 age segments created in SQL |
| CTE (WITH clause) | Multi-step churn contribution | 45-59 = 39.56% of all churned |
| RANK() OVER PARTITION BY | Balance rank within each city | Window function across geography |
| CREATE VIEW | Live Power BI data source | vw_churn_summary — 11 columns |

### MySQL View
![MySQL View](screenshots/img_mysql_view.png)
*Figure 5 — vw_churn_summary view with pre-calculated age_group column — connected directly to Power BI*

---

## 📈 Phase 3 — Power BI

**What was built:** Live MySQL connection, 7 DAX measures, 3-page dashboard with cross-filtering slicers.

```dax
Churn Rate %    = DIVIDE([Total Churned],[Total Customers],0)*100       → 20.57%
Avg Bal Churned = CALCULATE(AVERAGE([current_account]),[closed]=1)      → ₹11,74,828
Avg Bal Active  = CALCULATE(AVERAGE([current_account]),[closed]=0)      → ₹9,35,520
Avg Age Churned = CALCULATE(AVERAGE([age]),[closed]=1)                  → 54.48 years
```

### Page 1 — Executive Summary
![Power BI Page 1](screenshots/img_pbi_page1.png)
*Figure 6 — Executive Summary: 4 KPI cards + Geography bar chart + Gender bar chart + Donut + 3 interactive slicers*

### Page 2 — Segmentation Analysis
![Power BI Page 2](screenshots/img_pbi_page2.png)
*Figure 7 — Segmentation: Age Group column chart | Products churn | Age × Geography matrix (Mumbai 60+ = 65.09%!) | Scatter plot*

### Page 3 — Risk Profile
![Power BI Page 3](screenshots/img_pbi_page3.png)
*Figure 8 — Risk Profile: Churned customer table | UPI chart | Balance cards (Churned ₹11.74L vs Active ₹9.35L) | Income by age*

---

## 🐍 Phase 4 — Python & Machine Learning

**What was built:** Full ETL pipeline, 3 engineered features, 9 charts, Random Forest classifier.

```python
# 3 new features engineered
df['Age_Group']            = pd.cut(df['Age'], bins=[0,30,45,60,100],
                             labels=['Under 30','30-44','45-59','60+'])
df['Income_Segment']       = pd.cut(df['Estimated Yearly Income'], bins=[0,150000,300000,450000,600000],
                             labels=['Low','Medium','High','Very High'])
df['Balance_Income_Ratio'] = df['Current Account'] / (df['Estimated Yearly Income'] + 1)
```

### 6-Panel EDA Dashboard
![Python EDA](screenshots/img_py_charts.png)
*Figure 9 — EDA: Age (60+=48.5%) | Geography (Mumbai 32.7%) | Gender (Male 25.3%) | Credit KDE | Products (7=100%) | Age KDE (churned older)*

### Correlation Heatmap
![Correlation Heatmap](screenshots/img_corr_heatmap.png)
*Figure 10 — Correlation heatmap: Age is the only meaningful predictor (r=0.32). UPI near-zero (r=-0.01). Account & Products negatively correlated (r=-0.31).*

### Geography × Gender Heatmap ⭐ NEW INSIGHT
![Geo Gender](screenshots/img_geo_gender.png)
*Figure 11 — Cross-analysis REVEALS hidden segment: Mumbai Males = 37.8% — the highest-risk segment in the entire dataset. Invisible in single-dimension analysis.*

### Model Evaluation
![Model Eval](screenshots/img_model_eval.png)
*Figure 12 — Confusion Matrix: 1,495 Active correct | 174 Churned caught. Feature Importance: Age = 0.265 (26.5% of predictive power)*

### ROC Curve
![ROC Curve](screenshots/img_roc.png)
*Figure 13 — ROC AUC = 0.84. Strong discriminative performance. Curve rises steeply confirming model correctly ranks churned customers above active.*

---

## 📐 Quantified Results

> Every number below is directly derived from the analysis — not estimated.

### Churn by City

| City | Customers | Churned | Churn Rate | vs Average |
|---|---|---|---|---|
| Bengaluru | 4,937 | 806 | 16.33% | Below average |
| Delhi | 2,437 | 412 | 16.91% | Below average |
| **Mumbai** | **2,469** | **807** | **32.69%** | **2× national average** |

### Churn by Age Group

| Age Group | Customers | Churned | Churn Rate | % of Total Churn |
|---|---|---|---|---|
| Under 30 | 1,011 | 73 | 7.2% | 3.6% |
| 30 – 44 | 4,513 | 486 | 10.8% | 24.0% |
| **45 – 59** | **2,872** | **853** | **29.7%** | **39.56% — highest volume** |
| **60+** | **1,447** | **702** | **48.51%** | **34.67% — highest rate** |

### Churned vs Active Customer Profile

| Metric | Active | Churned | Difference |
|---|---|---|---|
| Average Age | 42.7 yrs | **54.5 yrs** | +11.8 years |
| Average Balance | ₹9,35,523 | **₹11,74,828** | +₹2,39,305 |
| Average Products | 3.09 | 2.81 | -0.28 |
| Average Credit Score | 530.4 | 525.4 | -5.0 |

### Churn by Product Count

| Products | Churn Rate | Signal |
|---|---|---|
| 2 products | 28.1% | High risk — cross-sell opportunity |
| 4 products | 7.6% | Sweet spot — target to retain |
| 5 products | 82.9% | Very high risk |
| **7 products** | **100%** | **Every single customer left** |

### Geography × Gender Matrix

| | Female | Male |
|---|---|---|
| Bengaluru | 12.9% | 20.5% |
| Delhi | 13.3% | 21.5% |
| **Mumbai** | **28.0%** | **37.8% 🚨** |

### Financial Impact Summary

| Metric | Value |
|---|---|
| Total churned customers | 2,025 |
| Avg balance per churned customer | ₹11,74,828 |
| **Estimated total at-risk assets** | **₹23.8 Crore** |
| Highest-risk city | Mumbai — 807 churned |
| Highest-risk segment | Mumbai Males — 37.8% |
| Churn model accuracy | 85% |
| ROC AUC | 0.84 |

---

## 🔑 Key Findings

**1. Age is the #1 predictor of churn** — Age has the strongest correlation with churn (r=0.32) and accounts for 26.5% of the Random Forest model's predictive power. Nearly half of all 60+ customers are leaving.

**2. Mumbai is a crisis city** — At 32.69%, Mumbai's churn is almost exactly double Bengaluru and Delhi despite having fewer customers. It produces the same absolute number of churned customers as Bengaluru (807 vs 806) with half the customer base.

**3. The bank is losing its wealthiest customers** — Churned customers hold ₹2.39 Lakhs MORE on average than active customers. Estimated total assets lost: ₹23.8 Crore.

**4. Mumbai Males = the hidden highest-risk segment** — Cross-analysis in Python revealed Mumbai Males churn at 37.8%, completely invisible in single-dimension analysis. This is the most actionable insight in the project.

**5. Products signal retention, not just engagement** — The 4-product sweet spot (7.6% churn) vs 2-product risk zone (28.1%) shows that cross-selling directly reduces attrition. 7-product customers had 100% churn — a product overload signal.

**6. UPI adoption cannot predict churn** — Despite 71% adoption overall, UPI correlation with churn is near-zero (r=-0.01). It cannot be used as a retention proxy.

---

## 💡 Business Recommendations

1. **Age-Targeted Retention Programme** — Proactive outreach for 45+ customers. Dedicated relationship managers for 60+ (48.51% churn). Focus resources where attrition is highest.

2. **Mumbai Emergency Investigation** — Exit surveys immediately for churned Mumbai customers. 32.69% churn needs urgent city-specific root cause identification.

3. **Cross-Sell to 2-Product Customers** — Move customers from the 28.1% risk zone (2 products) toward the 7.6% sweet spot (4 products) with structured cross-sell campaigns.

4. **VIP Retention for High-Balance Accounts** — Premium service for accounts above ₹10 Lakhs. These customers churn at higher rates and represent the biggest financial risk.

5. **Deploy ML Scoring Monthly** — Score all customers with the Random Forest model every month. Auto-trigger retention campaigns for the top 500 highest-risk individuals.

6. **Mumbai Male Dedicated Programme** — At 37.8%, this segment needs its own targeted strategy completely separate from general Mumbai retention efforts.

---

## ⚠️ Challenges Faced & Solved

| Challenge | Tool | Root Cause | Solution |
|---|---|---|---|
| BOM encoding error in CSV | Python | UTF-8 BOM in file header | `encoding='utf-8-sig'` |
| Age outliers up to 137 years | All tools | Source data entry errors | Filter `Age > 100` in every tool |
| Power BI Boolean type error | Power BI | MySQL TINYINT → True/False | Power Query → changed to Whole Number |
| MySQL auth failure in Power BI | Power BI | Windows auth used not DB auth | Switched to Database credentials tab |
| KPI visual needed trend axis | Power BI | Wrong visual type selected | Replaced with correct Card visual |
| DAX table name contains spaces | Power BI | Auto-generated table name | Wrapped in single quotes in all DAX |
| 4:1 class imbalance in data | Python | 80% active vs 20% churned | `class_weight='balanced'` applied |

---

## 📁 Project Structure

```
bank-customer-churn-analysis/
│
├── 📂 01_Raw_Data/
│   └── Dataset_master.csv
│
├── 📂 02_Excel/
│   └── Churn_Analysis.xlsx          ← Cleaned + Pivots + Dashboard + XLOOKUP
│
├── 📂 03_MySQL/
│   ├── create_table.sql
│   ├── cleaning.sql
│   ├── analysis_queries.sql
│   └── create_view.sql
│
├── 📂 04_PowerBI/
│   └── Bank_Churn_Dashboard.pbix    ← 3-page interactive dashboard
│
├── 📂 05_Python/
│   ├── churn_analysis.py
│   ├── requirements.txt
│   ├── churn_visualizations.png
│   ├── correlation_heatmap.png
│   ├── geo_gender_heatmap.png
│   ├── model_evaluation.png
│   └── roc_curve.png
│
├── 📂 06_Documentation/
│   └── Bank_Churn_Portfolio_FINAL.docx
│
├── 📂 screenshots/                  ← Images referenced in this README
│   ├── img_excel_dashboard.png
│   ├── img_excel_pivots.png
│   ├── img_mysql_geo.png
│   ├── img_mysql_profile.png
│   ├── img_mysql_view.png
│   ├── img_pbi_page1.png
│   ├── img_pbi_page2.png
│   ├── img_pbi_page3.png
│   ├── img_py_charts.png
│   ├── img_corr_heatmap.png
│   ├── img_geo_gender.png
│   ├── img_model_eval.png
│   └── img_roc.png
│
└── README.md
```

---

## ▶️ How to Run

### Python
```bash
git clone https://github.com/yourusername/bank-customer-churn-analysis.git
cd bank-customer-churn-analysis/05_Python
pip install -r requirements.txt
python churn_analysis.py
# Outputs: 9 PNG charts + printed model results
```

### MySQL
```sql
-- Run in this order in MySQL Workbench:
-- 1. 03_MySQL/create_table.sql
-- 2. Table Data Import Wizard → Dataset_master.csv
-- 3. 03_MySQL/cleaning.sql
-- 4. 03_MySQL/analysis_queries.sql
-- 5. 03_MySQL/create_view.sql
```

### Power BI
```
1. Open Bank_Churn_Dashboard.pbix
2. Transform Data → Update MySQL server to: localhost
3. Close & Apply → Refresh
4. All 3 pages populate automatically
```

---

## 📊 Project at a Glance

```
Dataset     : 9,843 clean records | 10 features | 1 target
Churn Rate  : 20.57% overall | 32.7% Mumbai | 48.5% age 60+
New Finding : Mumbai Males = 37.8% — highest-risk segment discovered
Balance Gap : Churned ₹11.74L avg vs Active ₹9.35L avg
At Risk     : ~₹23.8 Crore in managed assets
Model       : Random Forest | 85% Accuracy | AUC 0.84
Charts      : 9 PNG charts + 3-page Power BI dashboard
Tools       : Excel + MySQL + Power BI + Python — full 4-tool stack
```

---

## 👤 About the Author

**Sanket Kumar**
Data Analyst | Banking & Financial Analytics

- 📊 Skilled in Excel, MySQL, Power BI, Python
- 🏦 Focused on banking, retail, and financial analytics
- 🤖 

---

<div align="center">

*End-to-end analytics portfolio project — raw data to ML-powered business intelligence*

⭐ **Star this repo if you found it useful!** ⭐

</div>
