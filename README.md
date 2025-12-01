# Sales_Analysis_Amazon_Porducts

Below is a **clean, properly formatted README.md** *exactly* as it should appear in GitHub — no emojis, no distractions, fully professional, ATS-friendly, Markdown-standard, and suitable for a portfolio.

You can copy/paste directly into `README.md`.

---

# Amazon Products Sales Analysis – Power BI Dashboard

## Project Overview

This project presents a complete Power BI dashboard analyzing Amazon product sales, category performance, customer reviews, and time-based sales trends.
The goal is to provide insight into sales behavior, identify top-performing categories and products, and support data-driven decisions through interactive reporting.

---

## Dataset Description

### Amazon_Data (Fact Table)

* Order Date
* Product Category
* Product Description
* Price (Dollar)
* YTD Sales
* QTD Sales
* YTD Product Sold
* YTD Reviews
* Number of Reviews
* Shipment

```DAX
Date_Table = CALENDAR(MIN(Amazon_Data[Order Date]), MAX(Amazon_Data[Order Date]))
```

### Date_Table (Dimension Table)

* Date:
```DAX
Date_Table =
CALENDAR(
    MIN(Amazon_Data[Order Date]),
    MAX(Amazon_Data[Order Date]))
```
* Month Name:
```DAX
Month Name =
FORMAT(
    Date_Table[Date], "MMM")
```
* Month Number:
```DAX
Month Number =
MONTH(
    Date_Table[Date])
```
* Quarter:
```DAX
Qtr =
CONCATENATE(
    "Qtr ",
    Date_Table[Quarter Number])
```
* Quarter Number:
```DAX
Quarter Number =
QUARTER(
    Date_Table[Date])
```
* Week:
```DAX
Week =
WEEKNUM(
    Date_Table[Date]) 
```

Relationship:
`Amazon_Data[Order Date] → Date_Table[Date]`

---

## Dashboard Features

### Key Performance Indicators (KPIs)

* Year-to-Date (YTD) Sales
* Quarter-to-Date (QTD) Sales
* YTD Product Sold
* YTD Reviews

### Visuals Included

* Sales by Month (Line Chart)
* Sales by Week (Column Chart)
* Sales by Product Category (Matrix/Table)
* Top 5 Products by YTD Sales
* Top 5 Products by YTD Reviews

### Filters

* Product Category
* Quarter

---

## DAX Measures Used

### YTD Sales
```DAX
YTD Sales =
TOTALYTD(
    SUM(Amazon_Data[Price(Dollar)]),
    Date_Table[Date])
```

### QTD Sales

```DAX
QTD Sales =
TOTALQTD(
    SUM(Amazon_Data[Price(Dollar)]),
    Date_Table[Date])
```

### YTD Product Sold

```DAX
YTD Product Sold =
TOTALYTD(
    COUNT(Amazon_Data[Product Category]),
    Date_Table[Date])
```

### YTD Reviews

```DAX
YTD Reviwes =
TOTALYTD(SUM(
    Amazon_Data[Number of  reviews]),
    Date_Table[Date]) 
```

---

## Insights and Findings

* Men Clothes and Men Shoes generate the highest year-to-date revenue.
* Monthly sales peak in August and November, showing clear seasonal trends.
* SanDisk products rank highest in customer reviews.
* Weekly sales show fluctuation patterns, indicating varying customer buying behavior.
* Some products receive high reviews but generate moderate sales, suggesting opportunities for listing optimization.

---

## Tools and Technologies

* Power BI Desktop
* DAX (Data Analysis Expressions)
* Power Query
* Excel / CSV

---

## How to Use

1. Download the `.pbix` file from this repository.
2. Open it using Power BI Desktop.
3. Explore the dashboard using available filters and interactive visuals.

---

## Purpose of the Project

* Demonstrate Power BI dashboard development skills
* Apply DAX time-intelligence functions
* Showcase data modeling and analytics capabilities
* Provide meaningful business insights using visualization techniques

---

* A GitHub project folder structure
* A PDF project summary
* A polished LinkedIn project description

Just let me know.
