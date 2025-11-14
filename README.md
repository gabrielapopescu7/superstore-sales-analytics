# Superstore Sales & Profitability Analysis

This project is a complete hands-on data analysis of the **Superstore** dataset from Kaggle, using **Excel** and **Power BI**.  
The goal is to explore sales and profitability across products, regions and discounts, and to build interactive dashboards suitable for a junior Data Analyst portfolio.

---

## 📂 Dataset

- Source: [Superstore Dataset (Kaggle)](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- Records: ~10k rows
- Example fields:
  - `Order Date`, `Ship Date`
  - `Region`, `State`, `City`
  - `Category`, `Sub-Category`, `Product Name`
  - `Sales`, `Profit`, `Quantity`, `Discount`
  - `Segment`, `Ship Mode`

---

## 🛠 Tools & Technologies

- **Excel**
  - Tables
  - Pivot Tables
  - Basic charts
- **Power BI Desktop**
  - Data modeling & data types
  - DAX measures
  - Interactive visuals & slicers
  - Page navigation buttons

---

## 🔹 Step 1 – Data Cleaning & Preparation (Excel)

In Excel, I performed the initial data preparation:

- Imported the CSV file into a structured **Table** (`Ctrl + T`) with headers.
- Verified and corrected data types:
  - `Order Date`, `Ship Date` → Date
  - `Sales`, `Profit`, `Discount`, `Quantity` → Numeric
  - `Region`, `Category`, `Sub-Category`, `Segment`, etc. → Text
- Checked for missing values using filters and:
  - Removed or fixed rows with critical missing values (e.g. missing sales).
- Converted date columns to proper **Date** format (using *Text to Columns* when needed).

I documented these steps in a separate “Data_Cleaning” sheet inside the Excel file.

---

## 🔹 Step 2 – Exploratory Data Analysis (Excel, Pivot Tables)

Using Pivot Tables in Excel, I explored the dataset from multiple angles:

- **Top 10 products by sales**
  - Rows: `Product Name`
  - Values: `Sum of Sales`
  - Sorted by sales and filtered to Top 10
- **Sales by region**
  - Rows: `Region`
  - Values: `Sum of Sales`
  - Identified the most profitable regions
- **Profit by category**
  - Rows: `Category`
  - Values: `Sum of Profit`, `Sum of Sales`
  - Compared profitability vs. volume for each category
- **Sales over time (Year/Month)**
  - Rows: `Order Date` (grouped by Year & Month)
  - Values: `Sum of Sales`
  - Built a line chart to understand trends and seasonality
- **Number of orders per customer**
  - Rows: `Customer Name`
  - Values: `Count of Order ID`
  - Identified the most active customers

These analyses were used as a foundation for the Power BI dashboards.

---

## 🔹 Step 3 – Power BI Overview Dashboard

In **Power BI**, I imported the same Superstore dataset and performed the following:

### Data model & measures

- Adjusted data types (Dates, Text, Decimal Numbers)
- Created DAX measures for KPIs:

```DAX
Total Sales = SUM(Superstore[Sales])

Total Profit = SUM(Superstore[Profit])

Profit Margin = DIVIDE([Total Profit], [Total Sales])

Total Orders = DISTINCTCOUNT(Superstore[Order ID])
