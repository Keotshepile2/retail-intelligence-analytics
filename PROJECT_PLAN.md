
<div align="center">

# Retail Intelligence: Sales, Profitability & Customer Analytics

**Project Type:** Data Analytics & Business Intelligence 

_An end-to-end data analytics portfolio project — from raw transactions to executive-ready insights._

[![Status](https://img.shields.io/badge/status-in%20progress-yellow?style=for-the-badge)]()
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0+-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)

</div>

---

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Business Problem](#2-business-problem)
3. [Project Objectives](#3-project-objectives)
4. [Dataset and Scope](#4-dataset-and-scope)
5. [Key Business Questions](#5-key-business-questions)
6. [Key Performance Indicators](#6-key-performance-indicators)
7. [Tools and Technologies](#7-tools-and-technologies)
8. [Implementation Plan](#8-implementation-plan)
9. [SQL Analysis Requirements](#9-sql-analysis-requirements)
10. [Python Analysis Requirements](#10-python-analysis-requirements)
11. [Power BI Dashboard Specification](#11-power-bi-dashboard-specification)
12. [Findings and Recommendations](#12-findings-and-recommendations)
13. [GitHub Repository Structure](#13-github-repository-structure)
14. [Quality Assurance](#14-quality-assurance)
15. [Risks and Limitations](#15-risks-and-limitations)
16. [Final Deliverables](#16-final-deliverables)

---

## 1. Executive Summary

This project analyses retail transaction data to investigate sales performance, profitability, discount patterns, regional and product performance, and customer purchasing behaviour.

The project produces a reproducible data analysis workflow, documented SQL queries, a Python analysis notebook, an interactive Power BI dashboard, and an executive summary containing evidence-based findings and business recommendations.

The primary objective is to demonstrate practical data analytics and business intelligence skills through a complete project that combines technical analysis with clear business communication.

---

## 2. Business Problem

Retail businesses need to understand where sales and profit are generated, which products and regions may require attention, and how discount patterns relate to profitability.

This project investigates retail transaction data to identify performance trends, evaluate product and regional profitability, explore customer purchasing behaviour, and highlight opportunities for further business investigation.

The analysis focuses on measurable evidence. Observed relationships are described as associations rather than causal effects unless the analytical method supports a causal conclusion.

---

## 3. Project Objectives

The project aims to:

1. Inspect, clean, and validate the transaction dataset.
2. Use MySQL to answer business questions through aggregations, joins, conditional logic, common table expressions (CTEs), and window functions.
3. Use Python, pandas, NumPy, and Matplotlib for data preparation, exploratory analysis, and visualisation.
4. Develop an interactive Power BI dashboard with clearly defined KPIs and appropriate data modelling.
5. Identify meaningful business findings and translate them into practical recommendations.
6. Document the methodology, assumptions, limitations, and workflow.
7. Publish the project professionally on GitHub to demonstrate job-relevant analytical skills.

---

## 4. Dataset and Scope

The dataset contains fields relating to orders, shipping dates, customers, customer segments, geography, products, categories, sales, quantity, discounts, and profit.

The initial data audit establishes the dataset's source, licence, dimensions, date range, data types, and quality issues.

The expected record grain is an individual order line, but this is verified before analysis. Order-line counts, distinct orders, and distinct customers are treated as separate measures.

If the dataset is confirmed to be the commonly used Sample Superstore dataset, its source and geographic context are documented. Findings are not presented as representative of the South African retail market without supporting evidence.

The raw dataset is preserved during analysis. The repository README documents the data source and applicable usage terms.

---

## 5. Key Business Questions

The analysis addresses the following questions:

1. How do sales, profit, and profit margin change over time?
2. Which regions and product categories contribute most to sales and profit?
3. Which products have high sales but weak or negative profit?
4. How do profitability and loss-making order-line rates vary across discount bands?
5. Which customer segments contribute most to sales and profit?
6. What proportion of customers place repeat orders?
7. Which performance patterns warrant further investigation?
8. What practical recommendations can be made from the findings, and which KPIs could measure improvement?

---

## 6. Key Performance Indicators

| KPI | Definition |
|-----|------------|
| Total Sales | Sum of all valid sales values |
| Total Profit | Sum of all valid profit values |
| Profit Margin | Total profit divided by total sales |
| Total Orders | Distinct count of order IDs |
| Total Customers | Distinct count of customer IDs |
| Average Order Value | Total sales divided by distinct orders |
| Loss-Making Order-Line Rate | Valid order lines with negative profit divided by all valid order lines |
| Repeat Customer Rate | Customers with more than one distinct order divided by customers with at least one order |

All measures use consistent definitions across SQL, Python, and Power BI. Missing values and invalid records are handled according to documented rules.

---

## 7. Tools and Technologies

| Tool | Purpose |
|------|---------|
| Excel | Initial data inspection, PivotTables, and validation |
| MySQL Workbench | SQL queries and business analysis |
| Python | Data preparation, validation, exploratory analysis, and visualisation |
| Jupyter Notebook | Documented analysis, charts, and interpretation |
| Power BI | Data modelling, DAX measures, and interactive dashboards |
| GitHub | Version control, project documentation, and portfolio presentation |

---

## 8. Implementation Plan

The project prioritises a complete and validated analysis over unnecessary complexity. Optional features are only developed after the core deliverables are complete.

### Phase 1 — Business Understanding and Data Audit

**Tasks**
- Inspect the dataset structure, column names, data types, and dimensions.
- Confirm the date range and likely record grain.
- Investigate missing values, duplicate records, identifier uniqueness, and unusual numeric values.
- Define the business questions and KPI calculations.
- Record the dataset source and licence where available.

**Deliverables**
- Initial Jupyter notebook
- Data audit summary
- KPI definitions and data-quality notes

### Phase 2 — Data Cleaning and MySQL Setup

**Tasks**
- Develop a repeatable Python data-cleaning workflow.
- Convert dates and numeric columns to appropriate data types.
- Investigate unusual values before changing or removing records.
- Preserve the raw source and document cleaning decisions.
- Load the prepared data into MySQL.
- Reconcile row counts and key totals across the source, cleaned data, and SQL table.

**Deliverables**
- `src/clean_data.py`
- Cleaning and validation notes
- MySQL table ready for analysis

### Phase 3 — SQL Business Analysis

Write and document 8–10 core queries, expanding to 12 if scope permits.

The analysis covers:

- Overall sales, profit, margin, orders, and customers
- Monthly sales and profit trends
- Regional and category performance
- Products with the largest cumulative losses
- Profitability across discount bands
- Product rankings within categories
- Customer sales, profit, and order frequency
- Products with high sales but weak profitability
- Repeat-customer rate
- Region-category combinations with weak profitability

Use aggregations, joins, `CASE` expressions, CTEs, and window functions where appropriate.

**Deliverable:** `sql/business_analysis.sql`

### Phase 4 — Python Exploratory Analysis

**Tasks**
- Analyse monthly sales, profit, and profit-margin trends.
- Compare product and regional profitability.
- Investigate the relationship between discount levels and profit.
- Examine outliers and negative-profit records.
- Produce four or five labelled charts.
- Write a short interpretation for each major chart.
- If scope permits, develop customer recency, frequency, and monetary (RFM) analysis, documenting the analysis date and segmentation method.

**Deliverables**
- `notebooks/retail_analysis.ipynb`
- Charts and preliminary findings

### Phase 5 — Power BI Dashboard

Develop two polished, interactive dashboard pages.

**Page 1: Executive Overview**
- KPI cards for Total Sales, Total Profit, Profit Margin, and Total Orders
- Monthly sales and profit trends
- Profit by category or sub-category
- Profit by region
- Relevant date, region, and category slicers

**Page 2: Profitability Drivers**
- Products with the largest cumulative losses
- Profitability and loss-making order-line rate by discount band
- Product-level sales-versus-profit visual
- Detail table showing sales, profit, margin, and order count
- Relevant category and region filters

**Core DAX measures**
- Total Sales
- Total Profit
- Profit Margin
- Total Orders
- Average Order Value
- Loss-Making Lines

Use a suitable data model with a transaction fact table and relevant dimensions where practical. Format currency and percentages consistently, test the filters, and reconcile Power BI measures against SQL results.

A third Customer Insights page is optional and is only added after the two core pages are complete and validated.

**Deliverables**
- `powerbi/Retail_Intelligence.pbix`
- Dashboard preview screenshots

### Phase 6 — Findings and Business Recommendations

**Tasks**
- Identify three to five findings supported by verified figures.
- Explain why each finding matters to the business.
- Develop practical recommendations based on the evidence.
- Identify KPIs that could be used to monitor each recommendation.
- Document assumptions and analytical limitations.
- Complete a scenario analysis only if a defensible calculation is possible.
- Prepare a one- or two-page executive summary.

Any discount scenario states its baseline and assumptions. If it assumes demand and sales volume remain unchanged, that limitation is explicit. Scenario estimates are not presented as guaranteed financial gains.

**Deliverable:** `reports/executive_summary.pdf`

### Phase 7 — Quality Assurance and Publication

**Tasks**
- Organise the repository and finalise the README.
- Reconcile SQL, Python, and Power BI totals.
- Test dashboard filters and measures.
- Verify the documented setup and reproduction steps.
- Confirm the dataset source and applicable licence.
- Prepare a concise explanation of the project for interviews.

**Deliverables**
- Complete GitHub repository
- Final documentation and dashboard previews
- Interview explanation notes

---

## 9. SQL Analysis Requirements

The SQL analysis answers these questions:

1. What are total sales, total profit, profit margin, distinct orders, and distinct customers?
2. How do sales, profit, and margin change by month?
3. Which regions and product categories contribute most to sales and profit?
4. Which products have the largest cumulative losses?
5. How do profit and loss-making order-line rates vary by discount band?
6. Which products rank highest and lowest in profit within each category?
7. What are the sales, profit, and order counts for each customer?
8. Which products combine substantial sales with weak or negative profit?
9. What is the repeat-customer rate?
10. Which region-category combinations have material sales but weak profitability?

If scope permits, additional queries analyse cumulative profit and customer sales concentration.

Each query has a clear title, comments, and a business purpose.

---

## 10. Python Analysis Requirements

### Data quality and preparation

- Inspect missing values, duplicate records, data types, and date parsing.
- Check identifier uniqueness and unusual numeric values.
- Verify the record grain before removing duplicates.
- Document all cleaning decisions.

### Exploratory analysis

- Analyse monthly sales, profit, and margin.
- Compare profitability by product, category, region, and discount band.
- Investigate negative-profit records and potential outliers.
- Create clear charts with titles, labels, and written interpretations.

### Optional customer segmentation

Where the data supports it, calculate customer recency, frequency, and monetary value using a clearly defined analysis date. Document the segmentation method and avoid unsupported claims about customer lifetime value or acquisition costs.

---

## 11. Power BI Dashboard Specification

The dashboard focuses on business questions and actionable insights rather than visual complexity.

### Executive Overview
- Sales, profit, margin, and order KPIs
- Monthly performance trends
- Category and regional profitability
- Relevant interactive slicers

### Profitability Drivers
- Loss-making products
- Discount-band profitability
- Sales-versus-profit analysis
- Detailed product performance table
- Relevant filters

### Data modelling and validation

Use a star schema where practical, with a transaction fact table and appropriate dimensions. Keep the model proportionate to the dataset.

Validate the core DAX measures against SQL results and confirm that filters do not unexpectedly inflate counts or alter totals.

---

## 12. Findings and Recommendations

The final report presents three to five verified findings from the completed analysis.

Potential areas for investigation include:

- Products with persistent losses
- Discount patterns associated with weaker margins
- Region-category combinations with weak profitability
- Customer groups with substantial sales contributions

Each recommendation includes:

- **Evidence:** The finding that supports the recommendation
- **Action:** A specific, practical next step
- **KPI:** A metric for monitoring performance
- **Limitation:** What the analysis does not establish

Recommendations are based on actual results rather than assumptions made before the analysis.

---

## 13. GitHub Repository Structure

```text
retail-intelligence-analytics/
├── data/
│   └── README.md
├── notebooks/
│   └── retail_analysis.ipynb
├── src/
│   └── clean_data.py
├── sql/
│   └── business_analysis.sql
├── powerbi/
│   ├── Retail_Intelligence.pbix
│   └── dashboard_preview.png
├── reports/
│   └── executive_summary.pdf
├── requirements.txt
├── README.md
└── PROJECT_PLAN.md
```

Files and folders are added as the project progresses.

The README includes the business problem, dataset source and licence, KPI definitions, tools, workflow, verified findings, dashboard screenshots, recommendations, limitations, and reproduction instructions.

---

## 14. Quality Assurance

The project is considered complete when:

- The cleaning workflow runs successfully.
- Unexplained records are not silently discarded.
- SQL, Python, and Power BI totals reconcile.
- Dashboard filters and measures work correctly.
- The executive summary contains three to five verified findings and practical recommendations.
- Assumptions and limitations are documented.
- The repository includes clear setup and reproduction instructions.
- The project can be explained in approximately three minutes, including one analytical challenge and one business recommendation.

---

## 15. Risks and Limitations

| Risk | Mitigation |
|------|------------|
| Scope exceeds available capacity | Prioritise two completed dashboard pages, core SQL analysis, and the executive summary |
| Data-quality errors | Preserve the raw source, document cleaning rules, and reconcile results across tools |
| Incorrect aggregation | Distinguish order lines, distinct orders, and distinct customers |
| Overstated conclusions | Describe relationships as associations unless a suitable causal method is justified |
| Limited generalisability | Document the dataset source, geographic context, period, and limitations |
| Unclear data licence | Verify applicable terms and document how the data can be accessed |

---

## 16. Final Deliverables

1. `PROJECT_PLAN.md`
2. Data audit and KPI definitions
3. Python cleaning script and analysis notebook
4. Documented SQL business analysis
5. Power BI report with at least two completed pages and preview screenshots
6. Executive summary with verified findings and recommendations
7. README and dependency list
8. Concise interview explanation of the project

---

**Project Status:** In Progress. Findings, dashboard outputs, and recommendations will be added after the analysis is completed and validated.
