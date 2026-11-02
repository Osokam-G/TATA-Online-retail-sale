# TATA Online Retail Sales Overview

A Power BI Project analysis of online retail products, orders, net revenue, and quantity sold, with country and month filter

## Table of Contents

1. [Introduction](#1-introduction)
2. [Problem Statement](#2-problem-statement)
3. [Data Sourcing](#3-data-sourcing)
4. [Data Transformation and Cleaning](#4-data-transformation-and-cleaning)
5. [Analytical Measures](#5-analytical-measures)
6. [Dashboard and Visuals](#6-dashboard-and-visuals)
7. [General Insights](#7-general-insights)
8. [Recommendations](#8-recommendation)
9. [Conclusion](#9-conclusion)
10. [Author](#10-author)

## 1. Introduction

This project uses Power BI to explore online retail sales performance. The dashboard summarizes product count, order count, net revenue, and quantity sold, and compares orders and revenue across countries and year-month periods.

The dashboard displays **3,958 products**, **25,900 orders**, **₦9.7 million in net revenue**, and **5,645,019 units sold**.

## 2. Problem Statement

Retail teams need a clear view of sales performance across products, countries, and time periods. This dashboard brings key measures into one place to help users review order volume, revenue, and quantity sold.

The analysis focuses on these questions:

- What are the total products, orders, net revenue, and quantity sold?
- Which countries contribute the most orders and net revenue?
- How do order volume and net revenue vary by year and month?

## 3. Data Sourcing

this dataset was provided by Quantum analytics

- **Dataset name:** `TATA Online retail dataset`

## 4. Data Transformation and Cleaning

I used a three-stage workflow to inspect, clean, and validate the dataset before loading it into Power BI.

1. **Excel — data inspection:** I checked for missing values, duplicate records, data types, outliers, and extra spacing.
2. **Google Colab — data cleaning:** I cleaned the dataset and addressed the data-quality issues identified during inspection.
3. **Power Query — data validation:** I loaded the cleaned dataset into Power Query and checked its validity and quality to confirm that it was suitable for analysis before loading it into Power BI.

### Data Cleaning Summary

| Cleaning Operation | Reason | Records Affected |
|---|---|---:|
| Removed exact duplicate rows | Avoid duplicate inflation in transaction metrics. | 5,268 |
| Filled missing `CustomerID` values with `Guest` | Preserve transaction history when customer information is missing. | 135,037 |
| Filled missing `Description` values with `Unknown Item` | Avoid blank dimension labels in Power BI visuals. | 1,454 |


### view of the cleaned dataset in MS EXCEL

<img width="1920" height="1080" alt="Screenshot (103)" src="https://github.com/user-attachments/assets/a5cfd3b0-b93a-4b3a-a3af-e63d739d17b1" />



## 5. Analytical Measures

 summary measures:

| Measure | value |
|---|---:|
| Total Products | 3,958 |
| Total Orders | 25,900 |
| Total Net Revenue | ₦9.7M |
| Total Quantity Sold | 5,645,019 |

### DAX Measures

```DAX
Total Products =
DISTINCTCOUNT('Cleaned_Data'[StockCode])

Total Orders =
 DISTINCTCOUNT('Cleaned_Data'[InvoiceNo])

Total Net Revenue =
= SUM('Cleaned_Data'[Revenue])

Total Quantity Sold =
 CALCULATE(SUM('Cleaned_Data'[Quantity]), 'Cleaned_Data'[Quantity] > 0)
```

If each row represents an order line, `DISTINCTCOUNT` is typically used to count unique orders. Confirm the dataset structure before using these measures.

## 6. Dashboard and Visuals

The dashboard contains:

- KPI cards for total products, total orders, total net revenue, and total quantity sold.
- A bar chart showing total orders by country.
- A bar chart showing total net revenue by country.
- A line chart showing net revenue by `YEAR_MNTH`.
- A column chart showing total orders by `YEAR_MNTH`.
- Year-month and country slicers for interactive filtering.

<img width="1920" height="1080" alt="Screenshot (102)" src="https://github.com/user-attachments/assets/ecc8d902-f3e0-469f-af2a-8eb1657988e1" />




## 7. General Insights

- The Analysis reports **25,900 orders** across **3,958 products**.
- Total net revenue is **₦9.7 million**, and total quantity sold is **5,645,019 units**.
- The **United Kingdom** has the largest displayed order count and net revenue by a wide margin compared with the other countries shown.
- The net revenue line chart generally declines across the displayed periods, with a more noticeable drop near december 2011
- The orders  varies by displayed year-month period, with order during November 2011 periods showing a visible peak.


## 8. Recommendations

- **Review the United Kingdom’s contribution to sales.** It leads the displayed country charts by both order count and net revenue.
- **Investigate the declining revenue pattern.** 
- **Compare revenue with order volume.** 


## 9. Conclusion

This Power BI project provides an overview of online retail sales through product, order, revenue, and quantity measures. The dashboard highlights the United Kingdom as the largest displayed country by orders and net revenue and shows variation across year-month periods.



## 10. Author

**OSOKAM GIFT**

- [LinkedIn](https://www.linkedin.com/in/osokam-gift-375124291?utm_source=share_via&utm_content=profile&utm_medium=member_android)
- [Portfolio](add-your-link)
- [GitHub](add-your-link)
````
