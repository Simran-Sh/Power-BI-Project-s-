# 📊 Global Orders Sales Performance Dashboard (Power BI)

A complete end-to-end **Sales Analytics** project built using **Excel, Power Query, Star Schema Modeling, DAX**, and interactive Power BI dashboards.  
This project analyzes **4,115 distinct order records** to uncover insights about sales, profitability, customer behavior, and operational efficiency.

---

## 📝 Project Overview

This project transforms a raw Excel dataset containing order-level details into a fully interactive and insightful Power BI dashboard. The data covers customer information, region, shipping details, product hierarchy, and financial metrics (sales, cost, profit, quantity).

The goal of this project is to help business users answer questions such as:

- Which regions and segments generate the highest sales and profit?
- Which products are the biggest profit drivers or loss-makers?
- How do sales and profit trend over time?
- How does ship mode impact profitability?
- What customer segments contribute most to business growth?

---

## 🎯 Project Goals

- Build an end-to-end **Power BI Sales Dashboard**.
- Clean and transform raw Excel data using Power Query.
- Organize data into a **Star Schema** (Fact & Dimension tables).
- Create DAX measures for KPIs and insights.
- Build interactive dashboards with drill-down capabilities.
- Provide actionable insights for decision-making.

---

## ⭐ Key Features

- Star Schema Data Model  
- Custom DAX Measures  
- Date Intelligence  
- Region, Segment & Ship Mode Insights  
- Product & Customer Analytics  
- Interactive slicers and drill-down  
- Clean UI & data storytelling  

---

## 🏗️ Data Model (Star Schema)

### ✔ Fact Table – `FactSales`
Includes:
- Order ID  
- Order Date  
- Customer  
- Segment  
- City, State, Region, Country  
- Category, Sub-Category, Product Name  
- Ship Mode  
- Sales, Cost, Profit  
- Quantity  

### ✔ Dimension Tables
#### `DimDate`
Date hierarchy (Day, Month, Year, Quarter)

#### `DimCustomer`
Customer Name, Segment

#### `DimProduct`
Product Name, Sub-Category, Category

#### `DimGeography`
City, State, Region, Country

#### `DimShipMode`
Shipping modes (Economy, Priority, etc.)

---

## 📏 KPIs Used

- Total Sales  
- Total Profit  
- Total Quantity  
- Total Orders  
- Total Customers  
- Profit Margin %  
- Average Order Value (AOV)  
- Sales per Customer  
- YoY Sales Growth  
- YoY Profit Growth  

---

## 🧮 DAX Measures

```
Total Sales = SUM(FactSales[Sales])
Total Cost = SUM(FactSales[Cost])
Total Profit = SUM(FactSales[Profit])
Total Quantity = SUM(FactSales[Quantity])
Total Orders = DISTINCTCOUNT(FactSales[Order ID])
Total Customers = DISTINCTCOUNT(DimCustomer[Customer Name])

Profit Margin % = DIVIDE([Total Profit],[Total Sales])
Average Order Value = DIVIDE([Total Sales],[Total Orders])

Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(DimDate[Date]))
Sales YoY % = DIVIDE([Total Sales] - [Sales LY],[Sales LY])
```

---

## 📈 Dashboard Pages

### **1️⃣ Executive Summary**
KPI cards, sales trends, segment & region distribution.

### **2️⃣ Product Performance**
Top/Bottom products, category insights, profitability matrix.

### **3️⃣ Customer Insights**
Top customers, segment comparison, regional contribution.

### **4️⃣ Shipping & Operations**
Ship mode analysis, profit vs. delivery type, operational insights.

---

## 🧰 Tools Used
- Microsoft Excel  
- Microsoft Power BI  
- Power Query  
- DAX  
- Data Modeling (Star Schema)

---

## 📦 Deliverables
- `.pbix` Power BI file  
- Clean Data Model  
- Dashboard visuals  
- README documentation  

---

## 🙌 Conclusion

This project demonstrates expertise in **data transformation, modeling, DAX, and dashboard design**. It delivers actionable insights that help businesses understand performance, customer behavior, and operational efficiency.
