SALES PROJECT
🔍 Project Overview
This project demonstrates a comprehensive analysis pipeline using SQL for data extraction and Python (Pandas) for further analysis, visualization, and interpretation. The dataset (referred to as df_orders) contains detailed sales transaction records including product, category, region, revenue, and profit.


⚙️ Tools & Technologies
SQL (Window functions, CTEs) – for aggregation and time-based comparisons

Python (Pandas, NumPy) – for data manipulation

Jupyter Notebook – interactive analysis


📌 Key SQL Insights
1. 🔝 Top 10 Revenue-Generating Products
sql
Copy
Edit
SELECT TOP 10 product_id, SUM(sale_price) AS sales
FROM df_orders
GROUP BY product_id
ORDER BY sales DESC

2. 📦 Top 5 Selling Products by Region
Uses window functions to rank products within each region.


3. 📈 Month-over-Month Sales Comparison (2022 vs 2023)
sql
Copy
Edit
SELECT order_month, SUM(CASE WHEN order_year = 2022 THEN sales ELSE 0 END) AS sales_2022,
SUM(CASE WHEN order_year = 2023 THEN sales ELSE 0 END) AS sales_2023
FROM ...
Insight: Understands seasonal growth patterns and helps forecast future demand.

4. 📅 Highest Sales Month by Category
sql
Copy
Edit
ROW_NUMBER() OVER (PARTITION BY category ORDER BY sales DESC)
Insight: Identifies peak-performing periods for each product category (e.g., electronics may peak in November).

5. 🚀 Highest-Growth Subcategory (2023 vs 2022)
Calculates year-over-year growth rates.


✅ Business Impact
This project can help stakeholders:

Understand which products and regions are most profitable

Track growth over time for better forecasting

Detect shifts in consumer behavior

Optimize inventory and supply chain operations
