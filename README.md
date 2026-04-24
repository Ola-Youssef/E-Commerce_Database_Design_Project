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
[Download ERD Diagram](ER Diagram.drawio.png)
