# Sales Analysis

### Project Overview

Need to analyze pizza sales data to gain business insight.

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
```SQL
select sum(total_price) as Total_Revenue
from pizza_sales;
```
![image](https://github.com/user-attachments/assets/2491db4d-b4fd-49cf-ae57-97e40751db32)

**Average Order Value**
```SQL
select sum(total_price)/ count(DISTINCT order_id) as Average_Order_Value
from pizza_sales;
```
![image](https://github.com/user-attachments/assets/20a27fc7-50c0-407e-8b30-db04a631c5a5)

**Total Pizza Sold**
```SQL
select sum(total_price)/ count(DISTINCT order_id) as Average_Order_Value
from pizza_sales;
```
![image](https://github.com/user-attachments/assets/cb631cc9-33bd-4619-8b48-f62a494bb109)

