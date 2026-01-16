# Telco Customer Churn Analysis

Excel-based telecom churn analysis highlighting high-risk customer segments through KPI tracking, segmentation, and a contract–tenure risk heatmap

## Dashboard Preview

![Dashboard Preview](https://github.com/jacksonkavishe/telco-customer-churn-analysis/blob/main/churn_dashboard.png?raw=true)

## Executive Summary

The analysis reveals a churn rate of **26.54%** across 7,043 customers, with churn heavily concentrated among early-tenure customers on month-to-month contracts (47.44% churn in first year). Month-to-month contracts show **42.71% churn** compared to just **2.83%** for two-year contracts. Pricing also plays a role, with medium and high monthly charge customers exhibiting elevated churn risk (37.51% and 32.88% respectively). These insights highlight clear opportunities for targeted retention strategies focused on contract migration and early-lifecycle engagement.

## Project Overview

This project presents an end-to-end customer churn analysis for a telecommunications company using Microsoft Excel. The objective is to understand customer attrition patterns, identify high-risk segments, and support data-driven retention strategies through a structured analytical approach and an executive-level dashboard.

## Business Objectives

The main objectives of this analysis are to:
- Measure overall customer churn and retention performance  
- Identify key drivers of churn across customer segments  
- Highlight high-risk customer groups for targeted retention actions  

## Dataset used

- <a href="https://github.com/jacksonkavishe/telco-customer-churn-analysis/blob/main/churn_raw_data.csv">Raw Data<a/>




Key fields include:
- Customer ID  
- Contract type (Month-to-month, One year, Two year)
- Tenure (customer lifecycle in years)
- Monthly charges  
- Service features (Tech Support, Online Security, etc.)
- Churn status  

## Data Preparation & Cleaning

The following data preparation steps were performed in Excel:

1. Removed duplicate records using **CustomerID** as the unique identifier  
2. Validated data consistency across key variables  
3. Created a **Churn Flag** to clearly distinguish churned vs retained customers  
4. Ensured numerical fields (Monthly Charges, Tenure) were correctly formatted  

These steps ensured the dataset was analysis-ready and reliable.

## Core Metrics and KPIs

The following key performance indicators were calculated:

- **Total Customers**: 7,043
- **Total Churned Customers**: 1,869
- **Churn Rate**: 26.54%
- **Retention Rate**: 73.46%

These KPIs provide a high-level view of customer attrition and retention performance.

## Exploratory and Segmentation Analysis

Exploratory analysis was conducted to answer key business questions, focusing on variables with the strongest impact on churn.

### Churn by Contract Type

Compared churn behavior across contract types:
- **Month-to-month**: 42.71% churn rate
- **One year**: 11.27% churn rate
- **Two year**: 2.83% churn rate

Contract length emerges as the single strongest predictor of churn risk, with month-to-month customers churning at 15x the rate of two-year contract holders.

### Churn by Customer Tenure

Grouped customers into tenure bands to analyze lifecycle effects:
- **0–1 year**: 47.44% churn rate
- **1–2 years**: 28.71% churn rate
- **2–4 years**: 20.39% churn rate
- **4–6 years**: 9.51% churn rate

Early-tenure customers (first year) show significantly elevated churn risk, nearly 5x higher than long-tenured customers.

### Churn by Monthly Charges (Statistical Segmentation)

Monthly charges were segmented using **quartile-based statistical reasoning** rather than arbitrary thresholds to ensure segments reflect actual distribution patterns in the data.

Customers were classified as:
- **Low**: 17.91% churn rate
- **Medium**: 37.51% churn rate
- **High**: 32.88% churn rate

Using the following Excel formula:

```excel
=IF(T2<=QUARTILE.EXC($T$2:$T$7044,2),
   "Low",
   IF(T2<=QUARTILE.EXC($T$2:$T$7044,3),
      "Medium",
      "High"))
```

This approach ensures that segments are data-driven and representative of natural pricing tiers within the customer base.

### Contract–Tenure Risk Heatmap

A two-dimensional risk heatmap was created to visualize the combined impact of contract type and tenure on churn risk. The heatmap reveals that:
- Month-to-month contracts in the 0–1 year tenure band represent the highest-risk segment
- Risk decreases progressively with both longer contracts and longer tenure
- Two-year contracts show consistently low churn across all tenure groups

This visualization enables prioritization of retention efforts based on risk concentration.

## Dashboard & Visualizations

An executive dashboard was developed in Excel featuring:
- High-level KPI cards (Total Customers, Churned Customers, Churn Rate, Retention Rate)
- Churn Rate by Contract Type (bar chart)
- Churn Rate by Tenure (bar chart)
- Churn Rate by Monthly Charges (bar chart)
- Contract–Tenure Risk Heatmap (conditional formatting)

The dashboard provides an at-a-glance view of churn performance and enables quick identification of priority segments.

## 💡 Business Recommendations

Based on the analysis findings, the following retention strategies are recommended:

1. **Early-Lifecycle Intervention**: Implement proactive retention offers for customers in their first year, particularly those on month-to-month contracts
2. **Contract Migration Incentives**: Introduce targeted campaigns to migrate month-to-month customers to annual or two-year contracts within the first 6–12 months
3. **Pricing Strategy Review**: Evaluate value perception among medium and high-charge customers, as they exhibit elevated churn despite higher revenue contribution
4. **Risk-Based Monitoring**: Prioritize retention resources toward the highest-risk segment (month-to-month, 0–1 year tenure) identified in the heatmap

## ⚠️ Assumptions & Caveats

- Analysis assumes historical churn behavior is indicative of future risk patterns
- Some tenure–contract segments contain small customer counts, which may affect stability of churn rate estimates
- Results are descriptive and observational; causal relationships require controlled experimentation
- External factors (competitor actions, market conditions) are not reflected in this dataset

## Tools & Technologies

- **Microsoft Excel**: Data cleaning, analysis, visualization, and dashboard development
- **Techniques Used**: PivotTables, statistical formulas (QUARTILE.EXC), conditional formatting, data validation, chart design

## Files in Repository

```
├── data/
│   └── telco_customer_churn.xlsx       # Raw dataset
├── analysis/
│   └── churn_analysis_dashboard.xlsx   # Final analysis workbook with dashboard
├── visuals/
│   └── churn_dashboard.png             # Dashboard screenshot
└── README.md                            # Project documentation
```

## How to Use

1. Download the `churn_analysis_dashboard.xlsx` file from the `/analysis` folder
2. Open in Microsoft Excel (2016 or later recommended)
3. Navigate to the "Dashboard" sheet to view the executive summary
4. Explore individual analysis sheets for detailed breakdowns by segment
5. PivotTables and formulas are preserved for further exploration

## Future Improvements

With additional time and resources, this analysis could be extended to include:
- Predictive churn modeling using logistic regression or machine learning
- Service feature impact analysis (Tech Support, Online Security, etc.)
- Customer lifetime value (CLV) calculations to prioritize high-value retention
- Time-series analysis to identify seasonal churn patterns
- Integration with CRM systems for real-time risk scoring

## Author

[Your Name]  
[LinkedIn Profile] | [Email] | [Portfolio Website]

## Acknowledgments

Dataset source: [Add source if applicable, e.g., Kaggle, synthetic data, etc.]

---

*This project demonstrates end-to-end data analysis skills including business problem framing, data preparation, exploratory analysis, statistical segmentation, and executive communication through dashboard design.*
