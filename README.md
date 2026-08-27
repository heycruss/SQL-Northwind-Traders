# Northwind SQL Business Analysis

## 1. Project Overview

This project uses SQL to analyze the Northwind database from a business perspective.

The analysis explores sales performance, product and category performance, customer behavior, employee performance, and shipping operations.

## 2. Business Questions

This analysis aims to answer the following business questions:

1. How is revenue evolving over time?

2. Which products generate the most revenue, and how concentrated is revenue among the top products?

3. Which products drive revenue across different time periods?

4. Which categories generate the most revenue, and how does their performance evolve over time?

5. Which customers generate the most revenue, and which customers show the highest level of repeat purchasing?

6. Which employees generate the most revenue and sales volume?

7. How does shipping performance differ between shipping companies?

8. Which product generates the most revenue within each category?

## 3. Dataset


### Source

The analysis is based on the Northwind database.

[Northwind dataset](https://mavenanalytics.io/data-playground/northwind-traders?utm_source=chatgpt.com)

### Database Structure

The analysis uses the following tables:

- `raw_customers` — Customer information
- `raw_orders` — Order information
- `raw_order_details` — Products, quantities and prices for each order
- `raw_products` — Product information
- `raw_categories` — Product categories
- `raw_employees` — Employee information
- `raw_shippers` — Shipping company information

### Table Relationships

## Main Table Relationships

The dataset is structured around orders, which connect customers, employees, and shippers. Order details link each order to the products purchased, while products are grouped into categories.

- `raw_employees` → `raw_orders`: `employeeID`
- `raw_customers` → `raw_orders`: `customerID`
- `raw_shippers` → `raw_orders`: `shipperID`
- `raw_orders` → `raw_order_details`: `orderID`
- `raw_products` → `raw_order_details`: `productID`
- `raw_categories` → `raw_products`: `categoryID`



## 4. Data Validation & Data Quality

Before performing the analysis, the dataset was validated to ensure data consistency, completeness, and referential integrity.

The validation process included:

- **Table and record counts** — verifying that all expected tables contain data and checking the number of records in each table.
- **Duplicate records** — identifying potential duplicate records in tables where unique identifiers are expected.
- **NULL values** — checking for missing values in key fields and identifying columns that may affect the analysis.
- **Referential integrity** — verifying that foreign key relationships between tables are consistent and that there are no orphan records.
- **Data consistency** — checking that values follow the expected format and logical constraints of the dataset.

These checks help ensure that the subsequent analysis is based on reliable and consistent data.

### Unique Identifier in `raw_order_details`

During the validation process, it was identified that `raw_order_details` does not contain a single column that uniquely identifies each record.

`orderID` is not unique because a single order can contain multiple products, while `productID` is not unique because the same product can appear in multiple orders.

To uniquely identify each order detail record, the combination of:

`orderID + productID`

## 5. Analysis

### 5.1 Revenue Analysis

![SQL-Northwind-Traders](Images/1.Revenue_over_time.png)

- Revenue shows a strong overall upward trend over the analyzed period, despite significant month-to-month fluctuations.
- Monthly revenue is highly volatile, with several periods showing substantial increases and decreases.
- In 2014, particularly high revenue was observed in January, October, and December, with December showing a strong 68.75% increase compared with the previous month.
- Revenue continued to grow strongly at the beginning of 2015, reaching a peak of 134.6K in April.

### 5.2 Product Performance

![SQL-Northwind-Traders](Images/2.1.Products_and_revenue.png)


- With 57 products in the dataset, an equal distribution of revenue would result in approximately **1.75% per product**.
- Revenue is highly concentrated among a small number of products. **Côte de Blaye** is the strongest-performing product, generating **11.07%** of total revenue, followed by **Thüringer Rostbratwurst (6.48%)** and **Raclette Courdavault (5.63%)**.
- The **top 3 products account for 23.18% of total revenue**, showing a significant concentration of revenue among the best-performing products.
- After the top three products, revenue becomes considerably more distributed, with most products contributing between approximately **0.1% and 4%** of total revenue.

![SQL-Northwind-Traders](Images/3.1.Best_product_every_month.png)


- The leading product varies considerably across months, indicating that revenue performance is not consistently driven by a single product.
- Several products repeatedly appear as monthly revenue leaders, particularly **Côte de Blaye**, **Raclette Courdavault**, and **Thüringer Rostbratwurst**.
- **Côte de Blaye** appears particularly frequently as the top-performing product around the end and beginning of the year. Its repeated strong performance during these periods may indicate a **potential seasonal pattern** that would require further analysis to confirm.
- The revenue share of the monthly top-performing product also varies significantly, ranging from approximately **7.8% to 33.9%**, showing that the degree of revenue concentration changes considerably between months.

### 5.3 Category Performance

![SQL-Northwind-Traders](Images/4.1.Revenue_by_category.png)

![SQL-Northwind-Traders](Images/4.2.Revenue_growth_by_category.png)

### 5.4 Customer Analysis

![SQL-Northwind-Traders](Images/5.1.Revenue_by_customers.png)

![SQL-Northwind-Traders](Images/5.1.Customers_loyalty.png)


### 5.5 Employee Performance

![SQL-Northwind-Traders](Images/6.Employee_analysis.png)

### 5.6 Shipping Performance

![SQL-Northwind-Traders](Images/7.Shipper_analysis.png)

### 5.7 Best Product per Category

![SQL-Northwind-Traders](Images/8.Best_product_of_each_category.png)

## 6. Key Findings

## 7. Tools & Technologies

## 8. Project Structure

## 9. How to Run

## 10. Conclusions
