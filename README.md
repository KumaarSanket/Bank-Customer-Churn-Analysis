# 🏦 Bank Customer Churn Analysis
## End-to-End Analytics Project | Excel · MySQL · Power BI · Python

<div align="center">

![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![Excel](https://img.shields.io/badge/Excel-Advanced-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Python](https://img.shields.io/badge/Python-3.11.9-3776AB?style=for-the-badge&logo=python&logoColor=white)

![Accuracy](https://img.shields.io/badge/ML_Accuracy-85%25-success?style=flat-square)
![AUC](https://img.shields.io/badge/ROC_AUC-0.84-success?style=flat-square)
![Records](https://img.shields.io/badge/Records-9%2C843-blue?style=flat-square)
![Churn Rate](https://img.shields.io/badge/Churn_Rate-20.57%25-red?style=flat-square)
![Charts](https://img.shields.io/badge/Charts_Generated-9-purple?style=flat-square)

</div>

---

## 📌 Table of Contents
- [Business Context](#-business-context)
- [Problem Statement](#-problem-statement)
- [Dataset Overview](#-dataset-overview)
- [Tools & Tech Stack](#-tools--tech-stack)
- [Project Architecture](#-project-architecture)
- [Phase 1 — Excel](#-phase-1--advanced-excel)
- [Phase 2 — MySQL](#-phase-2--mysql)
- [Phase 3 — Power BI](#-phase-3--power-bi)
- [Phase 4 — Python & ML](#-phase-4--python--machine-learning)
- [Key Findings](#-key-findings--insights)
- [ML Model Results](#-ml-model-results)
- [Business Recommendations](#-business-recommendations)
- [Challenges Faced](#-challenges-faced)
- [Project Structure](#-project-structure)
- [How to Run](#-how-to-run)

---

## 💼 Business Context

A retail bank operating across **Bengaluru, Delhi, and Mumbai** was experiencing serious customer attrition with no data-driven understanding of why customers were leaving or who would leave next.

> *"The bank was losing 1 in every 5 customers — yet had no systematic way to predict or prevent it."*

This project was built to answer that problem completely — from raw CSV all the way to a deployed machine learning model — using a full 4-tool analytics stack.

---

## ❓ Problem Statement

| | |
|---|---|
| **The Problem** | 20.57% of customers are closing accounts — costing the bank an estimated **₹23.8 Crore** in managed assets |
| **The Gap** | No understanding of which customers are at risk or why they leave |
| **The Goal** | Identify root causes, quantify risk segments, and build a predictive ML model |
| **The Outcome** | 85% accurate Random Forest model + full interactive dashboard for ongoing monitoring |

---

## 📂 Dataset Overview

| Property | Value |
|---|---|
| **Source File** | Dataset_master.csv |
| **Raw Records** | 9,929 rows |
| **Clean Records** | 9,843 rows (after removing blanks, duplicates, outliers) |
| **Features** | 10 columns (8 numerical, 2 categorical) |
| **Target Variable** | `Closed` — 0 = Active, 1 = Churned |
| **Cities Covered** | Bengaluru (50%), Mumbai (25%), Delhi (25%) |
| **Overall Churn Rate** | **20.57%** — 2,025 out of 9,843 customers left |

### Column Reference

| Column | Type | Range | Notes |
|---|---|---|---|
| Credit Score | Numerical | 285 – 692 | Avg: 529.40 |
| Geography | Categorical | 3 cities | Bengaluru, Delhi, Mumbai |
| Gender | Categorical | Male / Female | 45.5% Male, 54.5% Female |
| Age | Numerical | 17 – 100 | Avg: 45.13 yrs |
| Customer Since | Numerical | 0 – 8 yrs | Avg: 4.42 yrs |
| Current Account | Numerical | ₹0 – ₹39.85L | Avg: ₹9.84L |
| Num of Products | Numerical | 2 – 7 | Avg: 3.03 |
| UPI Enabled | Binary | 0 or 1 | 71% enabled |
| Estimated Yearly Income | Numerical | ₹32 – ₹5.47L | Avg: ₹2.74L |
| **Closed** | **Binary** | **0 or 1** | **TARGET VARIABLE** |

### Data Quality Issues Fixed

| Issue | Count | Fix Applied |
|---|---|---|
| Blank rows | 2 | Dropped — all values NULL |
| Duplicate rows | 1 | Removed via deduplication |
| Age outliers (>100) | ~86 | Removed — impossible values |
| BOM encoding | Header | `encoding='utf-8-sig'` used |

**Overall Data Quality Score: 99.98%** ✅

---

## 🛠 Tools & Tech Stack

| Tool | Version | Purpose | Outcome |
|---|---|---|---|
| **Microsoft Excel** | Office 365 | Cleaning, Pivot Tables, Dashboard | Interactive dashboard, XLOOKUP lookup tool |
| **MySQL** | 8.0 | Relational DB, SQL analysis | 9 queries, CTEs, Window Functions, View |
| **Power BI** | 1.108 | Interactive visual dashboard | 3-page dashboard, 7 DAX measures |
| **Python** | 3.11.9 | EDA, Feature Engineering, ML | 9 charts, Random Forest 85% / AUC 0.84 |
| **VS Code** | 1.108.2 | Python IDE | Full pipeline in single script |
| **Pandas / NumPy** | Latest | Data manipulation | Cleaning + 3 engineered features |
| **Matplotlib / Seaborn** | Latest | Visualization | 9 publication-quality PNG charts |
| **Scikit-learn** | Latest | Machine Learning | Random Forest + ROC Curve |

---

## 🏗 Project Architecture

```
Raw CSV (9,929 rows)
       │
       ▼
┌─────────────────────┐
│   PHASE 1: EXCEL    │  → Clean + Pivot Tables + Dashboard + XLOOKUP Tool
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│   PHASE 2: MySQL    │  → Import to DB → 9 SQL Queries → View Created
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  PHASE 3: POWER BI  │  → MySQL View → DAX Measures → 3-Page Dashboard
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│  PHASE 4: PYTHON    │  → EDA → Feature Engineering → ML Model → 9 Charts
└─────────────────────┘
           │
           ▼
  Business Insights + Predictions + Recommendations
```

---

## 📊 Phase 1 — Advanced Excel

**What was built:** Cleaned dataset, 11 KPI formulas, XLOOKUP customer profile tool, 4 connected Pivot Tables, interactive dashboard with slicers.

### Key Formulas Used
```excel
Churn Rate     = COUNTIF(ChurnData[Closed],1)/COUNTA(ChurnData[Closed])*100
Avg Age Churn  = AVERAGEIF(ChurnData[Closed],1,ChurnData[Age])
UPI Rate       = COUNTIF(ChurnData[UPI Enabled],1)/COUNTA(ChurnData[UPI Enabled])*100
Age Group      = IF([@Age]<30,"Under 30",IF([@Age]<45,"30-44",IF([@Age]<60,"45-59","60+")))
XLOOKUP Tool   = XLOOKUP($B$1,ROW(ChurnData[Age])-ROW(ChurnData[#Headers]),ChurnData[Age])
```

### Excel KPI Results

| KPI | Value |
|---|---|
| Total Customers | 9,843 |
| Total Churned | 2,025 |
| Churn Rate | **20.57%** |
| Avg Age Churned | 54.56 years |
| Avg Age Active | 43.38 years |
| Avg Credit Score | 529.40 |
| Avg Yearly Income | ₹2,74,437 |
| Max Account Balance | ₹39,85,304 |
| UPI Adoption Rate | **71%** |

### Excel Dashboard
![Excel Dashboard](screenshots/img_excel_dashboard.png)
*4-chart interactive Excel dashboard — Geography, Gender, Age Group & Products analysis with 3 slicers filtering all charts simultaneously*

### Excel Pivot Tables
![Excel Pivots](screenshots/img_excel_pivots.png)
*All 4 Pivot Tables with connected slicers — every click updates all charts in real time*

---

## 🗄 Phase 2 — MySQL

**What was built:** `bank_churn_db` database, `customers` table (9,843 records), 9 SQL queries, advanced CTEs + Window Functions, `vw_churn_summary` view for Power BI.

### SQL Results — Churn by Geography
![MySQL Geo Results](screenshots/img_mysql_geo.png)
*Mumbai: 32.69% | Delhi: 16.91% | Bengaluru: 16.33% — Mumbai nearly 2x the rest*

### SQL Results — Churned vs Active Profile
![MySQL Profile](screenshots/img_mysql_profile.png)
*Churned: avg age 54.5, avg balance ₹11.74L | Active: avg age 42.7, avg balance ₹9.35L*

### Advanced SQL Techniques Used

| Technique | Purpose | Result |
|---|---|---|
| GROUP BY + HAVING | Segment-level churn aggregation | City, gender, age group rates |
| CASE WHEN | Age group inline classification | 4 segments created |
| CTE | Multi-step contribution analysis | 45-59 = 39.56% of total churn |
| RANK() OVER PARTITION BY | Window function ranking | Balance rank within each city |
| CREATE VIEW | Saved enriched query for Power BI | `vw_churn_summary` — 11 columns |

### MySQL View Created
![MySQL View](screenshots/img_mysql_view.png)
*`vw_churn_summary` — all columns including pre-calculated `age_group`, used as Power BI data source*

---

## 📈 Phase 3 — Power BI

**What was built:** Direct MySQL connection, 7 DAX measures, 3-page interactive dashboard with cross-filtering slicers.

### DAX Measures
```dax
Total Customers  = COUNTROWS('bank_churn_db vw_churn_summary')
Total Churned    = CALCULATE(COUNTROWS(...), [closed]=1)
Total Active     = CALCULATE(COUNTROWS(...), [closed]=0)
Churn Rate %     = DIVIDE([Total Churned],[Total Customers],0)*100
Avg Age Churned  = CALCULATE(AVERAGE([age]), [closed]=1)
Avg Bal Churned  = CALCULATE(AVERAGE([current_account]), [closed]=1)
Avg Bal Active   = CALCULATE(AVERAGE([current_account]), [closed]=0)
```

### Page 1 — Executive Summary
![Power BI Page 1](screenshots/img_pbi_page1.png)
*KPI Cards: 9,843 customers | 2,025 churned | 20.57% churn rate | 54.48 avg age churned + Geography/Gender bar charts + Donut chart + 3 interactive slicers*

### Page 2 — Segmentation Analysis
![Power BI Page 2](screenshots/img_pbi_page2.png)
*Age Group column chart | Products churn chart | Age×Geography matrix — Mumbai 60+ = 65.09%! | Age vs Balance scatter*

### Page 3 — Risk Profile
![Power BI Page 3](screenshots/img_pbi_page3.png)
*Churned customer table | UPI bar chart | Balance cards: Active ₹9.35L vs Churned ₹11.74L | Income by Age Group*

---

## 🐍 Phase 4 — Python & Machine Learning

**What was built:** Full EDA pipeline, 3 engineered features, 9 charts, Random Forest model 85% accuracy / AUC 0.84.

### Feature Engineering
```python
df['Age_Group']           = pd.cut(df['Age'], bins=[0,30,45,60,100],
                            labels=['Under 30','30-44','45-59','60+'])
df['Income_Segment']      = pd.cut(df['Estimated Yearly Income'], bins=[0,150000,300000,450000,600000],
                            labels=['Low','Medium','High','Very High'])
df['Balance_Income_Ratio']= df['Current Account'] / (df['Estimated Yearly Income'] + 1)
```

### Chart 1 — 6-Panel EDA Dashboard
![Python EDA Charts](screenshots/img_py_charts.png)
*Age Group (60+ = 48.5%) | Geography (Mumbai 32.7%) | Gender (Male 25.3%) | Credit Score KDE (nearly identical — weak predictor) | Products (7 products = 100% churn!) | Age KDE (churned clearly skewed older)*

### Chart 2 — Correlation Heatmap
![Correlation Heatmap](screenshots/img_corr_heatmap.png)
*Age has the strongest correlation with churn (r = 0.32). Current Account & Num of Products negatively correlated (r = -0.31). Most features are independent — ideal for Random Forest.*

### Chart 3 — Geography × Gender Heatmap
![Geo Gender Heatmap](screenshots/img_geo_gender.png)
*Mumbai Males = 37.8% churn — the single highest risk segment in the entire dataset. All Mumbai segments far exceed other cities regardless of gender.*

### Chart 4 — Model Evaluation
![Model Evaluation](screenshots/img_model_eval.png)
*Confusion Matrix: 1,495 Active correctly predicted | 174 Churned correctly caught. Feature Importance: Age dominates at 0.265 importance score.*

### Chart 5 — ROC Curve
![ROC Curve](screenshots/img_roc.png)
*ROC AUC = 0.84 — strong discriminative performance. Curve rises steeply confirming the model correctly identifies churned customers.*

### Model Configuration & Results

```
Train/Test Split : 80/20 stratified (7,874 train | 1,969 test)
Model            : RandomForestClassifier(n_estimators=100, class_weight='balanced')
Preprocessing    : StandardScaler on all 9 features
```

| Metric | Active (0) | Churned (1) | Overall |
|---|---|---|---|
| Precision | 0.87 | 0.72 | — |
| Recall | 0.96 | 0.43 | — |
| F1-Score | 0.91 | 0.54 | — |
| Support | 1,564 | 405 | 1,969 |
| **Accuracy** | — | — | **85%** |
| **ROC AUC** | — | — | **0.84** |

### Feature Importance Rankings

| Rank | Feature | Score |
|---|---|---|
| 🥇 1 | **Age** | **0.265** |
| 🥈 2 | Current Account | 0.154 |
| 🥉 3 | Yearly Income | 0.151 |
| 4 | Credit Score | 0.142 |
| 5 | Num of Products | 0.130 |
| 6 | Customer Since | 0.072 |
| 7 | Geography | 0.052 |
| 8 | Gender | 0.020 |
| 9 | UPI Enabled | 0.018 |

---

## 🔑 Key Findings & Insights

### Finding 1 — Age is the #1 Churn Driver

| Age Group | Total | Churned | Churn Rate |
|---|---|---|---|
| Under 30 | 1,011 | 73 | 7.2% |
| 30 – 44 | 4,513 | 486 | 10.8% |
| 45 – 59 | 2,872 | 853 | 29.7% |
| **60+** | **1,447** | **702** | **48.5% 🚨** |

### Finding 2 — Mumbai is a Crisis City (32.7% vs 16% elsewhere)

| City | Churn Rate | Risk |
|---|---|---|
| Bengaluru | 16.3% | Normal |
| Delhi | 16.9% | Normal |
| **Mumbai** | **32.7%** | **Critical 🚨** |

### Finding 3 — Bank is Losing Its Wealthiest Customers

| Status | Avg Balance | Avg Age |
|---|---|---|
| Active | ₹9,35,523 | 42.7 yrs |
| **Churned** | **₹11,74,828** | **54.5 yrs** |

> **₹23.8 Crore estimated in lost managed assets (2,025 customers × ₹11.74L avg)**

### Finding 4 — Mumbai Males = Highest Risk Segment

| Segment | Churn Rate |
|---|---|
| Bengaluru Female | 12.9% |
| Delhi Female | 13.3% |
| Bengaluru Male | 20.5% |
| Delhi Male | 21.5% |
| Mumbai Female | 28.0% |
| **Mumbai Male** | **37.8% 🚨** |

---

## 💡 Business Recommendations

1. **Age-Targeted Retention Program** — Proactive outreach for customers aged 45+. Dedicated relationship managers for 60+ (48.5% churn).
2. **Mumbai Emergency Investigation** — Exit surveys immediately. 32.7% churn needs urgent city-specific root cause analysis.
3. **Cross-Sell Campaign** — Move 2-product customers (28.1% churn) to 3–4 products (7.6% churn sweet spot).
4. **VIP Retention Program** — Premium service for accounts above ₹10 Lakhs before they consider leaving.
5. **Deploy ML Scoring Monthly** — Score all customers with the Random Forest model. Auto-trigger retention for top 500 high-risk customers.
6. **Mumbai Male Strategy** — At 37.8% churn, needs a dedicated targeted engagement program.

---

## ⚠️ Challenges Faced & Solved

| Challenge | Tool | Solution |
|---|---|---|
| BOM encoding error in CSV | Python | `encoding='utf-8-sig'` |
| Age outliers up to 137 years | All tools | Filter `Age > 100` across all tools |
| Power BI Boolean type error | Power BI | Power Query → Whole Number |
| MySQL auth failure in Power BI | Power BI | Switch to Database credentials tab |
| Wrong KPI visual (needs trend axis) | Power BI | Replaced with Card visual |
| DAX table name with spaces | Power BI | Wrap in single quotes |
| 4:1 class imbalance in ML | Python | `class_weight='balanced'` |

---

## 📁 Project Structure

```
bank-customer-churn-analysis/
├── 📂 01_Raw_Data/
│   └── Dataset_master.csv
├── 📂 02_Excel/
│   └── Churn_Analysis.xlsx
├── 📂 03_MySQL/
│   ├── create_table.sql
│   ├── cleaning.sql
│   ├── analysis_queries.sql
│   └── create_view.sql
├── 📂 04_PowerBI/
│   └── Bank_Churn_Dashboard.pbix
├── 📂 05_Python/
│   ├── churn_analysis.py
│   ├── requirements.txt
│   ├── churn_visualizations.png
│   ├── correlation_heatmap.png
│   ├── geo_gender_heatmap.png
│   ├── model_evaluation.png
│   └── roc_curve.png
├── 📂 06_Documentation/
│   └── Bank_Churn_Portfolio_Document.docx
├── 📂 screenshots/
│   └── (all chart PNGs for README display)
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
```

### MySQL
```sql
-- Run in order in MySQL Workbench:
-- 1. create_table.sql
-- 2. Import Dataset_master.csv via Table Data Import Wizard
-- 3. cleaning.sql → analysis_queries.sql → create_view.sql
```

### Power BI
```
1. Open Bank_Churn_Dashboard.pbix
2. Transform Data → update MySQL server to localhost
3. Refresh data — all 3 pages load automatically
```

---

## 📊 Project Summary

```
Dataset     : 9,843 clean records | 10 features | 1 target variable
Churn Rate  : 20.57% overall | 32.7% Mumbai | 48.5% age 60+
New Insight : Mumbai Males = 37.8% — highest-risk segment discovered
Balance Gap : Churned ₹11.74L avg vs Active ₹9.35L avg
At-Risk     : ~₹23.8 Crore in managed assets
ML Model    : Random Forest | 85% Accuracy | AUC 0.84 | Age = #1 predictor
Charts      : 9 publication-quality charts + 3-page Power BI dashboard
Tools       : Excel + MySQL + Power BI + Python — full 4-tool stack
```

---

## 👤 Author

**Sanket Kumar** | Data Analyst | Banking & Financial Analytics

---

<div align="center">

*Complete end-to-end analytics portfolio project — raw data to ML model*

⭐ **Star this repo if you found it useful!** ⭐

</div>
