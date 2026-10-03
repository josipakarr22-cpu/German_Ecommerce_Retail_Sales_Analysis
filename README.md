# E-Commerce Retail Sales Analysis — Project 2

## Project Overview

This project analyzes retail/e-commerce sales performance for a German market dataset covering **2023–2025**.

The goal was to build a complete business-analysis workflow focused on:

- data quality and cleaning
- Excel-based analysis and KPI preparation
- PivotTables and interactive filters
- Tableau dashboard design
- sales, profit and margin analysis
- business insights and communication of results

The project is designed as a **Junior Data Analyst portfolio project** and demonstrates practical Excel + Tableau skills.

---

## Business Objective

The main objective was to understand:

1. How sales and profit changed over time.
2. Which German regions generated the most sales.
3. How different customer segments performed.
4. Which product categories generated the most sales and profit.
5. Which categories had the strongest profit margins.
6. How the data could be transformed into an interactive management dashboard.

---

## Dataset

The dataset contains retail transaction/order-level information for Germany.

### Main fields

| Field | Description |
|---|---|
| Order ID | Unique order identifier |
| Order Date | Date the order was placed |
| Ship Date | Shipping date |
| Customer ID | Customer identifier |
| Customer Name | Customer name |
| Segment | Consumer, Corporate, Home Office |
| Country | Country |
| Region | German region |
| City | Customer/order city |
| Category | Product category |
| Sub-Category | Product sub-category |
| Product Name | Product name |
| Quantity | Quantity sold |
| Sales | Revenue |
| Discount | Discount applied |
| Profit | Profit |
| Shipping Cost | Shipping cost |
| Payment Mode | Payment method |

The original dataset contained **18,012 rows** and **18 columns**.

---

# 1. Data Cleaning

The dataset was inspected before analysis and several data-quality issues were identified.

### Issues identified

- Missing Customer ID values
- Missing Payment Mode values
- Missing Profit values
- Duplicate records
- Inconsistent whitespace in Region
- Inconsistent Segment spelling
- Inconsistent Category capitalization/spelling
- City naming inconsistency such as `Nürnberg` / `Nuremberg`

### Cleaning actions

Examples of transformations included:

- trimming leading/trailing whitespace
- standardizing region names
- standardizing `Homeoffice` → `Home Office`
- standardizing `Office supplies` → `Office Supplies`
- replacing missing Payment Mode values with `Unknown`
- checking duplicate records
- validating date fields
- checking numeric fields and null values

The cleaned dataset was then used for the dashboard analysis.

---

# 2. Excel Analysis

Excel was used for data preparation, quality checks, exploratory analysis and dashboard development.

### Excel skills demonstrated

- Data cleaning
- Filtering
- Sorting
- Excel Tables
- PivotTables
- PivotCharts
- Slicers
- Timeline
- KPI calculations
- Conditional formatting
- Dashboard layout
- Basic exploratory data analysis

The workbook contains dedicated areas for:

- RAW_DATA
- CLEAN_DATA
- EDA
- Dashboard
- data documentation/business questions

---

# 3. Key KPIs

The final dashboard presents the following KPIs:

| KPI | Value |
|---|---:|
| Total Sales | €15,574,987.80 |
| Total Profit | €1,699,897.07 |
| Total Orders | 18,000 |
| Profit Margin | 10.91% |

### Profit Margin calculation

```text
Profit Margin = Total Profit / Total Sales
```

For the dashboard:

```text
Profit Margin = 1,699,897.07 / 15,574,987.80
             ≈ 10.91%
```

---

# 4. Tableau Dashboard

The final Tableau dashboard is titled:

**E-Commerce Sales & Profit Analysis**

The dashboard was designed as an interactive business dashboard rather than as a collection of isolated charts.

### Main dashboard components

#### KPI section

- Total Sales
- Total Profit
- Total Orders
- Profit Margin %

#### Filters

- Year
- Region
- Segment
- Category

#### Visualizations

- Sales & Profit by Year
- Sales by Region
- Sales by Segment
- Sales & Profit by Category
- Profit Margin by Category

