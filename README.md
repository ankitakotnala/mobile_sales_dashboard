
# 📊 Mobile Sales Analytics Dashboard (Power BI)

# 🚀 Project Summary

This project showcases an end-to-end sales analytics solution built using Power BI, focusing on mobile sales data. The dashboard is designed to provide actionable insights into sales performance, profitability, and market trends.

It demonstrates:

Data cleaning & transformation

Data modeling

Advanced DAX calculations

Interactive dashboard design

Business insight generation

# 🎯 Problem Statement

Businesses often struggle to:

Track sales performance across regions and brands

Identify profitable products

Monitor growth trends over time

This dashboard solves these challenges by providing a centralized, interactive reporting system.

# 📂 Dataset Details

The dataset (mobile sales data.csv) contains transactional-level data.

# 🔑 Key Fields:

Order ID → Unique transaction identifier

Date → Sales date (used for time analysis)

Brand → Mobile manufacturer

Model → Product name

Region → Geographic sales area

Quantity → Units sold

Price → Selling price per unit

Total Sales → Revenue generated

Cost → Cost incurred

Profit → Revenue – Cost

# 🧱 Data Preparation (Power Query)

Steps performed:

Removed null and duplicate values

Converted data types (Date, Numeric fields)

Created calculated columns:

Revenue = Quantity × Price

Profit = Revenue – Cost

Standardized categorical fields (Brand/Region)

# 🧩 Data Modeling

Single fact table: Sales

Time-based analysis enabled using Date column

Optimized model for performance:

Removed unnecessary columns

Ensured proper data types

# 📊 Dashboard Structure
# 🟢 1. Overview Section (Top KPIs)

This section provides a quick snapshot of business performance.

KPIs displayed:

💰 Total Sales

📦 Total Quantity Sold

📈 Total Profit

📊 Profit Margin

# 📉 2. Sales Performance Analysis

Sales by Brand (Bar Chart)

Sales by Region (Column Chart)

Contribution % (Donut Chart)

👉 Helps identify:

Top-performing brands

High-revenue regions

# 📅 3. Time-Based Trends

Line chart showing Sales over time

👉 Helps identify:

Seasonal trends

Growth patterns

Sales fluctuations

# 📋 4. Detailed Breakdown

Table/Matrix with:

Brand

Model

Sales

Profit

👉 Useful for granular analysis.

# 📈 Key DAX Measures
1️⃣ Total Sales
Total Sales = SUM('Sales'[Total Sales])

2️⃣ Total Quantity
Total Quantity = SUM('Sales'[Quantity])

3️⃣ Total Profit
Total Profit = SUM('Sales'[Profit])

4️⃣ Profit Margin
Profit Margin = 
DIVIDE([Total Profit], [Total Sales], 0)

5️⃣ Average Selling Price
Avg Price = 
DIVIDE([Total Sales], [Total Quantity], 0)

6️⃣ Month-over-Month Growth
MoM Growth = 
VAR PrevMonth =
    CALCULATE(
        [Total Sales],
        PREVIOUSMONTH('Sales'[Date])
    )
RETURN
DIVIDE([Total Sales] - PrevMonth, PrevMonth, 0)

7️⃣ Top Performing Brand
Top Brand = 
TOPN(
    1,
    VALUES('Sales'[Brand]),
    [Total Sales],
    DESC
)
# 🧠 Key Insights

Certain brands consistently outperform others in total sales

Some regions generate high revenue but lower profit margins

Sales show periodic trends indicating seasonality

A small number of products contribute to a large portion of revenue (Pareto effect)

# 💼 Business Impact

This dashboard enables stakeholders to:

Make data-driven pricing decisions

Optimize inventory planning

Focus on high-performing regions/products

Improve profitability strategies

🛠 Tools & Skills Demonstrated

Power BI Desktop

DAX (Data Analysis Expressions)

Data Modeling

Data Visualization

Business Analysis


Example- Dashboard Preview-(https://github.com/ankitakotnala/mobile_sales_dashboard/blob/main/sales%20dashboard.png)

