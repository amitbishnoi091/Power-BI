# Retail Sales Performance Analysis Dashboard – Power BI Project

Overview:
This repository contains a Retail Sales Performance Analysis dashboard created using Power BI. The dashboard provides insights into sales performance across various regions, product categories, and time periods. It also includes advanced analytical features such as forecasting and what-if analysis to aid in data-driven decision-making. The dataset used for this project simulates real-world retail sales data, allowing for deep analysis of sales trends, regional performance, and the impact of pricing on sales.

Key Insights:
Sales Trends Over Time:

The line chart reveals the fluctuation of sales across different products over time. Products like refrigerators and washing machines show seasonal demand, with noticeable peaks around mid-year and the end of the year.
Overall, sales have a positive trend, with certain months exhibiting spikes in demand, potentially influenced by seasonal factors or promotional campaigns.
Regional Sales Performance:

A geographical breakdown of sales shows that the North region consistently outperformed other regions, contributing the highest revenue. The East and South regions showed lower sales volumes, indicating possible areas for targeted marketing or promotional efforts.
This regional insight can help the business focus on underperforming regions to explore growth opportunities.
Product Category Analysis:

Among the products, refrigerators and washing machines emerged as the top-selling categories, contributing a significant portion of the overall sales. Products like geyser and microwave were lower in sales but maintained steady growth.
This analysis is vital for inventory management, helping prioritize stock levels for high-demand items.
MTD, QTD, and YTD Performance:

Month-to-date (MTD), quarter-to-date (QTD), and year-to-date (YTD) calculations were displayed using cards. This provides a quick snapshot of sales performance at various time intervals, which is crucial for tracking short-term and long-term sales goals.
Sales Dip Diagnostic:

A detailed diagnostic analysis was conducted to identify dips in sales during specific months. The clustered bar chart for sales by region across time shows that dips occurred around certain months in South and East regions, suggesting possible supply chain issues or competitive market pressures.
Predictive Analysis for Future Sales:

The forecasting feature predicts sales trends for the upcoming months, helping the business anticipate demand and prepare inventory accordingly. The SalesNextMonth measure forecasts revenue based on historical trends, showing potential sales growth in the next quarter.
What-if Analysis for Pricing Strategy:

A dynamic What-if Parameter was implemented to simulate the effect of pricing changes on overall sales. The user can adjust the price slider to observe how lowering or raising prices impacts revenue, providing actionable insights for pricing strategies during promotional events or discounts.
Steps to Recreate the Dashboard:
1. Data Preparation:
Dataset: The dataset used for this analysis contains columns such as Date, Region, Product, SalesAmount, UnitsSold, StockLevel, and Price.
Cleaning: The dataset was cleaned in Power Query Editor. Missing data were handled, and correct data types (e.g., Date) were applied to ensure consistency in the analysis.
2. DAX Calculations:
Several DAX measures were created for advanced analysis, including time intelligence functions, ranking, and forecasting:

YTD Sales: SalesYTD = TOTALYTD(SUM(retail_sales_performance_dataset[SalesAmount]), retail_sales_performance_dataset[Date])
QTD Sales: SalesQTD = TOTALQTD(SUM(retail_sales_performance_dataset[SalesAmount]), retail_sales_performance_dataset[Date])
MTD Sales: SalesMTD = TOTALMTD(SUM(retail_sales_performance_dataset[SalesAmount]), retail_sales_performance_dataset[Date])
Ranking: RankProducts = RANKX(ALL(retail_sales_performance_dataset[Product]), SUM(retail_sales_performance_dataset[SalesAmount]))
Dynamic Forecasting: SalesNextMonth = CALCULATE(SUM(retail_sales_performance_dataset[SalesAmount]), NEXTMONTH(retail_sales_performance_dataset[Date]))
3. Visualizations:
The dashboard is divided into two main pages:

Page 1: Overview of Sales Performance

Line Chart: Displays sales trends over time with product categories as the legend.
Filled Map: Provides a geographical view of sales by region.
Stacked Bar Chart: Compares sales across different product categories.
KPI Cards: Highlight MTD, QTD, and YTD sales.
Page 2: Diagnostic, Predictive, and Prescriptive Analysis

Clustered Bar Chart: Identifies sales dips by region.
Line Chart (with Forecast): Predicts future sales trends based on historical data.
What-if Parameter Slider: Simulates the impact of price changes on overall sales.
Stacked Column Chart: Correlates stock levels with units sold to optimize inventory.
4. Slicers and Filters:
To enhance interactivity, slicers were added for:

Date Range: Allows users to filter by specific time periods.
Region and Product Category: Users can drill down into specific regions or products to explore trends.
Conclusion:
This Retail Sales Performance Dashboard provides a comprehensive view of a company's sales performance, combining descriptive, diagnostic, and predictive analytics to offer actionable insights. The inclusion of advanced DAX calculations and visualizations makes it a robust tool for data-driven decision-making. Users can easily explore trends, forecast future sales, and experiment with pricing strategies using the interactive features built into the dashboard.

Files in the Repository:
Power BI Dashboard (.pbix): The interactive Power BI file containing the entire dashboard.
Dataset (.csv): The raw dataset used for the analysis.
