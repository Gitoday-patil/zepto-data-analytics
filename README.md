# 🛒 Zepto E-Commerce SQL Data Analysis Project

This is a **real-world Data Analyst portfolio project** based on an e-commerce inventory dataset scraped from [Zepto](https://www.zeptonow.com/) — one of India’s fastest-growing quick-commerce platforms.  
It demonstrates **SQL-based data exploration, cleaning, and business insights generation**, similar to workflows in actual retail and e-commerce analytics roles.

---

## 📌 Project Objective
To simulate the work of a data analyst in the retail/e-commerce sector by:
- Setting up a real-world inventory database.
- Performing **Exploratory Data Analysis (EDA)** using SQL.
- Cleaning and transforming messy raw data.
- Writing business-driven SQL queries to derive actionable insights.

---

## 📁 Dataset Details
**Source:** [Kaggle Zepto Inventory Dataset](https://www.kaggle.com/datasets/palvinder2006/zepto-inventory-dataset)  
Each row represents a unique product SKU (Stock Keeping Unit) with details on price, stock, category, weight, and availability.

**Columns:**
- `sku_id` – Unique product ID.
- `name` – Product name.
- `category` – Product category (e.g., Fruits, Snacks, Beverages).
- `mrp` – Maximum Retail Price (₹).
- `discountPercent` – Discount applied (%).
- `discountedSellingPrice` – Price after discount (₹).
- `availableQuantity` – Inventory quantity.
- `weightInGms` – Product weight in grams.
- `outOfStock` – Boolean flag for availability.
- `quantity` – Units per package.

---

## 🔧 Project Workflow

### 1️⃣ Database Setup
```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
```

### 2️⃣ Data Import
- Import `zepto_v2.csv` into PostgreSQL using:
```sql
\copy zepto(category,name,mrp,discountPercent,availableQuantity,
discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv' WITH (FORMAT csv, HEADER true, ENCODING 'UTF8');
```
- Save file as UTF-8 CSV format if encoding errors occur.

### 3️⃣ Data Exploration
- Count total records.
- Check null values.
- Identify product categories.
- Compare in-stock vs out-of-stock.
- Detect duplicate products by SKU.

### 4️⃣ Data Cleaning
- Remove rows with zero MRP or selling price.
- Convert prices from paise to rupees.

### 5️⃣ Business Insights Queries
- Top 10 best-value products (highest discount).
- High MRP products currently out of stock.
- Revenue estimation per category.
- Expensive products with minimal discount.
- Top 5 categories by average discount.
- Price per gram analysis.
- Product grouping by weight range.
- Total inventory weight by category.

---
## 🏁 Conclusion  
This project demonstrates how SQL can be applied to real-world e-commerce data to perform **data cleaning, exploration, and business insights generation**.  
By simulating the workflow of a professional data analyst, it showcases skills in **PostgreSQL, data wrangling, and analytical thinking** — all essential for roles in **data analytics, business intelligence, and retail analytics**.  
The same techniques can be adapted for other industries, datasets, or more advanced analytics workflows.


---

## 👨‍💻 Author
**Gitoday Devendra Patil** – Data Analyst aspiring to work in fintech, retail, and e-commerce analytics.  

