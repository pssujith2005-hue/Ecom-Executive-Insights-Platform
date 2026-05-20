# Executive E-Commerce Data Analytics Platform

An end-to-end data engineering and business intelligence platform that extracts transactional data from a relational database, processes complex metrics via an optimized Star Schema, and delivers interactive executive insights.

## 📊 Live Dashboard Preview
![Dashboard Layout](Assets/dashboard_preview.png)

---

## 🏗️ Technical Architecture & Pipeline Lifecycle

1. **Relational Data Source:** Implemented a relational architecture leveraging an optimized local `SQLite` database engine storing over 10,000 historical transactional records.
2. **Middleware Pipeline:** Configured a native Windows `ODBC Data Driver` runtime environment to establish secure, absolute path connection strings directly into Power BI Desktop.
3. **Data Modeling (Star Schema):** Designed an efficient, normalized relational data model in the Power BI Model View, mapping multiple entity dimensions (`dim_customers`, `dim_products`) down into a centralized transaction ledger matrix (`fact_sales`) via 1-to-Many (`1:*`) directional filtering keys.
4. **Calculations Engine:** Engineered custom, explicit DAX logical measures inside a dedicated calculation folder container, completely bypassing low-performance implicit default columns.

---

## 🧠 Core Business Logic (Explicit DAX Formulations)

### 💵 Total Net Revenue
Calculates cumulative platform earnings post-markdowns and promotional tracking:
```dax
Total Net Revenue = SUM(fact_sales[NetRevenue])
