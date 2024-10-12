# KPI-Analysis

### Project Overview

Need to analyze key indicators for pizza sales data to gain business insight.

### Data Sources

Sales Data: The primary dataset used for this analysis is the "pizza_sales.csv" file, containing detailed information about each sale made by the company.

### Tools

- Excel - Data Cleaning
- SQL Server - Data Analysis
- PowerBI - Creating reports

### Data Cleaning/Preparation

In the initial data preparation phase, I performed the following tasks:

- Data loading and inspection.
- Handling missing values.
- Data cleaning and formatting.

### KPI's

**Total Revenue**
```sql
select sum(total_price) as Total_Revenue
from pizza_sales;
```
![image](https://github.com/user-attachments/assets/2491db4d-b4fd-49cf-ae57-97e40751db32)

