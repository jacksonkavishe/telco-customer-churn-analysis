# telco-customer-churn-analysis
Excel-based telecom churn analysis highlighting high-risk customer segments through KPI tracking, segmentation, and a contract–tenure risk heatmap

## Project Overview
This project presents an end-to-end customer churn analysis for a telecommunications company using Microsoft Excel. The objective is to understand customer attrition patterns, identify high-risk segments, and support data-driven retention strategies through a structured analytical approach and an executive-level dashboard.

## Business Objectives
The main objectives of this analysis are to:
- Measure overall customer churn and retention performance  
- Identify key drivers of churn across customer segments  
- Highlight high-risk customer groups for targeted retention actions  

## Dataset
The analysis is based on a customer-level telecom dataset containing demographic, service usage, contract, tenure, and billing information.

Key fields include:
- Customer ID  
- Contract type  
- Tenure  
- Monthly charges  
- Service features (i.e., Tech Support, Online Security)  
- Churn status  

## Data Preparation & Cleaning
The following data preparation steps were performed in Excel:

1. Removed duplicate records using **CustomerID** as the unique identifier  
2. Validated data consistency across key variables  
3. Created a **Churn Flag** to clearly distinguish churned vs retained customers  
4. Ensured numerical fields (i.e., Monthly Charges, Tenure) were correctly formatted  

These steps ensured the dataset was analysis-ready and reliable.

## Core Metrics and KPIs
The following key performance indicators were calculated:

- **Total Customers**
- **Total Churned Customers**
- **Churn Rate**
- **Retention Rate**

These KPIs provide a high-level view of customer attrition and retention performance.

## Exploratory and Segmentation Analysis
Exploratory analysis was conducted to answer key business questions, focusing on variables with the strongest impact on churn.

### Churn by Contract Type
- Compared churn behavior across Month-to-Month, One-Year, and Two-Year contracts  
- Identified contract length as a major driver of churn risk  

### Churn by Customer Tenure
- Grouped customers into tenure bands to analyze lifecycle effects  
- Observed significantly higher churn among early-tenure customers  

### Churn by Monthly Charges (Statistical Segmentation)
Monthly charges were segmented using **quartile-based statistical reasoning** rather than arbitrary thresholds.

Customers were classified as:
- **Low**
- **Medium**
- **High**

Using the following Excel formula:

```excel
=IF(T2<=QUARTILE.EXC($T$2:$T$7044,2),
   "Low",
   IF(T2<=QUARTILE.EXC($T$2:$T$7044,3),
      "Medium",
      "High"))
```
  
