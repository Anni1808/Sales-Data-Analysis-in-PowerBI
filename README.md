# ⚡ ElectroHub Sales Analysis Dashboard (Power BI)

An interactive Power BI project analyzing sales performance for **ElectroHub**, a multi-category retail business. This dashboard answers key business questions, provides actionable insights, and demonstrates best practices in Power BI, data modeling, and DAX.

---

## 📊 Business Objective

ElectroHub wants a dynamic sales analytics dashboard to monitor:

- Product performance (sales, profit, quantity sold)
- Seasonal trends
- Discounts & promotions
- Customer segmentation
- Regional sales impact

---

## 🧠 Business Questions Answered

1. **Top/Bottom 5 products** by sales, profit, and quantity sold  
2. **Sales trends** across daily, monthly, quarterly, and yearly views  
3. **Sales vs. Profit** relationship  
4. Compare **sales, profit, quantity sold** between any 2 selected periods  
5. **Average discount** offered per category  
6. **Total number of orders**  
7. Show **sales, profit, discount, net sales** for each order, filtered by:
   - Product
   - Customer ID
   - Promotion category
   - Date  
8. **City-wise sales analysis**

---

## 🗂 Data Model & Structure

Follows the **Star Schema** design:

- 📌 **Fact Table**: `Fact_Sales`
- 📎 **Dimension Tables**:  
  - `Dim_Customer`  
  - `Dim_Product`  
  - `Dim_Promotion`  
  - `Calendar Table`

### Relationships:

- `CustomerID` (PK) —> `Fact_Sales[CustomerID]`  
- `ProductID` (PK) —> `Fact_Sales[ProductID]`  
- `PromotionID` (PK) —> `Fact_Sales[PromotionID]`  
- One-to-many & single-direction filter flow

---

## 🔄 Power BI Workflow

### 1. Load and Transform Data

- Used **Power Query Editor** for data cleaning and transformation
- Checked column distribution, data types, nulls, and uniqueness

### 2. Data Preparation Steps

- Merged `Price Per Unit` from `Dim_Product`
- Calculated:
  - `Total Sales = Unit Sold * Price Per Unit`
  - `Discount Value = Total Sales * Discount%`
  - `Net Sales = Total Sales - Discount Value`
- Replaced nulls with default values

---

## 💡 DAX Measures Used

```dax
-- Example for Same Period Last Year Total MTD
SLY Total MTD = 
CALCULATE([Total MTD], SAMEPERIODLASTYEAR('Calendar'[Date]))

-- Net Sales
Net Sales = [Total Sales] - [Discount Value]

-- Discount Value
Discount Value = [Total Sales] * [Discount%]
```

---

## 📈 Visual Features

- KPI Cards: Total Sales, Total Orders, Net Sales, Avg Discount
- Trendlines: Time-series analysis (daily, monthly, quarterly, yearly)
- Bar Charts: Top/Bottom 5 products
- Line + Column Chart: Profit vs Sales
- Slicers for dynamic filtering
- City-wise maps (if enabled)
- Period-over-period comparison

---


## 👩‍💻 Author

**Mahek Mehta**  
Data Analyst | Power BI Developer | Insight Storyteller  
📧 mahekmehta@gmail.com  
🔗 https://www.linkedin.com/in/mahek-mehta/

---


> _“Transforming raw sales data into business power — one chart at a time.”_
