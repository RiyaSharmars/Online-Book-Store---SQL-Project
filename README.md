# 📚 Online Book Store – SQL Project

This project involves designing and querying a relational database system for an online book store using SQL. It simulates a real-world scenario where customers can browse, purchase books, and manage their orders. The database supports insights into inventory, customer activity, sales performance, and order management.

---

## 🗂️ Project Overview

- **Project Title:** Online Book Store
- **Technology Used:** SQL (Structured Query Language)
- **Database:** MySQL 
- **Type:** Academic / Personal SQL Project
- **Focus:** Database design, data manipulation, and analysis using SQL queries

---

## 🧱 Database Schema Includes

- **Books Table:** Book ID, Title, Author, Price, Genre, Stock
- **Customers Table:** Customer ID, Name, Email, City
- **Orders Table:** Order ID, Customer ID, Order Date, Total Amount
- **OrderDetails Table:** Order ID, Book ID, Quantity, Price
- **Authors Table:** Author ID, Name, Country
- **Genres Table:** Genre ID, Genre Name

---

## 🛠️ Features Implemented

- 🔍 Search books by title, author, or genre  
- 📦 Track inventory and low-stock books  
- 🧾 Generate sales reports by date, genre, or author  
- 👥 View top customers by purchase volume  
- 📈 Analyze revenue trends by month or book  
- 🛍️ Display order history for each customer  

---

## 📌 Sample SQL Queries

```sql
-- Get top 5 best-selling books
SELECT b.title, SUM(od.quantity) AS total_sold
FROM OrderDetails od
JOIN Books b ON od.book_id = b.book_id
GROUP BY b.title
ORDER BY total_sold DESC
LIMIT 5;

-- Find total revenue per month
SELECT MONTH(o.order_date) AS Month, SUM(o.total_amount) AS Monthly_Revenue
FROM Orders o
GROUP BY MONTH(o.order_date)
ORDER BY Month;
