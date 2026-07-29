# 📊 Sales Data Analysis Project — SQL, Excel & Power BI

A complete end-to-end sales analytics project simulating a two-year retail sales
dataset (5,000 transactions). This project demonstrates the full analyst workflow:
**data generation → SQL querying → Excel reporting → Power BI dashboarding →
business insight generation.**

---

## 📌 Project Overview

The goal of this project is to analyze retail sales performance across products,
categories, regions, and customers, and to surface actionable KPIs for business
stakeholders. It covers:

- A realistic, synthetic sales dataset (2024–2025) with seasonality, discounting, and
  category-based margin profiles
- SQL scripts for schema design and analytical querying
- An Excel workbook with a formula-driven KPI summary and embedded charts
- A documented Power BI dashboard design with DAX measures, page layouts, and filters
- Key business insights derived from the data

---

## 🗂️ Repository Structure

```
sales-data-analysis/
│
├── data/
│   └── sales_data.csv                 # 5,000-row raw dataset
│
├── excel/
│   └── Sales_Data_Analysis.xlsx       # Formatted data + KPI dashboard sheet
│
├── sql/
│   ├── 01_create_and_load.sql         # Table schema + load instructions
│   └── 02_analysis_queries.sql        # 15 analysis queries (KPIs, trends, rankings)
│
├── powerbi/
│   └── PowerBI_Dashboard_Guide.md     # Data model, DAX measures, page layouts
│
├── screenshots/
│   ├── executive_overview.png         # (add after building the .pbix)
│   ├── product_category_performance.png
│   ├── regional_customer_insights.png
│   └── discount_order_trends.png
│
└── README.md
```

---

## 🧾 Dataset Schema

| Column | Type | Description |
|---|---|---|
| Order ID | Text | Unique order identifier (`ORD-100001`) |
| Order Date | Date | Transaction date (Jan 2024 – Dec 2025) |
| Customer Name | Text | Synthetic customer name |
| Product | Text | Product sold (38 SKUs across 5 categories) |
| Category | Text | Electronics, Furniture, Clothing, Office Supplies, Food & Beverage |
| Region | Text | North, South, East, West, Central |
| State | Text | U.S. state within each region |
| Sales | Decimal | Net revenue after discount |
| Quantity | Integer | Units sold per order |
| Discount | Decimal | Discount rate applied (0–25%) |
| Cost | Decimal | Cost of goods sold |
| Profit | Decimal | Sales − Cost |

The dataset was generated programmatically with realistic seasonality (Nov–Dec
demand spike), category-specific margin profiles, and weighted regional/discount
distributions rather than uniform random values, so patterns are meaningful to
analyze.

---

## 🛠️ Skills & Tools Used

- **SQL** — schema design, indexing, window functions (`RANK`, `SUM() OVER`),
  `PERCENTILE_CONT`, CTEs, aggregate/GROUP BY analysis
- **Excel** — `SUMIFS`, `AVERAGE`, `COUNTA`, PivotTable-style summary tables, formatted
  tables, embedded bar/pie charts
- **Power BI** — data modeling, DAX (time intelligence, ranking, % of total), slicers,
  drill-through pages, bookmarks, conditional formatting
- **Python (pandas/openpyxl)** — synthetic data generation and workbook automation
- **Data Analysis & Storytelling** — KPI definition, trend analysis, segmentation,
  business insight generation

---

## 📈 Key KPIs Tracked

- Total Sales, Total Profit, Total Cost
- Profit Margin %
- Total Orders & Total Units Sold
- Average Order Value (AOV)
- Average Discount %
- Sales YoY % / MTD / YTD (Power BI time intelligence)
- Top/Bottom performing products, categories, regions, and customers

---

## 🔍 Sample Business Insights

- Seasonal demand peaks in **November–December**, suggesting inventory and staffing
  should ramp ahead of Q4.
- **Electronics and Furniture** categories generate the highest revenue, but margin
  varies meaningfully across products — some high-revenue SKUs carry below-average
  margins and are candidates for pricing review.
- Orders with **higher discount bands (20–25%)** show a measurably lower profit
  margin, reinforcing the need for disciplined discount governance.
- A relatively small share of **repeat customers** contributes a disproportionate
  share of lifetime sales, highlighting the value of retention efforts.
- **South and West regions** lead in total sales volume, while margin performance
  differs by region — useful for territory-level strategy.

*(Exact figures will vary slightly on regeneration since the dataset uses randomized
generation with fixed seasonal/margin weighting — rerun the SQL queries or open the
Excel dashboard for current numbers.)*

---

## 🚀 How to Use This Project

1. **Load the data:**
   ```bash
   psql -d your_database -f sql/01_create_and_load.sql
   ```
   Then load `data/sales_data.csv` using `\copy` (see comments in the script for
   MySQL/SQL Server equivalents).

2. **Run the analysis queries:**
   ```bash
   psql -d your_database -f sql/02_analysis_queries.sql
   ```

3. **Explore the Excel workbook:**
   Open `excel/Sales_Data_Analysis.xlsx` — see the `Sales_Data` sheet for raw data and
   `Dashboard_Summary` for KPI cards, category/region breakdown tables, and charts.

4. **Build the Power BI dashboard:**
   Import `data/sales_data.csv` into Power BI Desktop, follow
   `powerbi/PowerBI_Dashboard_Guide.md` for the data model, DAX measures, and
   page-by-page layout, then export dashboard screenshots into `/screenshots`.

---

## 🖼️ Screenshots

> Add exported Power BI dashboard screenshots here once the `.pbix` file is built.

| Executive Overview | Product & Category Performance |
|---|---|
| `screenshots/executive_overview.png` | `screenshots/product_category_performance.png` |

| Regional & Customer Insights | Discounts & Order Trends |
|---|---|
| `screenshots/regional_customer_insights.png` | `screenshots/discount_order_trends.png` |

---

## 📄 License

This project uses a synthetically generated dataset for portfolio/demo purposes and
is free to use, modify, and extend.