The dashboard allows the user to filter the analysis and observe how the KPIs and charts change.

---

# 5. Business Insights

Based on the final dashboard:

### Sales by region

**Bavaria** generates the highest sales among the analyzed regions.

North Rhine-Westphalia is the next largest region by sales, followed by Baden-Württemberg, Hesse and Saxony.

### Sales by segment

The **Corporate** segment generates the highest sales.

The Consumer segment has a lower sales total than Corporate but shows a higher profit margin.

### Category performance

**Technology** generates the largest sales volume.

However, Technology has the lowest profit margin among the four categories.

**Home & Lifestyle** has the highest profit margin.

This demonstrates an important business-analysis distinction:

> The category with the highest revenue is not necessarily the category with the highest profitability.

### Profitability

Overall profit margin is approximately **10.91%**.

The category-level margin analysis shows meaningful differences in profitability between product categories.

---

# 6. Tools & Technologies

### Excel

Used for:

- cleaning
- quality checks
- PivotTables
- PivotCharts
- slicers
- timeline
- KPI preparation
- dashboard development

### Tableau

Used for:

- interactive dashboard
- calculated fields
- KPI cards
- filters
- sales/profit visualizations
- category and segment analysis
- regional analysis
- dashboard layout and formatting

---

# 7. Tableau Calculated Fields

### Clean Region

```text
TRIM([Region])
```

### Clean Segment

```text
IF LOWER(TRIM([Segment])) = "homeoffice"
THEN "Home Office"
ELSE [Segment]
END
```

### Clean Category

```text
IF LOWER(TRIM([Category])) = "office supplies"
THEN "Office Supplies"
ELSE [Category]
END
```

### Clean Payment Mode

```text
IF ISNULL([Payment Mode])
OR TRIM([Payment Mode]) = ""
THEN "Unknown"
ELSE [Payment Mode]
END
```

### Profit Margin

```text
SUM([Profit]) / SUM([Sales])
```

---

# 8. What This Project Demonstrates

This project demonstrates the ability to:

- inspect a real-world dataset
- identify data-quality problems
- clean and standardize categorical data
- work with missing values
- validate data
- build PivotTable-based analysis
- create KPIs
- calculate profit margin
- build interactive Tableau dashboards
- choose visualizations for business questions
- compare revenue with profitability
- communicate business insights

---

# 9. Limitations

The analysis is descriptive and based on the available dataset.

It does not establish causal relationships between variables.

For example, a lower profit margin in a category does not by itself explain *why* the margin is lower. Additional analysis could investigate:

- discount levels
- product/sub-category performance
- shipping costs
- customer segment
- regional differences
- individual products

---

# 10. Portfolio Value

This project complements Project 1 by emphasizing **Excel + Tableau BI workflow**, while Project 1 demonstrates a broader end-to-end analysis workflow with Python/SQL/Power BI.

Together, the projects demonstrate practical Junior Data Analyst skills across:

**Data Cleaning → EDA → KPI Analysis → SQL/Python → Excel → Tableau → Power BI → Business Insights**

---

## Project Status

**Completed — Portfolio Ready**

Main deliverable:

**Interactive Tableau dashboard: E-Commerce Sales & Profit Analysis**


## GitHub Project Structure

```text
Project_2_Retail-Sales-Customer-Performance-Analysis/
│
├── README.md
├── data/
│   ├── raw/
│   │   └── JOCO_Project_2_Retail_Sales_Dataset.xlsx
│   └── cleaned/
│       └── JOCO_Project_2_Retail_Sales_Dataset.xlsx
├── screenshots/
│   ├── Ecommerce_Sales_Dashboard.PNG
│   └── Ecommerce_Sales_Dashboard.xlsx.PNG
└── tableau/
    └── Project_2_Retail_Sales_Dashboard.twb
```

## Project Status

**Completed — GitHub Ready**

The project includes the cleaned dataset, exploratory analysis, Excel dashboard, Tableau dashboard, documentation, and screenshots required for the portfolio version.
