# Sales-Analytics-Dashboard-PowerBI
Interactive 5-page Power BI dashboard analyzing 600 sales orders across 4 regions and 6 products, with dynamic slicers, drillthrough, and custom DAX measures.

# Sales Analytics Dashboard — Power BI

A sales performance dashboard built in Power BI to analyze sales, profit, and regional performance across multiple products, with interactive filtering and order-level drillthrough.

## About the Project

This project was built to help business teams track sales performance without manually going through spreadsheets. The dashboard gives a clear picture of which regions and products are performing well, lets users filter by region/product using slicers, and allows drilling through from a summary view into order-level detail.

The dataset contains 600 sales orders spanning Jan 2022 – Sep 2024, across 4 regions and 6 products in 3 categories (Electronics, Accessories, Office).

## What This Dashboard Does

- Tracks Total Sales, Total Profit, Total Orders, and Avg Sales per Order in real time
- Lets users filter the entire dashboard by **region** and **product** using slicers (available on the Overview and Business Insights pages)
- Supports **drillthrough**: right-click any region on a chart to jump to an "Order Details" page filtered to that region
- Flags high-value orders (>₹3,000) using a custom measure
- Classifies profit performance into Good / Average / Needs Improvement bands
- Breaks down revenue and profit by product, region, and category across dedicated pages

## Pages in the Dashboard

1. **Overview** — Key KPIs (Total Sales, Total Profit, Total Orders, Avg Sales per Order) + region/product slicers + summary charts
2. **Product & Region Performance** — Product-wise and region-wise sales/profit breakdown tables
3. **Business_Insights** — Category split (donut chart), year/month sales trend lines, region/product slicers
4. **Insights & Recommendations** — Written takeaways and business recommendations
5. **Order Details** — Drillthrough target page showing order-level detail filtered by region

## DAX Measures Created (12 total)

- `Total Sales = SUM(sales_orders[sales])`
- `Total profit = SUM(sales_orders[profit])`
- `Total orders = COUNTROWS(sales_orders)`
- `Avg Sales per Order = DIVIDE([Total Sales], [Total Orders])`
- `Profit Margin % = DIVIDE([Total Profit], [Total Sales])`
- `north / south / east / west = CALCULATE([Total Sales], sales_orders[region] = "North"/"South"/"East"/"West")` — region-specific sales
- `High Sales Order = CALCULATE(COUNT(sales_orders[order_id]), FILTER(sales_orders, sales_orders[sales] > 3000))`
- `Profit Status = IF([Profit Margin %] >= 0.2, "Good", IF([Profit Margin %] >= 0.15, "Average", "Needs Improvement"))`
- `Profit Category = SWITCH(TRUE(), [Total Profit] > 800000, "Excellent", [Total Profit] > 400000, "Good", "Low")`

## Technologies Used

- Power BI Desktop
- DAX (Data Analysis Expressions)
- Star-schema data model: `sales_orders` (fact table) + `products` (dimension table)
- Slicers, drillthrough pages, KPI cards, donut/line/bar charts

## Key Insights from Analysis

- **Keyboard is the top revenue-generating product** (₹3,32,541), followed closely by Mobile (₹3,21,884) and Smartwatch (₹3,15,099) — revenue is fairly balanced across products, unlike a single dominant SKU
- **Headphones has the highest profit margin (~22.4%)**, while Smartwatch has the lowest (~17.7%) — no product falls below a 15% margin, so no product is currently flagged "Needs Improvement"
- **East region generates the highest revenue** (₹4,70,530) and **West region generates the highest profit** (₹92,252) — the two are close competitors at the top
- **South region is the weakest performer** on both revenue and profit
- **Electronics is the leading category** (₹8,93,399), well ahead of Accessories (₹5,23,509) and Office (₹3,32,541)
- Caught and fixed a DAX bug during development where "Total Orders" was summing order IDs instead of counting rows — a reminder to validate measures against raw data rather than trusting the visual output blindly

## Business Recommendations

- Double down on Keyboard, Mobile, and Smartwatch — the three products driving most of the revenue — with consistent marketing and inventory support
- Investigate why South region underperforms relative to East/West/North; consider a regional promotion or pricing review
- Headphones' strong margin makes it a good candidate for a bundle offer alongside lower-margin products like Smartwatch

## How to Open

1. Download the `.pbix` file
2. Open with Power BI Desktop (free download from microsoft.com/powerbi)
3. All visuals and data will load automatically
4. Use the region/product slicers on the Overview or Business_Insights page to filter, or right-click a region on any chart and select "Drill through → Order Details" for order-level detail

## Author

Aditya Patidar
Email: adityaptdr222@gmail.com
LinkedIn: https://www.linkedin.com/in/aditya-patidar03/
GitHub: https://github.com/adityaptdr222-a
