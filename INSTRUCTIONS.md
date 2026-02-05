# 📊 Power BI Dashboard Project (GitHub)

## 🚀 Project Overview
This project demonstrates an **end-to-end Power BI dashboard** built for analytics job preparation. It focuses on **data modeling, DAX, and business insights**, with strong GitHub presentation.

**Key Skills Showcased:**
- Power BI (Modeling, DAX, Visuals)
- SQL-style thinking
- Data Cleaning & Transformation
- Business Insights & Storytelling

---

## 📂 Project Structure
```
MOBILE_ANALYSIS
│
├── data/
│   └── mobile-sales-data.xlsx
│
├── Power_BI_Dashboard/
│   └── MS_Dashboard -.pbix
│
├── screenshots/
│   ├── assets
│   ├── overview.png
│   ├── MTD.png
│   └── same_period_last_year.png
│
├── README.md
│
└── INSTRUCTIONS.md


```

---

## 🗂 Dataset Description
The dataset represents **sales transactions** with the following tables:

### 📌 Fact Table – Sales
- Order ID
- Order Date
- Customer ID
- Customer Name
- Region
- Product ID
- Product Name
- Category
- Quantity
- Sales Amount
- Profit

### 📌 Dimension Tables

**Date (Calendar Table)**
- Date
- Year
- Month
- DAY
---

## 🔗 Data Model
- Sales → Date (Many-to-One)
This model improves performance and supports time-based analysis.
LIST.DATES(START DATE,TIMESTAMP,DURATION)1461=4 YEAR
LIST.DATES(#DATE(2021,1,1),1461,(1,0,0,01))
---
,,
## 📐 DAX Measures Used
```DAX

Total_Sales = SUMX(Sales_Data,Sales_Data[Units Sold]*Sales_Data[Price Per Unit]) 

Total_Quantity = SUM(Sales_Data[Units Sold]) 

Same Period Last Year = CALCULATE([Total_Sales],SAMEPERIODLASTYEAR(Custom_Calendar[Date].[Date]))

Total Profit = SUM(Sales[Profit])

Profit Margin = DIVIDE([Total Profit], [Total Sales])
MTD = TOTALMTD([Total_Sales],Custom_Calendar[Date].[Date])

YTD Sales = TOTALYTD([Total Sales], 'Date'[Date])

Transactions = COUNTROWS(Sales_Data) 

Average_Price = AVERAGE(Sales_Data[Price Per Unit])
```
---

## 📊 Dashboard Pages

### 1️⃣ Executive Overview
- KPIs: Total_Sales,Total_Quantity, Average_Price,Transactions
- Slicers :Brand,Mobile MOdel,Payment Method
- Total_Quantity by Month
- Ratings by Rating Status
- Pie chart for Payment Method
- Table - Brand,totalsales,Transactions
- Profitability sale Analysis by mobile model top 3  using filter:Top N
- Total Sales by Day Name

Edit Interaction used so it doesnot effect all. 

### 2️⃣ MTD  Performance

- Table Analysis: 
MTD = TOTALMTD([Total_Sales],Custom_Calendar[Date].[Date])
Month To Date
QTD = TOTALQTD([Total_Sales],Custom_Calendar[Date].[Date])
YTD = TOTALYTD([Total_Sales],Custom_Calendar[Date].[Date])

### 3️⃣ Same Period last Year
- Same Period Last Year = CALCULATE([Total_Sales],SAMEPERIODLASTYEAR(Custom_Calendar[Date].[Date]))
---
---


---

👤 **Author:** Jalpa Modi  
📍 **Role Target:** Data Analyst

