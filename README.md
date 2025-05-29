Task 3 – SQL for Data Analysis

 Objective
The goal of this task is to perform data analysis using SQL queries on the Chinook music store database. This involves writing queries to extract insights, use joins, aggregate data, and create views.

 Tools Used
- DB Browser for SQLite
- Chinook SQLite database
- SQL (Structured Query Language)

 Dataset
The Chinook Database is a sample database that represents a digital music store, with tables for customers, invoices, tracks, artists, and more.

SQL Queries & What They Do

 1. View All Customers
  
  SELECT * FROM Customer;

  output:
  [screenshot_1_customers](https://github.com/user-attachments/assets/2ee1f4a3-09a5-4f73-954f-82ee88908355)

 3. Total Revenue
  
  SELECT SUM(Total) AS TotalRevenue FROM Invoice;

output :
[screenshot_2_total_revenue](https://github.com/user-attachments/assets/7a423c95-5529-41c5-ab64-758bf47cafdf)

4. Number of Customers by Country

SELECT Country, COUNT(*) AS NumberOfCustomers

FROM Customer

GROUP BY Country

ORDER BY NumberOfCustomers DESC;

output : 
[screenshot_3_group_by_country](https://github.com/user-attachments/assets/6153b574-8d51-417d-ade0-1d32c9bbe991)

5. Top-Paying Customers (Join Query)

SELECT c.FirstName, c.LastName, i.Total, i.InvoiceDate

FROM Invoice i

JOIN Customer c ON i.CustomerId = c.CustomerId

ORDER BY i.Total DESC;

output :
[Screenshot 2025-05-29 111818 - Copy](https://github.com/user-attachments/assets/2f7fc0e5-4f32-43a0-be1a-2807a77cf9a5)

6. Create a View for US Customers

DROP VIEW IF EXISTS US_Customers;

CREATE VIEW US_Customers AS

SELECT * FROM Customer WHERE Country = 'USA';

output :
[image](https://github.com/user-attachments/assets/84e4bac5-6c45-4029-afb3-df61c3eb2532)

6. View US Customers from the View
   
SELECT * FROM US_Customers;

output :
[image](https://github.com/user-attachments/assets/c023d24e-1d4c-4011-a38e-7c45649586a3)





