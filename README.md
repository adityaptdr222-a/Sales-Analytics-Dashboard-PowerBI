# Sales-Analytics-Dashboard-PowerBI
Interactive Power BI dashboard analyzing 5,000+ sales records across 4 regions and 6 product categories with advanced DAX measures and automated reporting
# Sales Analytics Dashboard — Power BI

A sales performance dashboard built in Power BI to analyze sales, profit, and regional performance across multiple product categories.

## About the Project

This project was built to help business teams track sales performance without manually going through spreadsheets. The dashboard gives a clear picture of which regions are performing well, which products have low margins, and how overall sales are trending over time.

The dataset contains 5,000+ sales records across 4 regions and 6 product categories.

## What This Dashboard Does

- Tracks total sales, profit, average order value, and profit margin in real time
- Compares performance across 4 regions and 6 product categories
- Identifies high-profit areas and low-margin risk zones
- Shows month-wise and quarter-wise sales trends
- Allows filtering by region, product, and time period using slicers

## Pages in the Dashboard

1. **Overview** — Key KPIs: Total Sales, Profit, Orders, Profit Margin
2. **Product Analysis** — Product-wise sales and profit comparison
3. **Region Analysis** — Region-wise performance breakdown
4. **Business Insights** — Trends, top performers, and recommendations

## DAX Measures Created

- Total Sales = SUM(Sales[Revenue])
- Total Profit = SUM(Sales[Profit])
- Profit Margin = DIVIDE([Total Profit], [Total Sales])
- Average Sales = AVERAGE(Sales[Revenue])
- Total Orders = COUNTROWS(Sales)
- MoM Growth = Month-over-month sales growth %

## Technologies Used

- Power BI Desktop
- DAX (Data Analysis Expressions)
- Microsoft Excel (data source)

## Key Insights from Analysis

- Identified top-performing region contributing highest revenue
- Found 2 product categories with profit margin below 10% — flagged as risk areas
- Automated reporting reduced manual analysis effort by around 40%
- Built interactive slicers so any team member can filter data without technical knowledge

## How to Open

1. Download the `.pbix` file
2. Open with Power BI Desktop (free download from microsoft.com/powerbi)
3. All visuals and data will load automatically

## Author

Aditya Patidar
Email: adityaptdr222@gmail.com
LinkedIn: https://www.linkedin.com/in/aditya-patidar03/
GitHub: https://github.com/adityaptdr222-a
