# **Sales and Customer Analysis Dashboard**
![image](https://github.com/user-attachments/assets/c7c68664-6379-40d6-aec0-62b345bc6338)




## **Link to the Project**
https://public.tableau.com/app/profile/omkardabholkar/viz/SalesDashboard_17100056219520/SalesDashboard

---

## **Table of Contents**
1. Project Description
2. Technologies Used
3. Features
4. Project Implementation
5. Logical Diagram
6. Example SQL Code for Data Analysis

---

## **1. Project Description**

The **Sales and Customer Analysis Dashboard** is a comprehensive Tableau project that provides insights into sales and customer performance for the year 2023. This dashboard delivers visualizations on key metrics such as total sales, profit, customer growth, and order trends, enabling businesses to make data-driven decisions.

### **Customer Dashboard**:
- **Total Customers**: Displays the number of customers for the year, with a comparison against the previous year.
- **Sales Per Customer**: Shows the average sales generated per customer.
- **Total Orders**: Highlights the total number of orders placed.
- **Top 10 Customers by Profit**: A ranked table listing the top 10 customers based on the profit generated.

### **Sales Dashboard**:
- **Total Sales**: Depicts total sales revenue for the year, compared to the previous year.
- **Total Profit**: Displays total profit with year-on-year comparison.
- **Quantity Sold**: Shows the quantity of products sold over time.
- **Sales & Profit by Subcategory**: Provides a breakdown of sales and profit for each subcategory.

---

## **2. Technologies Used**
- **Tableau**: For data visualization and dashboard creation.
- **SQL**: To query and prepare data for analysis.
- **CSV/Excel**: Data sources were imported from these formats.
- **GitHub**: For version control and repository hosting.

---

## **3. Features**
- **Interactive Filters**: Users can filter by year, product category, subcategory, and geographical location (region, state, city).
- **Performance Comparisons**: Key metrics compared between 2023 and 2022.
- **Customer and Sales Insights**: Visualizes key customer behaviors and sales performance across different segments.
- **Profit and Loss Analysis**: The dashboard shows detailed profit and loss by subcategories.

---

## **4. Project Implementation**

### **Step 1: Data Preparation**
- Sales and customer data for 2022 and 2023 were cleaned and formatted.
- SQL queries were used to extract relevant information and aggregate it.

### **Step 2: Data Connection in Tableau**
- Data was imported from CSV/Excel formats into Tableau, and relationships were established for accurate data representation.

### **Step 3: Dashboard Design**
- Created two main dashboards: Customer Dashboard and Sales Dashboard.
- Used charts, bar graphs, and line graphs to visualize the data clearly.

### **Step 4: Interactive Filters**
- Added filter options for categories, subcategories, and location, enabling users to drill down into specific data points.

### **Step 5: Data Visualization**
- Designed charts with color coding to indicate trends, such as profit and loss. Orange denotes the lowest month, and blue denotes the highest month.

---

## **5. Example SQL Code for Data Analysis**

Here is an example SQL query used to extract sales and customer data for 2023 before importing into Tableau:

```sql
-- Query to extract customer sales and profit data
SELECT 
    customer_id, 
    customer_name, 
    order_date, 
    SUM(sales) AS total_sales, 
    SUM(profit) AS total_profit, 
    COUNT(order_id) AS total_orders
FROM 
    sales_data
WHERE 
    YEAR(order_date) = 2023
GROUP BY 
    customer_id, customer_name, order_date
ORDER BY 
    total_profit DESC;

-- Query to analyze subcategory sales and profit
SELECT 
    subcategory, 
    SUM(sales) AS total_sales, 
    SUM(profit) AS total_profit
FROM 
    product_data
WHERE 
    YEAR(order_date) = 2023
GROUP BY 
    subcategory
ORDER BY 
    total_sales DESC;
