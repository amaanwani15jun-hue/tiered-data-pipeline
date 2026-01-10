# 📈 Advanced Data Analytics: Sales Performance Analysis

## 🎯 Overview
This repository contains **7 advanced SQL queries** for performing comprehensive sales performance analysis on a three-tier data warehouse built with SQL Server. The analysis focuses on the Gold layer analytics tables using CTEs, subqueries, and window functions to uncover deep business insights, analyze trends over time, and support strategic decision making.

## 🔍 Analysis Queries
The 7 advanced queries are designed for sophisticated analytics:

### **Query 1: Monthly Sales Trend Analysis**
- **Purpose**: Track sales performance over time with running totals and growth metrics
- **Key Features**: 
  - Monthly sales aggregation with running totals
  - Month-over-month growth percentage calculations
  - Order and unit volume tracking
- **Business Use**: Revenue forecasting, trend identification, performance tracking
- **SQL Techniques**: CTEs, Window Functions (SUM OVER, LAG), Date formatting

### **Query 2: Yearly Product Performance Comparison**
- **Purpose**: Analyze product performance year-over-year with historical comparisons
- **Key Features**:
  - Product-level yearly sales comparison
  - Comparison against product historical averages
  - Year-over-year growth calculations
- **Business Use**: Product portfolio management, growth strategy, product lifecycle analysis
- **SQL Techniques**: Multiple CTEs, Window Functions (LAG with PARTITION), Subqueries

### **Query 3: Category Contribution Analysis**
- **Purpose**: Understand market share and profitability by product category
- **Key Features**:
  - Sales contribution percentages by category
  - Profit contribution percentages
  - Category-level performance metrics
- **Business Use**: Category strategy, resource allocation, marketing focus
- **SQL Techniques**: Window Functions (SUM OVER for totals), Percentage calculations

### **Query 4: Product Cost Segmentation**
- **Purpose**: Segment products by cost ranges and analyze performance
- **Key Features**:
  - Cost-based segmentation (Low/Medium/High/Premium)
  - Revenue contribution by cost segment
  - Average product cost analysis
- **Business Use**: Pricing strategy, cost optimization, product positioning
- **SQL Techniques**: Nested CTEs, CASE statements for segmentation, Window Functions

### **Query 5: Customer Segmentation by Spending Behavior**
- **Purpose**: Classify customers into segments based on spending patterns
- **Key Features**:
  - VIP/Regular/New customer classification
  - Customer lifetime value calculation
  - Average order value and monthly spending analysis
- **Business Use**: Customer relationship management, targeted marketing, retention strategies
- **SQL Techniques**: Complex CTE chains, DATEDIFF calculations, Conditional logic

### **Query 6: Rolling 3-Month Average & Trend Analysis**
- **Purpose**: Analyze short-term trends and seasonal patterns
- **Key Features**:
  - 3-month rolling averages for sales and profit
  - Year-over-year comparisons
  - Trend direction indicators
- **Business Use**: Short-term forecasting, inventory planning, promotional timing
- **SQL Techniques**: Window Functions with ROWS BETWEEN, Multiple CTEs, Trend analysis

### **Query 7: Product Performance Quartile Analysis**
- **Purpose**: Rank products across multiple dimensions using quartiles
- **Key Features**:
  - Multi-dimensional quartile ranking (Revenue, Profit, Margin, Customers, Volume)
  - Weighted performance scoring system
  - Product categorization (Top/Good/Average/Underperformer)
- **Business Use**: Product portfolio optimization, performance benchmarking, strategic planning
- **SQL Techniques**: NTILE function, Weighted scoring algorithms, Multi-criteria ranking

## 🛠️ Prerequisites
- **Database**: SQL Server 2016 or later
- **Database Name**: `DataWarehouse`
- **Schemas**: Bronze, Silver, Gold layers must be populated
- **Required Tables**:
  - `Gold.dim_customers` (Customer dimension)
  - `Gold.dim_products` (Product dimension) 
  - `Gold.fact_sales` (Sales fact table)
- **Advanced Features**: Window functions, CTEs, and subquery support

## 🚀 Quick Start
1. **Clone or download** this repository
2. **Open SQL Server Management Studio** (SSMS)
3. **Connect** to your `DataWarehouse` database
4. **Open** `advanced_analytics_queries.sql`
5. **Execute queries individually** starting with Query 1

## 📈 Sample Insights You'll Discover
- Running total of sales over time with month-over-month growth percentages
- Product performance compared to their historical averages and previous year
- Category contributions to overall revenue and profit
- Customer segmentation (VIP, Regular, New) with detailed spending patterns
- 3-month rolling averages for identifying short-term trends
- Product performance quartiles to identify top vs. bottom performers
- Seasonal sales patterns and trend direction indicators

## 💡 Usage Tips
1. **Start with Query 1** to understand basic time series patterns
2. **Use Query 5** for customer segmentation and retention insights
3. **Analyze Query 7** for product portfolio optimization
4. **Run Query 6** for short-term forecasting and trend analysis
5. **Export results** to Excel/Power BI/Tableau for visualization and dashboard creation

### Add Time Filters
For performance with large datasets, add WHERE clauses:
```sql
-- Add to trend analysis queries
WHERE order_date BETWEEN '2023-01-01' AND '2023-12-31'
```




## 📊 Business Applications

### **For Sales Teams:**
- Track performance trends (Query 1)
- Identify growth opportunities (Query 2)
- Understand category performance (Query 3)

### **For Marketing Teams:**
- Customer segmentation (Query 5)
- Product positioning (Query 4)
- Campaign timing (Query 6)

### **For Product Management:**
- Portfolio optimization (Query 7)
- Performance benchmarking (Query 2)
- Pricing strategy (Query 4)

### **For Executive Leadership:**
- Strategic planning (All queries)
- Performance monitoring
- Decision support

---

**Note**: These advanced queries build upon foundational EDA.
