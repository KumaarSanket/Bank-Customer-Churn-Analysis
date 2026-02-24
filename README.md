# 🏦 Bank Customer Churn Analysis
### End-to-End Analytics Project | Excel · MySQL · Power BI · Python

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Tools](https://img.shields.io/badge/Tools-Excel%20%7C%20MySQL%20%7C%20PowerBI%20%7C%20Python-blue)
![Domain](https://img.shields.io/badge/Domain-Banking%20%7C%20Financial%20Analytics-orange)
![ML](https://img.shields.io/badge/ML%20Model-Random%20Forest-purple)
![Accuracy](https://img.shields.io/badge/Model%20Accuracy-85%25-success)
![AUC](https://img.shields.io/badge/ROC%20AUC-0.84-success)

---

## 📌 Table of Contents
- [Business Context](#-business-context)
- [Problem Statement](#-problem-statement)
- [Dataset Overview](#-dataset-overview)
- [Data Quality & Issues Found](#-data-quality--issues-found)
- [Tools & Technologies](#-tools--technologies)
- [Project Architecture](#-project-architecture)
- [Phase 1 — Advanced Excel](#-phase-1--advanced-excel)
- [Phase 2 — MySQL](#-phase-2--mysql)
- [Phase 3 — Power BI](#-phase-3--power-bi)
- [Phase 4 — Python & Machine Learning](#-phase-4--python--machine-learning)
- [Key Findings & Insights](#-key-findings--insights)
- [Quantified Business Impact](#-quantified-business-impact)
- [ML Model Results](#-ml-model-results)
- [Business Recommendations](#-business-recommendations)
- [Challenges Faced](#-challenges-faced)
- [Project Structure](#-project-structure)
- [How to Run](#-how-to-run)

---

## 💼 Business Context

A retail bank operating across **three major Indian cities — Bengaluru, Delhi, and Mumbai** — is experiencing a significant customer attrition problem. The bank offers multiple products including current accounts, UPI-linked services, and other financial instruments to a diverse customer base.

The bank's leadership needed answers to a critical question:

> *"Why are our customers leaving — and can we predict who will leave next before they do?"*

This project was built to answer exactly that, using a full analytics stack from raw data all the way to a deployed machine learning model.

---

## ❓ Problem Statement

The bank is losing **1 in 5 customers** (churn rate of **20.43%**) which directly impacts revenue, customer lifetime value, and brand reputation. Without understanding the root causes, retention efforts are generic and ineffective.

**Business Goals:**
- Identify the key demographic and behavioral factors driving churn
- Quantify churn risk across cities, age groups, gender, and product usage
- Build a predictive model to flag at-risk customers before they leave
- Deliver actionable recommendations to reduce churn by targeted intervention

---

## 📂 Dataset Overview

| Property | Details |
|---|---|
| **File** | Dataset_master.csv |
| **Raw Rows** | 9,929 |
| **Clean Rows** | 9,843 (after cleaning) |
| **Columns** | 10 |
| **Domain** | Indian Banking — Customer Churn |
| **Target Variable** | `Closed` (0 = Active, 1 = Churned) |

### Column Descriptions

| Column | Type | Description | Range |
|---|---|---|---|
| `Credit Score` | Numerical | Customer credit rating | 285 – 692 |
| `Geography` | Categorical | City of the customer | Bengaluru, Delhi, Mumbai |
| `Gender` | Categorical | Customer gender | Male, Female |
| `Age` | Numerical | Customer age | 17 – 100 |
| `Customer Since` | Numerical | Years with the bank | 0 – 8 years |
| `Current Account` | Numerical | Account balance in ₹ | ₹0 – ₹39,85,304 |
| `Num of Products` | Numerical | Bank products used | 2 – 7 |
| `UPI Enabled` | Binary | UPI active status | 0 or 1 |
| `Estimated Yearly Income` | Numerical | Annual income in ₹ | ₹32 – ₹5,47,947 |
| `Closed` | Binary | **TARGET** — Churned? | 0 or 1 |

---

## 🔍 Data Quality & Issues Found

**Overall Data Quality Score: 99.98%** — dataset was very clean with only 3 issues:

| Issue | Count | Action Taken |
|---|---|---|
| Completely blank rows | 2 rows | Dropped — all values NULL |
| Duplicate rows | 1 row | Removed using deduplication |
| Age outliers (Age > 100) | ~86 rows | Removed — physically impossible |

**Post-cleaning: 9,843 valid, analysis-ready records**

---

## 🛠 Tools & Technologies

| Tool | Version | Purpose | Key Outcome |
|---|---|---|---|
| **Microsoft Excel** | Office 365 | Data cleaning, exploration, dashboard | Pivot tables, XLOOKUP, interactive dashboard with slicers |
| **MySQL** | 8.0 | Database storage, SQL analysis | 9 analytical queries, CTEs, Window Functions, Views |
| **Power BI Desktop** | 1.108 | Interactive visual dashboard | 3-page dashboard with DAX measures and drill-through |
| **Python** | 3.11.9 | EDA, visualizations, ML model | 6 charts, Random Forest model — 85% accuracy, AUC 0.84 |
| **VS Code** | 1.108.2 | Python IDE | Full analysis pipeline |
| **Pandas / NumPy** | Latest | Data manipulation | Cleaning, feature engineering |
| **Matplotlib / Seaborn** | Latest | Visualization | 9 publication-quality charts |
| **Scikit-learn** | Latest | Machine Learning | Random Forest Classifier |

---

## 🏗 Project Architecture

```
Raw CSV Data (9,929 rows)
         │
         ▼
┌─────────────────┐
│  EXCEL PHASE    │  ── Clean data, Pivot Tables, XLOOKUP, Dashboard
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  MySQL PHASE    │  ── Import to DB, SQL cleaning, 9 queries, View created
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  POWER BI PHASE │  ── Connect to MySQL View, DAX measures, 3-page dashboard
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  PYTHON PHASE   │  ── EDA, Feature Engineering, ML Model, ROC Curve
└─────────────────┘
         │
         ▼
  Business Insights + Predictions + Recommendations
```

---

## 📊 Phase 1 — Advanced Excel

### What Was Built
- Imported raw CSV as a structured **Excel Table** named `ChurnData`
- Performed data cleaning — removed blanks, duplicates, and age outliers
- Built **Summary Stats sheet** with 11 KPI formulas using `COUNTIF`, `AVERAGEIF`, `COUNTA`
- Created **XLOOKUP-based customer profile lookup tool**
- Built **4 Pivot Tables** with connected slicers for interactive filtering
- Assembled a **full dashboard** with 4 charts + 3 slicers

### Key Formulas Used
```excel
Churn Rate    = COUNTIF(ChurnData[Closed],1)/COUNTA(ChurnData[Closed])*100
Avg Age Churn = AVERAGEIF(ChurnData[Closed],1,ChurnData[Age])
UPI Rate      = COUNTIF(ChurnData[UPI Enabled],1)/COUNTA(ChurnData[UPI Enabled])*100
Age Group     = IF([@Age]<30,"Under 30",IF([@Age]<45,"30-44",IF([@Age]<60,"45-59","60+")))
```

### Excel Dashboard Output

| KPI | Value |
|---|---|
| Total Customers | 9,927 |
| Total Churned | 2,028 |
| Churn Rate | 20.43% |
| Avg Age (Churned) | 54.56 |
| Avg Age (Active) | 43.38 |
| Avg Credit Score | 529.47 |
| Avg Yearly Income | ₹2,74,357 |
| Max Account Balance | ₹39,85,304 |
| UPI Adoption Rate | 70.49% |

---

## 🗄 Phase 2 — MySQL

### Database Setup
```sql
CREATE DATABASE bank_churn_db;
USE bank_churn_db;
```

### Table Created
```sql
CREATE TABLE customers (
    credit_score      INT,
    geography         VARCHAR(50),
    gender            VARCHAR(10),
    age               INT,
    customer_since    INT,
    current_account   DECIMAL(15,2),
    num_of_products   INT,
    upi_enabled       TINYINT(1),
    yearly_income     DECIMAL(12,2),
    closed            TINYINT(1)
);
```

**Records imported: 9,927 | Records after cleaning: 9,843**

### SQL Analysis Queries

**Churn by Geography:**
```sql
SELECT geography,
    COUNT(*) AS total,
    SUM(closed) AS churned,
    ROUND(SUM(closed)/COUNT(*)*100, 2) AS churn_rate
FROM customers
GROUP BY geography ORDER BY churn_rate DESC;
```

| Geography | Total | Churned | Churn Rate |
|---|---|---|---|
| **Mumbai** | 2,469 | 807 | **32.69%** 🚨 |
| Delhi | 2,437 | 412 | 16.91% |
| Bengaluru | 4,937 | 806 | 16.33% |

**Churned vs Active Customer Profile:**
```sql
SELECT CASE WHEN closed=1 THEN 'Churned' ELSE 'Active' END AS status,
    ROUND(AVG(credit_score),1) AS avg_credit,
    ROUND(AVG(age),1) AS avg_age,
    ROUND(AVG(current_account),2) AS avg_balance,
    ROUND(AVG(num_of_products),2) AS avg_products
FROM customers GROUP BY closed;
```

| Status | Avg Credit | Avg Age | Avg Balance | Avg Products |
|---|---|---|---|---|
| Active | 530.4 | 42.7 | ₹9,35,523 | 3.09 |
| **Churned** | 525.4 | **54.5** | **₹11,74,828** | **2.81** |

### Advanced SQL Techniques Used
- ✅ `GROUP BY` + `HAVING` for segmentation
- ✅ `CASE WHEN` for age group classification
- ✅ **CTE (Common Table Expressions)** for multi-step analysis
- ✅ **Window Functions** — `RANK() OVER (PARTITION BY geography)`
- ✅ **VIEW** created for Power BI connection

```sql
CREATE VIEW vw_churn_summary AS
SELECT geography, gender,
    CASE WHEN age < 30 THEN 'Under 30'
         WHEN age BETWEEN 30 AND 44 THEN '30-44'
         WHEN age BETWEEN 45 AND 59 THEN '45-59'
         ELSE '60+' END AS age_group,
    credit_score, age, current_account,
    num_of_products, upi_enabled, yearly_income, closed
FROM customers WHERE credit_score IS NOT NULL;
```

---

## 📈 Phase 3 — Power BI

### Connection
Power BI connected directly to **MySQL view `vw_churn_summary`** via MySQL Connector/NET

### DAX Measures Created

```dax
Total Customers  = COUNTROWS('bank_churn_db vw_churn_summary')
Total Churned    = CALCULATE(COUNTROWS(...), [closed]=1)
Total Active     = CALCULATE(COUNTROWS(...), [closed]=0)
Churn Rate %     = DIVIDE([Total Churned], [Total Customers], 0) * 100
Avg Age Churned  = CALCULATE(AVERAGE([age]), [closed]=1)
Avg Bal Churned  = CALCULATE(AVERAGE([current_account]), [closed]=1)
Avg Bal Active   = CALCULATE(AVERAGE([current_account]), [closed]=0)
```

### Dashboard Pages

**Page 1 — Executive Summary**
- 4 KPI Cards: Total Customers (9,843) | Churned (2,025) | Churn Rate (20.57%) | Avg Age Churned (54.48)
- Bar chart: Churn Rate by Geography
- Bar chart: Churn Rate by Gender
- Donut Chart: Active vs Churned split
- 3 Interactive Slicers: Geography | Gender | UPI Enabled

**Page 2 — Segmentation Analysis**
- Column chart: Churn by Age Group
- Column chart: Churn by Number of Products
- Matrix: Age Group × Geography churn rates
- Scatter Plot: Age vs Account Balance by Churn status

**Page 3 — Risk Profile**
- High-value churned customers table
- UPI Enabled vs Churn stacked bar
- Avg Balance: Active (₹9,35,520) vs Churned (₹11,74,828)
- Income by Age Group and Churn status

---

## 🐍 Phase 4 — Python & Machine Learning

### Libraries Used
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder, StandardScaler
from sklearn.metrics import classification_report, roc_auc_score
```

### Feature Engineering
```python
# Age Group segmentation
df['Age_Group'] = pd.cut(df['Age'],
                  bins=[0,30,45,60,100],
                  labels=['Under 30','30-44','45-59','60+'])

# Income segmentation
df['Income_Segment'] = pd.cut(df['Estimated Yearly Income'],
                       bins=[0,150000,300000,450000,600000],
                       labels=['Low','Medium','High','Very High'])

# Balance to income ratio
df['Balance_Income_Ratio'] = df['Current Account'] / (df['Estimated Yearly Income'] + 1)
```

### Model Training
```python
# Train/Test Split — 80/20 stratified
X_train: 7,874 rows
X_test : 1,969 rows

# Random Forest with class balancing
rf = RandomForestClassifier(n_estimators=100, random_state=42, class_weight='balanced')
```

### Visualizations Generated
| Chart | File | Insight |
|---|---|---|
| Churn by Age Group | churn_visualizations.png | 60+ at 48.5% churn |
| Churn by Geography | churn_visualizations.png | Mumbai at 32.7% |
| Churn by Gender | churn_visualizations.png | Males at 25.3% |
| Credit Score KDE | churn_visualizations.png | Similar distributions |
| Churn by Products | churn_visualizations.png | 7 products = 100% churn |
| Age Distribution KDE | churn_visualizations.png | Churned skewed older |
| Confusion Matrix | model_evaluation.png | 1,495 TP, 174 TN |
| Feature Importance | model_evaluation.png | Age = #1 predictor |
| ROC Curve | roc_curve.png | AUC = 0.84 |

---

## 🔑 Key Findings & Insights

### 1. Age is the Strongest Churn Predictor
| Age Group | Churn Rate |
|---|---|
| Under 30 | 7.2% |
| 30 – 44 | 10.8% |
| 45 – 59 | 29.7% |
| **60+** | **48.5%** 🚨 |

Nearly **half of all customers aged 60+** are closing their accounts.

### 2. Mumbai is a Critical Problem City
Mumbai's churn rate of **32.69%** is almost **double** that of Bengaluru (16.33%) and Delhi (16.91%) — requiring urgent city-specific investigation.

### 3. The Bank is Losing Its Wealthiest Customers
Churned customers have a significantly **higher average balance of ₹11,74,828** vs ₹9,35,523 for active customers. High-value customers are disproportionately leaving.

### 4. Fewer Products = Higher Churn Risk
| Products | Churn Rate |
|---|---|
| 2 products | 27.8% |
| 4 products | 7.6% |
| 5 products | 82.9% |
| 7 products | **100%** |

Customers using only 2 products are at high churn risk. Cross-selling reduces churn significantly.

### 5. Male Customers Churn More
Males churn at **25.31%** vs females at **16.63%** — a significant 9-point gap.

### 6. Age Contributes Most to Total Churn Volume
| Age Group | % of Total Churn |
|---|---|
| **45-59** | **39.56%** |
| 60+ | 34.67% |
| 30-44 | 22.27% |
| Under 30 | 3.51% |

The 45-59 group contributes the **most churn in absolute numbers** despite 60+ having the highest rate.

---

## 📐 Quantified Business Impact

| Metric | Value |
|---|---|
| Total customers at risk of churning | ~2,025 customers |
| Customers correctly identified by ML model | 174 out of 405 churned (43% recall) |
| Highest risk city | Mumbai — 807 churned customers |
| Highest risk segment | 60+ age group — 702 churned (48.5% rate) |
| Avg balance lost per churned customer | ₹11,74,828 |
| Total estimated balance at risk | ~₹23.8 Crore (2,025 × ₹11.7L avg) |
| UPI adoption among churned customers | 70% — same as active — not a differentiator |
| Model can flag at-risk customers with | 84% AUC accuracy |

---

## 🤖 ML Model Results

### Random Forest Classifier

| Metric | Active (0) | Churned (1) |
|---|---|---|
| Precision | 0.87 | 0.72 |
| Recall | 0.96 | 0.43 |
| F1-Score | 0.91 | 0.54 |
| Support | 1,564 | 405 |

**Overall Accuracy: 85% | ROC AUC: 0.84**

### Feature Importance Rankings
| Rank | Feature | Importance Score |
|---|---|---|
| 🥇 1 | Age | 0.265 |
| 🥈 2 | Current Account Balance | 0.154 |
| 🥉 3 | Estimated Yearly Income | 0.151 |
| 4 | Credit Score | 0.142 |
| 5 | Num of Products | 0.130 |
| 6 | Customer Since | 0.072 |
| 7 | Geography | 0.052 |
| 8 | Gender | 0.020 |
| 9 | UPI Enabled | 0.018 |

**Age alone accounts for 26.5% of the model's predictive power.**

---

## 💡 Business Recommendations

1. **Launch Age-Targeted Retention Program** — Customers aged 45+ should receive personalized outreach, loyalty rewards, and dedicated relationship managers before they consider leaving.

2. **Mumbai Emergency Intervention** — With a 32.69% churn rate, Mumbai needs immediate investigation. Conduct exit surveys with churned Mumbai customers to understand city-specific drivers.

3. **Cross-Sell to 2-Product Customers** — Customers using only 2 products churn at 27.8%. A structured cross-selling program targeting this segment could significantly reduce churn.

4. **Protect High-Balance Customers** — The bank is losing customers with ₹11.7L+ balances. Implement a VIP retention program for customers with balances above ₹10 Lakhs.

5. **Deploy ML Churn Prediction System** — Use the trained Random Forest model (AUC 0.84) in production to score all customers monthly and trigger proactive retention campaigns for high-risk individuals.

6. **Male Customer Retention Strategy** — Males churn 8.7 percentage points more than females. Investigate product preferences and satisfaction gaps specific to male customers.

---

## ⚠️ Challenges Faced

| Challenge | Tool | How It Was Resolved |
|---|---|---|
| CSV had BOM encoding issue | Python | Used `encoding='utf-8-sig'` parameter |
| Age outliers up to 137 years | Excel + MySQL + Python | Filtered Age > 100 across all tools |
| Power BI imported `closed` as Boolean | Power BI | Fixed data type in Power Query Editor — changed to Whole Number |
| MySQL connector authentication in Power BI | Power BI | Switched from Windows auth to Database auth tab |
| Wrong visual type (KPI vs Card) in Power BI | Power BI | Deleted KPI visuals, used correct Card visual |
| DAX measure failing due to True/False type | Power BI | Resolved after fixing data type in Power Query |
| Table name with spaces in DAX | Power BI | Wrapped in single quotes: `'bank_churn_db vw_churn_summary'` |

---

## 📁 Project Structure

```
Customer-Churn-Analysis/
│
├── 📂 01_Raw_Data/
│   └── Dataset_master.csv              # Original untouched dataset
│
├── 📂 02_Excel/
│   └── Churn_Analysis.xlsx             # Cleaned data + Pivot Tables + Dashboard
│
├── 📂 03_MySQL/
│   ├── create_table.sql                # DDL — table creation
│   ├── data_cleaning.sql               # Cleaning queries
│   ├── analysis_queries.sql            # 9 exploratory SQL queries
│   └── create_view.sql                 # vw_churn_summary view
│
├── 📂 04_PowerBI/
│   └── Bank_Churn_Dashboard.pbix       # 3-page interactive dashboard
│
├── 📂 05_Python/
│   ├── churn_analysis.py               # Main analysis + ML script
│   ├── churn_visualizations.png        # 6-chart EDA visualization
│   ├── model_evaluation.png            # Confusion matrix + Feature importance
│   └── roc_curve.png                   # ROC Curve (AUC = 0.84)
│
├── 📂 06_Documentation/
│   └── BankChurn_Analytics_Guide.docx  # Full project guide document
│
└── README.md                           # This file
```

---

## ▶️ How to Run

### Python Analysis
```bash
# Clone the repo
git clone https://github.com/yourusername/bank-churn-analysis.git
cd bank-churn-analysis/05_Python

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn

# Run the analysis
python churn_analysis.py
```

### MySQL Setup
```bash
# Open MySQL Workbench
# Run scripts in this order:
1. 03_MySQL/create_table.sql
2. Import Dataset_master.csv via Table Data Import Wizard
3. 03_MySQL/data_cleaning.sql
4. 03_MySQL/analysis_queries.sql
5. 03_MySQL/create_view.sql
```

### Power BI Dashboard
```
1. Open 04_PowerBI/Bank_Churn_Dashboard.pbix
2. Update MySQL connection to your local server
3. Refresh data
4. Explore all 3 dashboard pages
```

---

## 📊 Quick Stats Summary

```
Dataset    : 9,843 clean records | 10 features | 1 target variable
Churn Rate : 20.57% overall | 32.69% Mumbai | 48.51% age 60+
ML Model   : Random Forest | 85% Accuracy | 0.84 AUC
Top Factor : Age (26.5% feature importance)
Balance Gap: Churned ₹11.74L avg vs Active ₹9.35L avg
Tools      : Excel + MySQL + Power BI + Python
```

---

## 👤 Author

**Kumar Sanket**
Data Analyst | Banking & Financial Analytics

---

*Built as a complete end-to-end analytics portfolio project covering data cleaning, SQL analysis, interactive dashboards, and machine learning.*
