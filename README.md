# -database-wk-8
PLP program assignment 
# E-Commerce Store Database (MySQL)

## Overview
This project contains a complete MySQL relational schema for a simple **E-Commerce Store**.  
It demonstrates table design, relationships, and constraints suitable for a realistic small-to-medium online store.

## Features
- Customers, Addresses
- Products, Categories, Suppliers
- Inventory tracking
- Orders and Order Items (many-to-many via order_items)
- Payments
- Employees & Roles
- Product Reviews and Images
- Referential integrity via PRIMARY KEY and FOREIGN KEY constraints
- Example sample data and verification queries

## Files
- `ecommerce_schema.sql` — Main SQL script. Includes:
  - `CREATE DATABASE` and `USE` statements
  - `CREATE TABLE` statements with constraints (PK, FK, UNIQUE, NOT NULL, CHECK)
  - Sample `INSERT` data to test relationships
  - Index examples and verification `SELECT` statements

## How to run
1. Open MySQL Workbench, phpMyAdmin, or your MySQL client connected to a MySQL 8+ server.
2. Create a new SQL tab and paste the contents of `ecommerce_schema.sql`.
3. Execute the script. It will create `ecommerce_db` and the tables, then insert sample rows.
4. Run the verification queries at the bottom of the file to inspect created data.

## Schema Notes
- `orders` -> `order_items` implements the many-to-many relationship between orders and products.
- `customers` -> `addresses` is one-to-many.
- `products` belongs to `categories` and `suppliers` (many-to-one).
- `inventory` uses `product_id` as primary key to represent stock per product.
- Referential actions:
  - `ON DELETE CASCADE` used where removing parent should remove child (e.g., products -> product_images).
  - `ON DELETE SET NULL` used when preserving child rows is preferred (e.g., product's category/supplier).

## Extending this schema
- Add authentication (users & hashed passwords) and sessions table.
- Add promotions/discounts and coupon tables.
- Implement audit logging or history tables for inventory changes.
- Add triggers for automatic inventory decrement on order placement.

## License
This sample schema is provided for educational and demonstration purposes.
