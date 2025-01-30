
# Global Super Store Sales Analysis
# Objective:
  Analyze sales and profit performance across various dimensions, focusing on product trends, 
  customer behavior, and regional insights to enhance decision-making.

# Dataset Details
  Data Source: Global Super Store Dataset (Kaggle, Excel file)
  
  About the Dataset: 
  The Global Superstore dataset is a rich and expansive collection of sales data from a hypothetical
  multinational retail corporation. This dataset encompasses a wide range of information, including 
  details about products, customers, orders, and sales across different regions and product categories.
  With its extensive scope and granularity, the dataset serves as a valuable resource for gaining insights
  into various aspects of retail operations and consumer behavior.  

# Data Transformation:
 •	Calendar Table: Created from the Order Date with split columns for Year, Month, and Day.
 
 •	Calculated Metrics: 
 
     Average Order Value (AOV): AOV = DIVIDE(SUM(Orders[Sales]), DISTINCTCOUNT(Orders[Order ID]), 0)
   
	  Return Rate (%): Return Rate (%) = DIVIDE([Total Returns], COUNT(Orders[Order ID]), 0)
________________________________________
# Key Visuals & Features
 # Page 1: Summary
 
 1.	Slicers:
   o	Filters for Market, Category, SubCategory, Product Name, Region, Country, Year, Month, Day.

 2.	Visuals:
    
    o	Map: Customer Sales by Region (Drill-up and Drill-down enabled).
  
    o	KPIs: Total Sales, Profit, Quantity, Discount, AOV, Unique Products, Shipping Cost, Return Rate.
  
    o	Bar Charts: Top 5 High-Selling and Low-Selling Products.
  
 3.	Navigation: Button to navigate to the "Sales & Performance" page.
________________________________________
# Page 2: Sales & Performance

  1.	Slicers:     
    o	Synchronized with Page 1 for consistent filtering.

  2.	Visuals:
       
    o	Stacked Column Chart: Total Sales by Product Sub-Category.
    o	Line Chart: Sales Trend by Time Period (Year and Month).    
    o	Donut Chart: Sales by Customer Segmentation.    
    o	Line & Stacked Column Chart: Profit & Sales by Product Name.    
    o	Clustered Column Chart: Top 5 Customers by Sales & Profit.    
    o	Matrix: Displays Year, Month, Day as rows and Category, SubCategory, Product Name as columns,
         with Sales as values (Drill-up and Drill-down enabled, Data Bars with Tooltips).
    
  3.	Navigation: Button to return to the "Summary" page.
________________________________________
# Technical Details
  1.	Data Model:
     
    o	Star schema with a fact table (Orders) and dimension tables (Products, Customers, Dates).
    
  2.	Relationships:

    o	Orders[Order ID] -> Returns[Order ID]    
    o	Orders[Region] -> People[Region]    
    o	Calendar[Date] -> Orders[Order Date]    
    o	Orders[Ship Date] -> Calendar[Date]
    
  3.	Key DAX Calculations:
     
    o	Average Order Value (AOV): DIVIDE(SUM(Orders[Sales]), DISTINCTCOUNT(Orders[Order ID]), 0)
    
    o	Return Rate (%): DIVIDE([Total Returns], COUNT(Orders[Order ID]), 0)
________________________________________
# Insights

•	Top-Selling Category: Technology in the North Africa region.

•	Highest Profitable Product: Canon Image Copier in the Technology category, Eastern US region.

•	Least-Selling Category: Office Supplies in the North Africa region.

•	Seasonality: Sales peak every year during November and December.

•	Customer Segmentation: The Consumer segment contributes the highest sales.
