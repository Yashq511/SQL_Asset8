## task8
Stored Procedure &  Function

Customer Orders Management – PostgreSQL
## 📌 Overview

This project demonstrates the use of Stored Procedures and Functions in PostgreSQL.

Stored Procedure: Inserts a new customer along with their first order.

Function: Calculates the total amount spent by a specific customer.

## 🗄 Database Structure

Tables:

1- customers – Stores customer details (customer_id, name, email).

2- orders – Stores orders (order_id, customer_id, order_amount, order_date).

## ⚙️ Features

Add customer + first order with a single procedure call.

Insert additional orders manually.

Calculate total amount spent by any customer using a function.

## 🖥 SQL Commands
Create Tables
CREATE TABLE customers (
    customer_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE
);

CREATE TABLE orders (
    order_id SERIAL PRIMARY KEY,
    customer_id INT REFERENCES customers(customer_id),
    order_amount NUMERIC(10,2),
    order_date DATE DEFAULT CURRENT_DATE
);

Stored Procedure Example
CALL add_customer_with_order('Yash Tak', 'yash@mail.com', 1200.50);

Function Usage Example
SELECT get_total_spent(1);

## 📊 Example Output
customer_id	name	total_spent
1	Neha Mishra	1700.50

## 🔄 Data Flow Diagram
![data flow diagram](https://github.com/user-attachments/assets/8b4fff37-b92a-48b4-9de8-7c6bcedf7a8f)

## 🔄 Report
![report](https://github.com/user-attachments/assets/c9998c88-f019-40a9-bc1b-271679ce47d6)
    
📌 How to Run

Create tables in PostgreSQL.

Add stored procedure and function code.

Insert data using procedure or manual inserts.

Query totals using the function.
