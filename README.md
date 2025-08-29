# Shopify-Sales-Funnel-Report
This Power BI project analyzes Shopify Sales &amp; Customer Funnel using 1-week store data. It highlights Net Sales, AOV, Customer Retention, Repeat Rate, LTV, and Regional Sales Trends through dynamic DAX-driven KPIs and interactive visuals, enabling businesses to make data-driven decisions.

## 📂 Dataset
- **Source:** Shopify store (1-week real data for confidentiality)  
- **Data Includes:**  
  - Orders (IDs, dates, quantities, sales values)  
  - Customers (unique IDs, order frequency)  
  - Products  
  - Payment methods  
  - Regions & cities  

---

## 🎯 Key Insights & KPIs
The dashboard highlights important **Transaction, Customer, and Retention KPIs**:  

- **Transaction Performance**
  - Net Sales: `$4.18M`
  - Total Quantity: `7,534`
  - Average Order Value (AOV): `$562.6`

- **Customer Purchase Behavior**
  - Total Customers: `4,431`
  - Single-Order Customers: `2,392`
  - Repeat Customers: `2,039`

- **Retention & Value KPIs**
  - Life Time Value (LTV): `$943.6`
  - Repeat Customer Rate: `46%`
  - Purchase Frequency: `1.68`

---

## 📊 Visualizations
The dashboard leverages a variety of visuals for clarity:  

- **KPI Cards** → Sales, Customers, LTV, Repeat Rate  
- **Line/Area Chart** → Net Sales Trends Over Time  
- **Donut Chart** → Sales by Payment Gateway (Shopify Payments, PayPal, etc.)  
- **Bar Charts** →  
  - Net Sales by Product  
  - Net Sales by City & Region  
- **Maps (Shape & Filled)** → Regional sales distribution  

All visuals are **fully interactive** with filters for:  
- Measure Selection (Net Sales, Quantity, AOV)  
- Gateway (All, PayPal, Shopify, etc.)  
- Province/Region  

---

## 🧮 DAX Queries
Several **DAX measures** were created for KPIs:  

```DAX
-- Average Order Value
AvgOrderValue =
DIVIDE(SUM(Sales[NetSales]), DISTINCTCOUNT(Sales[OrderID]), 0)

-- Life Time Value (simplified)
LTV =
DIVIDE(SUM(Sales[NetSales]), DISTINCTCOUNT(Sales[CustomerID]), 0)

-- Repeat Customers
RepeatCustomers =
CALCULATE(
    COUNTROWS(VALUES(Sales[CustomerID])),
    FILTER(VALUES(Sales[CustomerID]),
        CALCULATE(DISTINCTCOUNT(Sales[OrderID])) > 1
    )
)

-- Repeat Customer %
RepeatCustomer% =
DIVIDE([Repeat Customers], [Total Customers], 0)


🚀 Features
Fully dynamic with DAX-driven measures
KPI tracking across multiple dimensions
Customer segmentation (single vs repeat)
Region & city level drilldowns
Payment gateway performance analysis

📷 Dashboard Preview

🛠️ Tools Used
Power BI Desktop
DAX (Data Analysis Expressions) for calculations
Shopify Exported Dataset

📌 How to Use
Clone this repository
Open the .pbix file in Power BI Desktop
Explore the dashboard using slicers & filters

💡 Conclusion
This dashboard helps stakeholders understand sales trends, customer retention, and regional performance.
By analyzing repeat customers, LTV, and order values, businesses can make better marketing & sales strategy decisions.
