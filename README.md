# SQL Developer Internship - Task 8: Indexing for Query Optimization

## 📌 Problem
When working with large datasets, queries can become very slow due to **full table scans**.  
The objective of this task is to identify a slow query and optimize it using **indexes**.  

We use a **dummy e-commerce database** with:
- `users` table → 10,000 rows
- `orders` table → 50,000 rows

---

## ⚡ Database Setup

### 1. Create Schema
```sql
CREATE DATABASE ecommerce_db;
USE ecommerce_db;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    fullname VARCHAR(100),
    email VARCHAR(100),
    phone VARCHAR(20)
);

CREATE TABLE orders (
    order_id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    order_date DATE,
    amount DECIMAL(10,2),
    FOREIGN KEY (user_id) REFERENCES users(id)
);
