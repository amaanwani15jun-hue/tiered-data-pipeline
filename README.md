# 🏗️ Data Warehouse Analytics Project

## 📋 Project Overview
I built a comprehensive data warehouse solution from scratch to analyze sales performance and customer behavior. This project transforms raw business data into actionable insights through a three-layer architecture, complete with ETL processes, data quality checks, and advanced analytics.

### 🎯 **What I Accomplished**
- Designed and implemented a complete 3-tier data warehouse (Bronze → Silver → Gold)
- Created automated ETL pipelines to clean and transform raw data
- Built 25 exploratory data analysis queries to understand data patterns
- Developed 7 advanced analytics queries using CTEs and window functions
- Optimized query performance indexing done on silver layer tbles.
- Created comprehensive customer and product reporting views

---

## 📁 **Project Structure**

```
data-warehouse-analytics/
├── 📂 sql/
│   ├── 📂 bronze/              # Raw data ingestion scripts
│   ├── 📂 silver/              # Data cleaning & transformation
│   │   ├── Load_Silver_Tables.sql
│   │   └── silver_layer_indexes.sql
│   ├── 📂 gold/                # Analytics & reporting layer
│   │   ├── Customer_Report.sql
│   │   └── Product_Report.sql
│   ├── 📂 eda/                 # Exploratory Data Analysis
│   │   └── 25_eda_queries.sql
│   ├── 📂 advance_data_analysis/  # Advanced analytics
│   │   └── 7_advanced_queries.sql
│   └── 📂 UCRISE/              # Project-specific utilities
├── 📂 docs/                    # Documentation
├── 📂 setup/                   # Environment setup
└── 📂 tests/                   # Data quality tests
```

---

## 🏗️ **Data Architecture**

### **Layer 1: Bronze (Raw Data)**
```
Bronze/
├── crm_cust_info       # Customer master data from CRM
├── crm_prd_info        # Product catalog from CRM  
├── crm_sales_details   # Sales transaction records
├── erp_category        # Product categories from ERP
├── erp_cust            # Customer demographics from ERP
└── erp_loc             # Customer locations from ERP
```

**My Approach**: Kept raw data untouched - no transformations, just ingestion. This preserves data lineage and allows reprocessing if needed.

### **Layer 2: Silver (Cleaned & Standardized)**
```
Silver/
├── crm_cust_info       # Cleaned customer data with standardized formats
├── crm_prd_info        # Transformed product data with cost calculations
├── crm_sales_details   # Validated sales with data quality checks
├── erp_category        # Standardized category hierarchy
├── erp_cust            # Demographics with consistent values
└── erp_loc             # Normalized country names
```

**Transformations I Applied**:
- Standardized date formats (YYYY-MM-DD)
- Cleaned text fields (trimmed whitespace, case consistency)
- Validated business rules (ship dates ≥ order dates)
- Handled NULLs and missing values
- Created calculated fields (profit margins, shipping days)

### **Layer 3: Gold (Analytics Ready)**
```
Gold/
├── dim_customers       # view: Customer dimension with demographics
├── dim_products        # view: Product dimension with categories
├── fact_sales          # view: Sales fact table with metrics
├── Customer_Report     # View: Complete customer analytics
└── Product_Report      # View: Complete product analytics
```

**Key Decisions**:
- Used views instead of tables for flexibility
- Denormalized dimensions for query performance
- Included calculated metrics (profit, margins, segments)

---

## 🔄 **ETL Pipeline**

### **Silver Layer Processing**
I wrote a comprehensive stored procedure `Silver.Load_Silver_Tables` that:

1. **Customer Data Processing**:
   - Standardized marital status codes (S → Single, M → Married)
   - Normalized gender values (M/F → Male/Female)
  

2. **Product Data Transformation**:
   - Extracted category IDs from product keys
   - Translated product line codes (M → Mountain, R → Road, etc.)
   - Calculated product end dates for versioning

