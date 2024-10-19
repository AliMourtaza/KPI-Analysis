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
SELECT SUM(total_price) As Total_revenue
FROM pizza_sales;
```
![image](https://github.com/user-attachments/assets/0299fb25-b0f5-4045-a616-3029f096ba5f)

**Average Order Value**
```SQL
SELECT SUM(total_price)/ COUNT(DISTINCT order_id) As Average_order_value
FROM pizza_sales;
```
![image](https://github.com/user-attachments/assets/5fb38c11-6ec4-4b33-9c2a-f3d4499225de)

**Total Pizza Sold**
```SQL
SELECT SUM(quantity) As Total_pizza_sold
FROM pizza_sales;
```
![image](https://github.com/user-attachments/assets/17f0de25-95e2-4abe-ac45-6f6ac61f645a)

**Total Orders**
```SQL
SELECT SUM(DISTINCT order_id) As Total_orders
FROM pizza_sales;
```
![image](https://github.com/user-attachments/assets/d967200f-7879-4c44-954a-af45b7f4baf4)


**Average Pizzas Per Order**
```SQL
SELECT CAST(
           CAST(SUM(quantity) AS DECIMAL(10, 2)) /
           CAST(COUNT(DISTINCT order_id) AS DECIMAL(10, 2)) 
           AS DECIMAL(10, 2)
       ) AS Average_pizzas_per_order
FROM pizza_sales;
```
![image](https://github.com/user-attachments/assets/c5c8dd51-1e79-458f-ab83-70a236304862)

### Data Analysis
**Daily Trend for Total Orders**
```SQL
SELECT 
    DATENAME(DW, order_date) AS Order_day, 
    COUNT(DISTINCT order_id) AS Total_orders
FROM 
    pizza_sales
GROUP BY 
    DATENAME (DW, order_date);
```
![image](https://github.com/user-attachments/assets/979cc446-ae15-40f1-be4d-170a29d2fd3d)

**Hourly Trend for Orders**
```SQL
SELECT 
    DATEPART(HOUR, order_time) AS Order_Hours, 
    COUNT(DISTINCT order_id) AS Total_Orders
FROM 
    pizza_sales
GROUP BY 
    DATEPART(HOUR, order_time)
ORDER BY
    DATEPART(HOUR, order_time);
```
![image](https://github.com/user-attachments/assets/0c4be8a8-53f5-434b-8cee-f9458c109148)

**% of Sales by Pizza Category**
```SQL
SELECT 
    pizza_category, 
    CAST(SUM(total_price) AS DECIMAL(10, 2)) AS total_revenue, 
    CAST(
        SUM(total_price) * 100.0 / (SELECT SUM(total_price) FROM pizza_sales) 
        AS DECIMAL(10, 2)
    ) AS percentage_of_total_sales
FROM 
    pizza_sales
GROUP BY 
    pizza_category;
```
![image](https://github.com/user-attachments/assets/a47408c9-bd30-4de1-8b35-e80955eb7658)

**% of Sales by Pizza Size**
```SQL
SELECT 
    pizza_size, 
    CAST(SUM(total_price) AS DECIMAL(10, 2)) AS total_revenue, 
    CAST(
        SUM(total_price) * 100.0 / (SELECT SUM(total_price) FROM pizza_sales) 
        AS DECIMAL(10, 2)
    ) AS percentage_of_sales
FROM 
    pizza_sales
GROUP BY 
   pizza_size
ORDER BY
   pizza_size;
```
![image](https://github.com/user-attachments/assets/2c200ec8-9778-4c1a-9a13-8f8a7c900032)


