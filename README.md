# Ecommerce-Sales-Dashboard
Power BI dashboard analyzing e-commerce sales performance using time intelligence and KPI analysis.

**Project Overview**
This project is an interactive E-Commerce Sales Dashboard built using Power BI to analyze sales performance, profitability, and business trends.
The objective is to transform raw transactional data into meaningful insights using data modeling, DAX measures, and time intelligence functions.

**Business Objective**
To analyze:
Overall revenue and profit performance
Category and regional contribution
Sales trends over time
Profitability distribution
Growth patterns using time intelligence
This dashboard helps stakeholders make data-driven decisions regarding product strategy, regional focus, and revenue growth.

**Dataset Description**
The dataset includes:
Order ID
Order Date
Customer Name
Region
City
Category & Sub-Category
Product Name
Quantity
Unit Price
Discount
Sales
Profit
Payment Mode
A separate Calendar table was created for time intelligence calculations.

**Key KPIs Implemented**
Total Sales (Revenue)
Total Profit
Total Customers
Total Quantity Sold
Average Order Value
Year-over-Year Growth

**Data Modeling**
Created a Star Schema
Fact Table: Sales Data
Dimension Table: Calendar Table
Relationship:
DateTable[Date] → Sales[Order Date]
The Calendar table was marked as a Date table to enable proper time intelligence functions.

** DAX Measures Used**
Total Sales = SUM(Ecommerce_Sales_Data[Sales])
Total Profit = SUM(Ecommerce_Sales_Data[Profit])
Total Orders = DISTINCTCOUNT(Ecommerce_Sales_Data[Order ID])
Total Quantity = SUM(Ecommerce_Sales_Data[Quantity])
Total Customers = DISTINCTCOUNT(Ecommerce_Sales_Data[Customer Name])
AOV = DIVIDE([Total Sales],[Total Orders])
Sales Previous Year = 
CALCULATE(
    [Total Sales],
    SAMEPERIODLASTYEAR(DateTable[Date])
)
YoY % Growth = DIVIDE([Total Sales] - [Sales Previous Year], [Sales Previous Year], 0)

**Dashboard Features**
Interactive slicer (Year)
Dynamic KPI cards
Monthly sales trend analysis
Category-wise profit
Top 10 Products by sales
Region-wise performance distribution
Time intelligence calculations

**Key Insights**
Profit margins are relatively consistent across categories
Monthly sales remain consistent, indicating stable demand and minimal seasonality in the business
Regional sales distribution is relatively uniform, suggesting balanced market penetration across regions
Headphone Accusantium is the top-performing product, contributing the highest share of total sales and acting as a key revenue driver
Textbook Omnis generates the lowest sales, indicating potential underperformance or lower demand

**Tools & Technologies**
Power BI
DAX
Data Modeling
Time Intelligence Functions

**What I Learned**
Importance of filter context in DAX
Proper use of CALCULATE for time intelligence
Building interactive dashboards with slicers
Designing clean KPI-focused layouts
Converting raw data into actionable insights