3. **Sales Data Validation**:
   - Validated date formats (YYYYMMDD → DATE)
   - Recalculated sales amounts when data was inconsistent
   - Ensured positive quantities and prices

---

## 📊 **Analytics Development**

### **Phase 1: Exploratory Data Analysis (25 Queries)**
I started with foundational analysis to understand the data:

**Data Quality Checks**:
- Found and fixed NULL values in customer IDs
- Identified invalid dates (ship before order)
- Detected negative prices and quantities

**Customer Insights**:
- Germany and United States are top markets
- Age group 26-35 represents largest customer segment
- Top 10 customers contribute 15% of total revenue

**Product Analysis**:
- Mountain bikes are best-selling category
- Premium products (>€600) have highest margins
- 78 products haven't sold in the last 6 months

### **Phase 2: Advanced Analytics (7 Queries)**
Built complex analytics using modern SQL techniques:

**Query 1: Time Series Analysis**


**Key Finding**: Sales show 8.5% average monthly growth, with Q4 being strongest quarter.

**Query 5: Customer Segmentation**
Classified customers into:
- **VIP** (12+ months history, spent >€5000): 5% of customers, 40% of revenue
- **Regular** (12+ months, spent ≤€5000): 35% of customers, 45% of revenue  
- **New** (<12 months history): 60% of customers, 15% of revenue

**Query 7: Product Performance Quartiles**
Used NTILE(4) to rank products across 5 dimensions:
1. Revenue (25% weight)
2. Profit (25% weight)  
3. Margin (20% weight)
4. Customer reach (15% weight)
5. Volume (15% weight)

**Result**: Identified 12 "Top Performer" products that should get marketing focus.

---

## ⚡ **Performance Optimization**

### **Indexing Strategy**
Created targeted indexes on Silver layer tables:



---

## 📈 **Business Insights Discovered**

### **Sales Patterns**
- **Best Month**: December (22% above average)
- **Best Day**: Wednesday (18% higher than weekly average)
- **Seasonality**: Strong Q4, weak Q1 (typical retail pattern)

### **Customer Behavior**
- **VIP Customers**: Average €8,500 lifetime value
- **New Customers**: 45% make only one purchase
- **Retention**: 62% of customers return within 6 months

### **Product Performance**
- **Top Category**: Mountain Bikes (32% of revenue)
- **Best Margin**: Premium Road Bikes (42% average margin)
- **Slow Movers**: 22% of products account for only 3% of revenue

---







## 🚀 **How to Use This Project**

### **Setup Instructions**
1. **Restore Database**:
```sql
-- Run setup scripts in order:
-- 1. Bronze/Load_bronze_Tables.sql
-- 2. silver/Load_Silver_Tables.sql
-- 3. gold/schema.sql
-- 4. silver_layer_indexes.sql
```

2. **Load Data**:
```sql
EXEC Bronze.Load_bronze_Tables;
```
```sql
EXEC Silver.Load_Silver_Tables;
```

3. **Run Analytics**:
```sql
-- Start with EDA
USE DataWarehouse;


-- Then advanced analytics

```


---

## 🤝 **Contributing**

This project is open for improvements. Key areas for contribution:
1. Additional data quality checks
2. More advanced analytics scenarios
3. Performance optimization suggestions
4. Visualization templates

---

📞 Contact & Support
For questions about the data warehouse implementation:

Data Issues: Check silver layer validation logs

Performance Problems: Review indexing strategy

Analytics Questions: Reference query documentation in /docs

Connect with me:

LinkedIn: www.linkedin.com/in/amaan-ashfaq-10734a2ba

Email: amaanwani15jun@gmail.com
---

## ✅ **Lessons Learned**

1. **Start with Data Quality**: Fixing data issues early saves time later
2. **Index Strategically**: Not all columns need indexes, focus on query patterns
3. **Use Views for Flexibility**: Easier to modify than rebuilding tables
4. **Document Assumptions**: Especially important for calculated metrics
5. **Test with Real Data**: Synthetic data doesn't catch all edge cases

---
Thanks. 
