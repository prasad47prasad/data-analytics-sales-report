                Sales Data Analysis Project
Overview

This project focuses on analysing sales performance to uncover business insights, trends, and improvement opportunities. The dataset was sourced from Kaggle, and the analysis was performed using Excel, SQL, and Power BI.

The project includes data cleaning, transformation, KPI creation, and interactive dashboards designed for business decision-making.

Tools Used

Tool	Purpose
Excel	Initial data cleanup & exploration
SQL	Data querying, filtering, aggregations & transformations
Power BI	Building interactive dashboards & reports
Dataset Description

The dataset includes:

Order details (Order ID, Date, Customer, Segment)

Product information (Category, Sub-Category, Product Name)

Sales, Quantity, Discount, Profit

Shipping details and Regional information

Dashboard Pages & Insights


1. Executive Dashboard (Overview)

Goal: Provide leadership with a real-time performance summary.

Visuals Included:

KPI Cards → Total Sales, Total Profit, Total Orders, Profit Margin %

Sales Trend Line Chart

Sales by Segment Donut Chart

Sales by Region Map

Key Insights:

Profit and Sales patterns fluctuate monthly.

Consumer segment contributes the highest share of total revenue.

Certain regions outperform others significantly.



2. Sales & Profit Analysis

Goal: Evaluate sales and profitability drivers.

Visuals:

Sales by Category → Sub-category chart

Product-wise Sales & Profit table

Waterfall profit contribution chart

Key Insight:

Some products generate high sales but low or negative profit due to discounting.



3. Customer Insights

Goal: Understand customer contributions and behaviors.

Visuals:

Total Customers & Avg Sales per Customer

Top 10 Customers by Sales

Sales Heatmap by Segment & Region

Key Insight:

A small portion of customers drives a major share of revenue (Pareto Pattern).



4. Time Intelligence (Growth Trends)

Goal: Observe YoY and MoM performance.

Visuals:

This Year vs Last Year Sales Trend

YoY Growth per Month

Current vs Previous Month KPIs

Key Insight:

Seasonal patterns influence sales trends (peaks during certain months).



5. Discount & Shipping Impact

Goal: Understand how discounts and logistics affect profit.

Visuals:

Discount % vs Profit Scatter Plot

Avg Shipping Cost by Ship Mode

Avg Discount KPI

Key Insight:

Higher discounts significantly reduce profit margins.

Certain shipping modes increase cost disproportionately.



6. Regional & Market Performance

Goal: Compare business performance across regions and markets.

Visuals:

State-wise Sales Map

Sales by Market Donut Chart

Profit by Region Bar Chart

Key Insight:

Some regions show strong sales but weak profitability → requiring pricing and discount strategy adjustments.

DAX Measures Used
Total Sales = SUM(Sales[Sales])
Total Profit = SUM(Sales[Profit])
Total Orders = DISTINCTCOUNT(Sales[Order ID])
Profit Margin % = DIVIDE([Total Profit],[Total Sales])

Sales LY = CALCULATE([Total Sales], DATEADD(Calendar[Date], -1, YEAR))
YoY Growth % = DIVIDE([Total Sales] - [Sales LY], [Sales LY])

Sales LM = CALCULATE([Total Sales], DATEADD(Calendar[Date], -1, MONTH))
MoM Growth % = DIVIDE([Total Sales] - [Sales LM], [Sales LM])

Customer Count = DISTINCTCOUNT(Sales[Customer Name])
Avg Sales per Customer = DIVIDE([Total Sales], [Customer Count])

Discount % = AVERAGE(Sales[Discount])
Avg Shipping Cost = AVERAGE(Sales[Shipping Cost])

Rank Product = RANKX(ALL(Sales[Product Name]), [Total Profit], , DESC)

Project Outcomes

Identified key product and regional profit drivers.

Highlighted customer behavior trends and high-value customers.

Exposed the negative impact of heavy discounting on profitability.

Built dynamic dashboards for decision-making and trend forecasting.


How to View the Dashboard

Download the .pbix Power BI file from this repository.

Open in Power BI Desktop (free download from Microsoft Store).