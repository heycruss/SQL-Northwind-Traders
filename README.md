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

The main relationships are:

                               raw_employees
                                    │
                                    │ employeeID
                                    ▼
raw_customers ── customerID ──► raw_orders ◄── shipperID ── raw_shippers
                                   │
                                   │ orderID
                                   ▼
                           raw_order_details
                                   │
                                   │ productID
                                   ▼
                              raw_products
                                   │
                                   │ categoryID
                                   ▼
                             raw_categories

## 4. Data Validation & Data Quality

## 5. Analysis

### 5.1 Revenue Analysis

### 5.2 Product Performance

### 5.3 Category Performance

### 5.4 Customer Analysis

### 5.5 Employee Performance

### 5.6 Shipping Performance

### 5.7 Best Product per Category

## 6. Key Findings

## 7. Tools & Technologies

## 8. Project Structure

## 9. How to Run

## 10. Conclusions
