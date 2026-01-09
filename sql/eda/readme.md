# 📊 Data Warehouse EDA: Complete Exploratory Data Analysis

## 🎯 Overview
This repository contains **25 comprehensive SQL queries** for performing Exploratory Data Analysis (EDA) on a three-tier data warehouse built with SQL Server. The analysis focuses on the Gold layer analytics tables to uncover business insights, validate data quality, and support data-driven decision making.


## 🔍 Analysis Categories
The 25 queries are organized into six logical categories:

### 1. **Data Overview & Structure** (Q1-Q3)
- Table row counts and basic metrics
- Column data type verification
- Recent transaction sampling

### 2. **Data Quality & Completeness** (Q4-Q7)
- NULL value detection in key columns
- Invalid date and value validation
- Data consistency checks

### 3. **Customer Analysis** (Q8-Q11)
- Geographic distribution by country
- Demographic breakdown (age, gender)
- Top customers by lifetime value
- Customer acquisition trends

### 4. **Product Analysis** (Q12-Q15)
- Category and product line distribution
- Price segmentation analysis
- Best-selling products by revenue
- Most profitable products by margin

### 5. **Sales & Performance Metrics** (Q16-Q20)
- Overall business KPIs dashboard
- Monthly revenue and profit trends
- Day-of-week sales patterns
- Order size and shipping performance

### 6. **Advanced Business Insights** (Q21-Q25)
- Cross-analysis of product categories by customer demographics
- Customer segmentation by purchase behavior
- Price tier profitability analysis
- Seasonal sales patterns
- Customer-product affinity analysis

## 🛠️ Prerequisites
- **Database**: SQL Server 2016 or later
- **Database Name**: `DataWarehouse`
- **Schemas**: Bronze, Silver, Gold layers must be populated
- **Required Tables**:
  - `Gold.dim_customers` (Customer dimension)
  - `Gold.dim_products` (Product dimension) 
  - `Gold.fact_sales` (Sales fact table)

## 🚀 Quick Start
1. **Clone or download** this repository
2. **Open SQL Server Management Studio** (SSMS)
3. **Connect** to your `DataWarehouse` database
4. **Open** `eda_complete_analysis.sql`
5. **Execute queries individually** or by section

## 📈 Sample Insights You'll Discover
- Which countries have the most customers
- Top 10 highest-spending customers  
- Most profitable product categories
- Monthly revenue trends
- Customer segmentation (one-time vs repeat buyers)
- Shipping performance metrics
- Seasonal sales patterns
- Price tier profitability

## 💡 Usage Tips
1. **Start with Section 1** to verify data structure
2. **Run Section 2** to validate data quality before analysis
3. **Modify date filters** in trend queries (Q17, Q24) for your date range
4. **Adjust TOP N limits** in ranking queries (Q10, Q14, Q15) as needed
5. **Export results** to Excel/Power BI for visualization


### Add Time Filters
For performance with large datasets, add WHERE clauses:
```sql
-- Add to trend queries
WHERE order_date BETWEEN '2023-01-01' AND '2023-12-31'
```




