## E-Commerce Database Design Project

## 1. Project Description

This project represents a simplified E-Commerce Database System designed to manage customers, products, orders, and order details.
It demonstrates key database design concepts such as entity modeling, relationships, normalization, ERD creation, and SQL query development.

## 2. Table of Contents

- [Relationships Between Entities](#relationships-between-entities)
- [ERD Diagram](#erd-diagram)
- [Database Schema Scripts](#database-schema-scripts)
- [SQL Queries](#sql-queries)

## 3. Relationships Between Entities 
-Customer (1) ─────── (M) Order
One customer can place many orders.

-Order (1) ─────── (M) Order_Details
One order can contain multiple order items.

-Product (1) ─────── (M) Order_Details
One product can appear in many order details.

-Order (M) ─────── (M) Product
Many-to-Many (resolved via Order_Details table)

## 4. ERD Diagram
![ER Diagram](ER_Diagram.png)

## 5. Schema Scripts
```
USE [E-Commerce_DB_Design];

CREATE TABLE Category (
    category_id INT PRIMARY KEY,
    category_name VARCHAR(50) NOT NULL
);

CREATE TABLE Product (
    product_id INT PRIMARY KEY,
    category_id INT,
    name VARCHAR(100),
    description VARCHAR(255),
    price DECIMAL(10,2),
    stock_quantity INT,
    FOREIGN KEY (category_id) REFERENCES Category(category_id)
);

CREATE TABLE Customer (
    customer_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(100),
    password VARCHAR(100)
);

CREATE TABLE [Order] (
    order_id INT PRIMARY KEY,
    customer_id INT,
    order_date DATE,
    total_amount DECIMAL(10,2),
    FOREIGN KEY (customer_id) REFERENCES Customer(customer_id)
);

CREATE TABLE Order_Details (
    order_detail_id INT PRIMARY KEY,
    order_id INT,
    product_id INT,
    quantity INT
);
