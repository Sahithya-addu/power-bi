# 📊 Sales Performance Dashboard – Power BI Project

## 📝 Project Overview
This Power BI project analyzes sales performance across regions, products, and time periods.  
It provides insights such as revenue, profit, best-selling products, and year-over-year trends.  
The dashboard helps businesses make data-driven decisions.

---

## 🎯 Objectives
- Track Total Sales, Profit & Quantity
- Analyze monthly and yearly trends
- Identify top/low performing products
- Compare performance across regions
- Build an interactive dashboard with slicers

---

## 🗂 Dataset Description (`dataset/Sales_Data.csv`)
| Column Name          | Description |
|----------------------|-------------|
| Order ID             | Unique order number |
| Order Date           | Date of purchase |
| Customer Name        | Customer who placed the order |
| Product Category     | Category (Electronics, Furniture, etc.) |
| Product Sub-Category | Detailed product type |
| Sales                | Total sale amount |
| Profit               | Profit made |
| Quantity             | Units sold |
| Region               | Region of sale |

---

## 🛠 Tools Used
- Power BI Desktop  
- Power Query  
- DAX  
- CSV Dataset  

---

## 📐 Data Model
Star Schema:
- **Fact Table:** Sales_Fact  
- **Dimension Tables:** Date_Dim, Product_Dim, Customer_Dim, Region_Dim  

---

## 📊 DAX Measures (Copy directly)

```DAX
Total Sales = SUM(Sales_Data[Sales])

Total Profit = SUM(Sales_Data[Profit])

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

Total Quantity = SUM(Sales_Data[Quantity])

YoY Sales Growth =
VAR CurrentYear =
    YEAR(MAX(Sales_Data[Order Date]))
VAR PrevYearSales =
    CALCULATE([Total Sales],
        YEAR(Sales_Data[Order Date]) = CurrentYear - 1)
RETURN
DIVIDE([Total Sales] - PrevYearSales, PrevYearSales)
```

---

## 📊 Dashboard Screenshots
(Add your images in the `images/` folder)

```
/images/dashboard_page1.png
/images/dashboard_page2.png
```

Example:

![Dashboard Screenshot](images/dashboard_page1.png)

---

## 📂 Folder Structure

```
├── dataset
│   └── Sales_Data.csv
│
├── images
│   ├── dashboard_page1.png
│   └── dashboard_page2.png
│
├── pbix
│   └── SalesDashboard.pbix
│
└── README.md
```

---

## 🚀 How to Use
1. Download `SalesDashboard.pbix`  
2. Open using Power BI Desktop  
3. Replace dataset if needed (Power Query → Change Source)  
4. Refresh the dashboard  

---

## 📝 Resume Description (Copy-Paste)
**Sales Performance Dashboard – Power BI:**  
Developed an interactive Power BI dashboard to analyze sales KPIs including revenue, profit, and product performance.  
Built a star schema data model, cleaned data using Power Query, and created DAX measures for KPI calculations.  
Implemented slicers, drill-down visuals, and trend analysis for business insights.

---

## ⭐ Future Enhancements
- Add forecasting  
- Add RFM Customer Segmentation  
- Connect with SQL Server  

# power-bi
