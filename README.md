# 📊 Retail Sales & Inventory Performance Analysis

## 📌 Executive Summary & Business Problem
Managing thousands of SKUs and daily sales transactions in a mobile spare parts and accessories distribution center presents significant operational challenges. Without clear data-driven visualization, business stakeholders struggle to evaluate product performance, optimize inventory levels, and identify high-revenue categories.

**Key Objectives:**
1. Analyze revenue distribution across product lines (`SPAREPART`, `AKSESORIS`, `TOOLS`).
2. Identify top-performing items to streamline warehouse stock rebalancing.
3. Build an interactive business dashboard in Tableau Public for ongoing operational monitoring.

---

## 🛠️ Tech Stack & Tools
- **Database / Query Engine:** MySQL (Data Querying, Aggregation, Filtering)
- **Data Visualization:** Tableau Public
- **Data Processing:** CSV / Microsoft Excel

---

## 🗄️ Database Schemas & SQL Queries

Below are key MySQL queries executed to extract and aggregate transaction records for analysis:

### 1. Revenue & Sales Volume Aggregation by Product Type
```sql
SELECT 
    type_barang, 
    SUM(omset) AS total_revenue,
    SUM(qty) AS total_units_sold
FROM transaksi 
GROUP BY type_barang 
ORDER BY total_revenue DESC;

**Identifying Top 5 Best-Selling Products by Quantity**
SELECT 
    nama_produk, 
    brand,
    SUM(qty) AS total_units_sold 
FROM transaksi 
GROUP BY nama_produk, brand 
ORDER BY total_units_sold DESC 
LIMIT 5;

📈 Interactive Dashboard

Access the live interactive dashboard on Tableau Public:
👉 https://public.tableau.com/views/RetailSalesInventoryAnalysis-SparepartAccessories/Sheet2?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link
💡 Business Insights & Actionable Recommendations

    Core Revenue Drivers: Replacement spare parts (such as LCD assemblies and high-capacity battery units) account for the majority of total sales revenue compared to general accessories.

    Inventory Optimization: Recommended establishing higher buffer stock for high-demand battery models and LCDs to prevent stockouts and revenue loss.

    Cross-Selling Opportunities: Fast-moving accessories like USB cables and screen protectors exhibit high unit volume with lower unit prices, making them ideal candidates for product bundling with major spare part sales.

Developed by [Elga Bagja Diana] - Warehouse Leader & Data Analyst
