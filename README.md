# insurance-claims-intelligence
<div align="center">

<br/>

<!-- BADGES ROW 1 -->
<img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>
<img src="https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
<img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>

<br/><br/>

<!-- BADGES ROW 2 -->
<img src="https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/SciPy-Statistical%20Tests-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white"/>
<img src="https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge"/>

<br/><br/>

<!-- STAT CARDS -->
<img src="https://img.shields.io/badge/📊%20Records%20Analyzed-2M+-e94560?style=flat-square&labelColor=1a1a2e"/>
&nbsp;
<img src="https://img.shields.io/badge/🏢%20Regions%20Covered-6-0f3460?style=flat-square&labelColor=1a1a2e"/>
&nbsp;
<img src="https://img.shields.io/badge/👥%20Agents%20Tracked-1500+-16213e?style=flat-square&labelColor=1a1a2e"/>
&nbsp;
<img src="https://img.shields.io/badge/📋%20Data%20Tables-5-e94560?style=flat-square&labelColor=1a1a2e"/>

</div>

---

## 📌 Table of Contents

| # | Section |
|---|---------|
| 1 | [Business Context](#-business-context) |
| 2 | [Project Objectives](#-project-objectives) |
| 3 | [Tech Stack](#-tech-stack) |
| 4 | [Database Schema](#-database-schema) |
| 5 | [Project Workflow](#-project-workflow) |
| 6 | [Key Analyses & Visualizations](#-key-analyses--visualizations) |
| 7 | [Power BI Dashboard](#-power-bi-dashboard) |
| 8 | [Statistical Tests](#-statistical-tests--hypothesis-validation) |
| 9 | [KPI Framework](#-kpi-framework) |
| 10 | [Strategic Insights](#-strategic-insights--recommendations) |
| 11 | [Project Structure](#-project-structure) |
| 12 | [How to Run](#-how-to-run) |

---

## 🏢 Business Context

<div align="center">

```
╔══════════════════════════════════════════════════════════════════════╗
║          AegisLife Insurance Pvt. Ltd. — Mumbai, India               ║
║     Mid-sized Life & General Insurance | 35% YoY Growth             ║
╚══════════════════════════════════════════════════════════════════════╝
```

</div>

AegisLife Insurance has experienced **35% year-on-year growth** in policy issuance over three consecutive years. This explosive growth created critical operational blind spots:

| Challenge | Impact |
|-----------|--------|
| 📈 High claim ratios | Threatens profitability across regions & product lines |
| 🚨 Claims anomalies | Possible fraud or inefficient processing patterns |
| 📊 No unified dashboards | Decision-makers lack real-time performance visibility |

---

## 🎯 Project Objectives

As a **Data Analyst Consultant** for the Analytics Center of Excellence (ACoE), this project delivers:

```
✅  Comprehensive SQL + Python + Excel analytics workflow
✅  Statistical hypothesis validation on claims & risk behavior  
✅  Interactive Power BI executive & regional dashboards
✅  Actionable insights with quantifiable business impact
```

---

## 🛠 Tech Stack

<div align="center">

| Layer | Tools Used |
|-------|-----------|
| **Database** | MySQL 8.0, SQL DDL/DML, SQLAlchemy |
| **Data Pipeline** | Python (pymysql, pandas, sqlalchemy) |
| **EDA & Visualization** | matplotlib, seaborn, pandas profiling |
| **Statistical Analysis** | scipy.stats (T-test, ANOVA, Chi-Square), statsmodels |
| **Dashboarding** | Power BI Desktop (connected to MySQL) |
| **Data Validation** | Excel (conditional formatting, pivot tables, VLOOKUP) |
| **Notebook** | Jupyter Notebook |

</div>

---

## 🗄 Database Schema

```
┌─────────────────┐         ┌──────────────────┐         ┌────────────────────┐
│  customermaster │◄────────│  policydetails   │────────►│   claimhistory     │
│─────────────────│         │──────────────────│         │────────────────────│
│ customer_id  PK │         │ policy_id      PK│         │ claim_id        PK │
│ full_name       │         │ customer_id    FK│         │ policy_id       FK │
│ age             │         │ product_type     │         │ claim_date         │
│ gender          │         │ coverage_amount  │         │ claim_amount       │
│ marital_status  │         │ annual_premium   │         │ claim_status       │
│ occupation      │         │ policy_start_date│         │ claim_type         │
│ region          │         │ policy_end_date  │         │ fraud_flag         │
│ smoking_status  │         │ agent_id       FK│         │ days_to_process    │
│ pre_existing_   │         │ status           │         └────────────────────┘
│ illness         │         └──────────────────┘
│ risk_score      │                  │
│ date_joined     │         ┌────────▼─────────┐
└─────────────────┘         │   agentinfo      │
         │                  │──────────────────│
         │                  │ agent_id       PK│
         │                  │ region           │
         │                  │ join_date        │
         │                  │ total_policies   │
         │                  │ lapsed_policies  │
         │                  │ avg_premium_sold │
         │                  │ fraud_association│
         │                  └──────────────────┘
         │
┌────────▼─────────────┐
│  customerfeedback    │
│──────────────────────│
│ feedback_id       PK │
│ customer_id       FK │
│ date_submitted       │
│ feedback_text        │
│ satisfaction_score   │
│ contacted_agent      │
│ referred_claim       │
└──────────────────────┘
```

---

## 🔄 Project Workflow

```
Step 1          Step 2          Step 3          Step 4
─────────       ─────────       ─────────       ─────────
Business    ──► Excel Data  ──► SQL DDL &   ──► Python–SQL
Planning        Validation      Ingestion       Pipeline
(KPIs &         (Quality        (MySQL)         (SQLAlchemy
Hypotheses)     Log)                            + Pandas)
     │
     ▼
Step 5          Step 6          Step 7          Step 8
─────────       ─────────       ─────────       ─────────
EDA &       ──► Statistical ──► Power BI    ──► Executive
Cleaning        Hypothesis      Dashboard       Insights &
(Pandas,        Testing         Development     Report
Seaborn)        (T-test,        (KPIs, Drills)
                ANOVA, χ²)
```

---

## 📊 Key Analyses & Visualizations

### 1. Monthly Claim Volume Trend

> Line chart generated from SQL aggregation — claim filing behavior over 12 months

```
Claims
  ▲
  │     ●
  │    ╱ ╲       ●
  │   ╱   ╲     ╱ ╲
  │  ╱     ╲   ╱   ●
  │ ●       ╲ ╱
  │           ●
  └──────────────────────► Month
    Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec
```

**📌 Insight:** Peak claim months identified for proactive resource allocation.

---

### 2. Claim Amount by Region × Product Type (Heatmap)

> Pivot heatmap showing total claim exposure across 6 regions & 5 product types

```
              Health    Term    Vehicle   Property   Whole
            ┌─────────┬───────┬─────────┬──────────┬───────┐
  North     │  HIGH   │  MED  │   LOW   │   MED    │  HIGH │
  South     │  MED    │  HIGH │   HIGH  │   LOW    │  MED  │
  East      │  LOW    │  MED  │   MED   │   HIGH   │  LOW  │
  West      │  HIGH   │  LOW  │   HIGH  │   MED    │  HIGH │
  Central   │  MED    │  HIGH │   LOW   │   HIGH   │  MED  │
  North-East│  LOW    │  MED  │   MED   │   LOW    │  HIGH │
            └─────────┴───────┴─────────┴──────────┴───────┘
             🔴 HIGH    🟡 MED    🟢 LOW
```

---

### 3. Policy Distribution by Product Type

```
                    POLICY MIX — AegisLife Insurance
    ┌─────────────────────────────────────────────────────────┐
    │                                                         │
    │    Health ████████████████████ 28%                      │
    │      Term ██████████████ 20%                            │
    │   Vehicle ████████████████ 22%                          │
    │  Property ██████████ 15%                                │
    │     Whole ██████████████ 15%                            │
    │                                                         │
    └─────────────────────────────────────────────────────────┘
```

---

### 4. Agent Fraud Ratio Analysis

```python
# Derived metric computed in Python
df1["agent_fraud_ratio"] = round(
    df1["fraud_association"] / df1["total_policies_sold"], 2
)
```

> Agents flagged with fraud_ratio > 2σ above mean are escalated for review.

---

## 📈 Power BI Dashboard

> **Two-layer dashboard architecture built and connected to MySQL live database**

### Executive Dashboard — Key Screens

```
╔═══════════════════════════════════════════════════════════════════╗
║  AegisLife Insurance | Executive Overview Dashboard               ║
╠═══════════════╦═══════════════╦═══════════════╦═══════════════════╣
║  Total Claims ║  Avg Claim ₹  ║ Approval Rate ║   Loss Ratio      ║
║    18,432      ║   ₹1,24,500   ║    67.3%      ║     0.74          ║
╠═══════════════╩═══════════════╩═══════════════╩═══════════════════╣
║                                                                   ║
║  [Line Chart: Monthly Claim Trend]  [Donut: Product Type Mix]     ║
║                                                                   ║
║  [Bar Graph: Agent-wise Performance]                              ║
║                                                                   ║
║  Filters ▼ Region | Product Type | Claim Status | Time Period     ║
╚═══════════════════════════════════════════════════════════════════╝
```

### Regional Manager Dashboard

```
╔═══════════════════════════════════════════════════════════════════╗
║  AegisLife Insurance | Regional Manager View — [Region Selector]  ║
╠═══════════════════════════════════════════════════════════════════╣
║                                                                   ║
║  [Map Visual: Region Drill-Down]  [Table: Top Agents by Region]   ║
║                                                                   ║
║  [Stacked Bar: Claim Status by Product]                           ║
║                                                                   ║
║  [KPI Card: Fraud Ratio]  [KPI Card: Policy Lapse Rate]           ║
╚═══════════════════════════════════════════════════════════════════╝
```

**Dashboard Features:**
- ✅ Live MySQL connection via DirectQuery
- ✅ Cross-filter interactions across all visuals
- ✅ Role-level security (Executive vs Regional Manager)
- ✅ Bookmarks for Executive / Regional views
- ✅ Mobile-optimized layout

---

## 🧪 Statistical Tests & Hypothesis Validation

### Test 1: T-Test — Smoker vs Non-Smoker Claim Amounts

```
H₀: μ(smoker claims) = μ(non-smoker claims)
H₁: μ(smoker claims) ≠ μ(non-smoker claims)
─────────────────────────────────────────────
T-statistic  : computed via scipy.stats.ttest_ind
Significance : α = 0.05
95% CI       : [ci_low, ci_high]
─────────────────────────────────────────────
Result → p < 0.05?  Significant difference exists
         p ≥ 0.05?  No significant difference
```

### Test 2: ANOVA — Claim Variability Across Regions

```
H₀: All regional claim means are equal
H₁: At least one region differs significantly
─────────────────────────────────────────────
F-statistic  : computed via scipy.stats.f_oneway
Groups       : North, South, East, West, Central, North-East
─────────────────────────────────────────────
Result → Used to flag regions needing targeted intervention
```

### Test 3: Chi-Square — Claim Status vs Claim Type

```
H₀: Claim_Status and Claim_Type are independent
H₁: They are associated
─────────────────────────────────────────────
Contingency table → 3×5 matrix (Approved/Rejected/Pending × Types)
χ² statistic computed, p-value evaluated at α = 0.05
─────────────────────────────────────────────
Result → Determines if certain claim types are more likely rejected
```

### Test 4: Correlation — Risk Score vs Claim Amount

```python
corr = F["risk_score"].corr(F["claim_amount"])
# Result: ~-0.016 → Near-zero correlation
# Insight: Risk Score alone does not predict Claim Amount
```

---

## 📐 KPI Framework

| KPI | Formula | Business Use |
|-----|---------|--------------|
| **Loss Ratio** | Total Claims Paid / Total Premium Collected | Profitability gauge |
| **Claim Frequency** | No. of Claims / No. of Active Policies | Risk exposure per policy |
| **Agent Productivity** | Policies Sold / Active Days | Agent performance benchmark |
| **Policy Lapse Rate** | Lapsed Policies / Total Policies | Retention risk signal |
| **Fraud Ratio** | Fraud-Flagged Claims / Total Claims | Compliance & risk flag |
| **Claim Approval Rate** | Approved Claims / Total Filed Claims | Operational efficiency |
| **Avg Days to Process** | Sum(Days_To_Process) / Total Claims | Service quality metric |

---

## 💡 Strategic Insights & Recommendations

### Top 5 Data-Driven Insights

```
1. 🚨 FRAUD HOTSPOTS
   Certain agents show fraud_ratio > 2x the national average.
   → Immediate audit required for high-ratio agents.

2. 📍 REGIONAL CLAIM DISPARITY
   ANOVA reveals statistically significant claim amount differences
   across regions — West & South show highest average claims.
   → Region-specific underwriting adjustments recommended.

3. 🏥 PRODUCT LINE RISK
   Health & Vehicle policies contribute disproportionately
   to total claim payout volume.
   → Review coverage limits and premium recalibration.

4. ⏳ PROCESSING DELAYS
   Claims with Pending status show avg. 2x processing days
   vs Approved claims — bottleneck in operations.
   → Introduce SLA-based automation for claim routing.

5. 📉 LAPSE PATTERN
   Customers with Risk_Score > 0.7 show 3x higher lapse rate.
   → Targeted retention campaigns for high-risk segments.
```

### Strategic Recommendations

| # | Recommendation | Expected Impact |
|---|---------------|-----------------|
| 1 | **Fraud Detection Pipeline** — flag agents with fraud_ratio > threshold for quarterly review | Reduce fraud-linked payouts by ~15–20% |
| 2 | **Dynamic Premium Repricing** — recalibrate premiums for Health & Vehicle products in high-claim regions | Improve loss ratio by 8–12% |
| 3 | **Claims SLA Dashboard** — auto-alert when claim exceeds X days without resolution | Reduce avg processing time by 30% |

---

## 📁 Project Structure

```
📦 AegisLife-Capstone/
├── 📂 SQL/
│   └── Insurance_ddl_script.sql       ← DDL: Table creation with FK constraints
├── 📂 Data/
│   ├── agentinfo.csv
│   ├── claimhistory.csv
│   ├── customerfeedback.csv
│   ├── customermaster.csv
│   └── policydetails.csv
├── 📂 Notebooks/
│   └── Capstone.ipynb                 ← Full EDA + Statistical Analysis
├── 📂 PowerBI/
│   └── Capstone_dashboard.pbix        ← Executive + Regional dashboards
├── 📂 Excel/
│   └── Data_Quality_Log.xlsx          ← Validation & cleaning log
└── README.md
```

---

## 🚀 How to Run

### Prerequisites

```bash
pip install pandas pymysql sqlalchemy scipy matplotlib seaborn jupyter
```

### Step 1 — Set Up MySQL Database

```sql
-- Run the DDL script
SOURCE Insurance_ddl_script.sql;

-- Load CSV data into tables (via MySQL Workbench or LOAD DATA INFILE)
```

### Step 2 — Connect Python to SQL

```python
from sqlalchemy import create_engine
import pandas as pd

engine = create_engine("mysql+pymysql://root:<password>@localhost:3306/Capstone")

df_agent    = pd.read_sql_query("SELECT * FROM agentinfo", engine)
df_claims   = pd.read_sql_query("SELECT * FROM claimhistory", engine)
df_feedback = pd.read_sql_query("SELECT * FROM customerfeedback", engine)
df_customer = pd.read_sql_query("SELECT * FROM customermaster", engine)
df_policy   = pd.read_sql_query("SELECT * FROM policydetails", engine)
```

### Step 3 — Run the Notebook

```bash
jupyter notebook Capstone.ipynb
```

### Step 4 — Open Power BI Dashboard

```
1. Open Capstone_dashboard.pbix in Power BI Desktop
2. Update data source credentials (MySQL host/credentials)
3. Refresh dataset
4. Explore Executive & Regional Manager views
```

---



<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100:0f3460&height=100&section=footer&animation=fadeIn"/>

*Built with 🔍 SQL · 🐍 Python · 📊 Power BI · 📐 Statistics*

</div>
