<div align="center">

# 🛒 Retail Intelligence Analytics

**Sales, Profitability & Customer Analytics**

_An end-to-end data analytics portfolio project — from raw transactions to executive-ready insights._

[![Status](https://img.shields.io/badge/status-in%20progress-yellow?style=for-the-badge)]()
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0+-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![License](https://img.shields.io/badge/license-TBD-lightgrey?style=for-the-badge)]()

</div>

---

## 📋 Table of Contents

<table>
<tr>
<td valign="top" width="50%">

- [🎯 Project Overview](#-project-overview)
- [💼 Business Problem](#-business-problem)
- [🚧 Project Status](#-project-status)
- [🗂️ Repository Structure](#️-repository-structure)
- [📊 Dataset](#-dataset)

</td>
<td valign="top" width="50%">

- [📐 KPI Definitions](#-kpi-definitions)
- [🛠️ Tech Stack](#️-tech-stack)
- [🔄 Workflow](#-workflow)
- [🗺️ Roadmap](#️-roadmap)
- [📈 Key Findings](#-key-findings)

</td>
</tr>
<tr>
<td valign="top" width="50%">

- [💡 Recommendations](#-recommendations)
- [⚠️ Limitations](#️-limitations)

</td>
<td valign="top" width="50%">

- [🚀 Getting Started](#-getting-started)
- [📁 Deliverables](#-deliverables)
- [👤 About](#-about)

</td>
</tr>
</table>

---

## 🎯 Project Overview

This project demonstrates a complete **entry-level Data Analyst / BI Analyst workflow** — from data audit and cleaning through SQL analysis, Python exploration, Power BI dashboarding, and executive reporting.

The emphasis is on **trustworthy analysis** and **clear business communication** rather than unnecessary technical complexity.

> **Scope note:** The data is the _Sample Superstore_ dataset (US retail transactions). Findings are **not** presented as evidence about the South African market — generalisability is documented explicitly.

---

## 💼 Business Problem

A retail business needs a clearer view of **what drives sales and profit**.

**Management wants to:**

| # | Objective |
|:-:|-----------|
| 🔍 | Identify strong and weak **product categories, regions, and customer segments** |
| 💸 | Investigate whether **discount levels are associated** with weaker profitability |
| 🎯 | Decide where **further investigation or operational action** is justified |

The analysis describes **patterns** in the data. It does **not** claim causation unless the evidence and method support a causal conclusion.

---

## 🚧 Project Status

| Component | Status | Notes |
|:----------|:------:|:------|
| 📝 Project plan | ✅ Complete | `PROJECT_PLAN.md` |
| 🔍 Data audit | 🟡 In progress | Data dictionary & quality log |
| 🧹 Data cleaning | 🟡 In progress | Reproducible `clean_data.py` |
| 🗄️ SQL analysis | 🟡 In progress | 10–12 documented queries |
| 🐍 Python EDA & RFM | ⏳ Pending | Notebook + charts |
| 📊 Power BI dashboard | ⏳ Pending | Executive + Profitability pages |
| 📄 Executive report | ⏳ Pending | Summary + recommendations |
| 🚀 Publication | ⏳ Pending | README, reproduction steps |

**Legend:** ✅ Complete · 🟡 In Progress · ⏳ Planned

---

## 🗂️ Repository Structure

```text
retail-intelligence/
│
├── 📁 data/
│   └── README.md              # Source, licence, grain, load instructions
│
├── 📁 notebooks/
│   └── retail_analysis.ipynb  # EDA, charts, RFM segmentation
│
├── 📁 src/
│   └── clean_data.py          # Reproducible cleaning script
│
├── 📁 sql/
│   └── business_analysis.sql  # 10–12 documented queries
│
├── 📁 powerbi/
│   ├── Retail_Intelligence.pbix
│   └── dashboard_preview.png
│
├── 📁 reports/
│   ├── data_audit.md
│   └── executive_summary.md
│
├── 📄 requirements.txt
├── 📄 README.md
└── 📄 PROJECT_PLAN.md
```

---

## 📊 Dataset

| Attribute | Detail |
|:----------|:-------|
| **Name** | Sample Superstore |
| **Context** | US retail transactions |
| **Grain** | ⚠️ Order **line** (not one row per order) |
| **Key fields** | Row ID, Order ID, Order Date, Customer, Segment, Region, Product, Category, Sub-Category, Sales, Quantity, Discount, Profit |
| **Source / Licence** | Documented in `data/README.md` |

> 

**Identifier assumptions** (verified in the data audit):

| Identifier | Represents |
|:-----------|:-----------|
| `Row ID` | Individual records |
| `Order ID` | Orders |
| `Customer ID` | Customers |
| `Product ID` | Products |

---

## 📐 KPI Definitions

All measures are clearly labelled. **Order-line counts are never described as order counts.**

| KPI | Definition |
|:----|:-----------|
| 💰 **Total Sales** | `SUM(Sales)` |
| 📈 **Total Profit** | `SUM(Profit)` |
| 📉 **Profit Margin** | `Total Profit ÷ Total Sales` (guarded when sales = 0) |
| 🧾 **Total Orders** | `COUNT(DISTINCT Order ID)` |
| 👥 **Total Customers** | `COUNT(DISTINCT Customer ID)` |
| 🛍️ **Average Order Value** | `Total Sales ÷ Total Orders` |
| ⚠️ **Loss-Making Order-Line Rate** | Lines with `Profit < 0` ÷ all valid lines |
| 🔁 **Repeat Customer Rate** | Customers with >1 distinct order ÷ customers with ≥1 order |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|:----:|:--------|
| 🐍 **Python** (pandas, NumPy, Matplotlib) | Cleaning, EDA, charts, RFM |
| 🗄️ **MySQL** | Business-question SQL analysis |
| 📊 **Power BI** | Interactive dashboard & DAX |
| 📗 **Excel** | Initial inspection & reconciliation |
| 🐙 **GitHub** | Version control & documentation |

---

## 🔄 Workflow

```mermaid
graph LR
    A[📥 Raw Data] --> B[🔍 Audit]
    B --> C[🧹 Clean]
    C --> D[🗄️ SQL Analysis]
    D --> E[🐍 Python EDA + RFM]
    E --> F[📊 Power BI]
    F --> G[📄 Executive Report]
    G --> H[🐙 Publish]
```

---

## 🗺️ Roadmap

| Status | Milestone |
|:------:|:----------|
| ✅ | Project plan & scope |
| ⬜ | Data audit & data dictionary |
| ⬜ | Reproducible cleaning script |
| ⬜ | MySQL database loaded & reconciled |
| ⬜ | 12 SQL business queries |
| ⬜ | Python EDA notebook with 4–5 charts |
| ⬜ | RFM customer segmentation |
| ⬜ | Power BI Executive Overview page |
| ⬜ | Power BI Profitability Drivers page |
| ⬜ | Power BI Customer Insights page _(optional)_ |
| ⬜ | Executive summary with recommendations |
| ⬜ | Reproduction steps verified |
| ⬜ | Dashboard screenshots added |

---

## 📈 Key Findings

> 🔬 *Findings will be populated from **actual data** once analysis is complete. No values are pre-written or invented.*

| # | Finding | Evidence | Status |
|:-:|:--------|:---------|:------:|
| 1 | _Pending_ | — | ⏳ |
| 2 | _Pending_ | — | ⏳ |
| 3 | _Pending_ | — | ⏳ |
| 4 | _Pending_ | — | ⏳ |
| 5 | _Pending_ | — | ⏳ |

---

## 💡 Recommendations

> Each recommendation will state: **evidence → action → KPI to monitor → limitation**.

| # | Recommendation | KPI | Status |
|:-:|:---------------|:----|:------:|
| 1 | _Pending analysis_ | — | ⏳ |
| 2 | _Pending analysis_ | — | ⏳ |
| 3 | _Pending analysis_ | — | ⏳ |

---

## ⚠️ Limitations

| Area | Consideration |
|:-----|:--------------|
| 📏 **Grain discipline** | Order lines ≠ orders ≠ customers |
| 🔗 **Association, not causation** | Discount–profit patterns are described as associations unless a causal method is justified |
| 🌍 **Generalisability** | US retail data may not represent other markets (e.g., South Africa) |
| 🧩 **Thresholds** | "High sales" and "material margin" thresholds are documented and justified, not arbitrary |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- MySQL 8.0+
- Power BI Desktop

### Quick Start

**1 · Clone the repository**

```bash
git clone https://github.com/<your-username>/retail-intelligence.git
cd retail-intelligence
```

**2 · Set up the environment**

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

**3 · Clean the data**

```bash
python src/clean_data.py \
  --input data/Sample_Superstore.csv \
  --output data/clean_superstore.csv
```

**4 · Load into MySQL** (see `data/README.md` for DDL), then:

```sql
SOURCE sql/business_analysis.sql;
```

**5 · Explore in Python**

```bash
jupyter notebook notebooks/retail_analysis.ipynb
```

**6 · Open the dashboard**

```text
powerbi/Retail_Intelligence.pbix → Refresh
```

---

## 📁 Deliverables

| # | Deliverable | File |
|:-:|:------------|:-----|
| 1 | 📝 Project plan | `PROJECT_PLAN.md` |
| 2 | 🔍 Data audit & dictionary | `reports/data_audit.md` |
| 3 | 🧹 Cleaning script | `src/clean_data.py` |
| 4 | 🐍 Analysis notebook | `notebooks/retail_analysis.ipynb` |
| 5 | 🗄️ SQL queries | `sql/business_analysis.sql` |
| 6 | 📊 Power BI dashboard | `powerbi/Retail_Intelligence.pbix` |
| 7 | 📄 Executive summary | `reports/executive_summary.md` |
| 8 | 🐙 Repository & docs | This file |

---

## 👤 About

**Data Analyst / BI Analyst Portfolio Project**

Built to demonstrate practical, trustworthy analytics: from raw transactions → reproducible cleaning → SQL → Python → Power BI → executive communication.

📫 _[LinkedIn](https://linkedin.com/in/keotshepile-keikabile-94b753324) · [GitHub](https://github.com/Keotshepile2) · [Email](keotshepilekeikabile2@gmail.com)

---

<div align="center">


</div>
