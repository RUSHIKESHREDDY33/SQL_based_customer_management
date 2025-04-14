
This project is my complete SQL solution for managing an e-commerce platform. It includes everything from the basic schema design to advanced stored procedures, triggers, views, and performance optimization techniques. I created this database to handle product inventory, customer data, order processing, and analytical reporting.

## Table of Contents

- [Overview](#overview)
- [Database Schema](#database-schema)
- [Installation & Setup](#installation--setup)
- [Features](#features)
- [Stored Procedures](#stored-procedures)
- [Triggers](#triggers)
- [Views](#views)
- [Advanced Queries](#advanced-queries)
- [Extensions & Optimizations](#extensions--optimizations)
- [License](#license)

## Overview

This database system was built to address the needs of a full-fledged e-commerce application. It maintains:

- Users and authentication
- Product inventory and categories
- Order processing and financial calculations
- Customer reviews, wishlists, and shopping carts
- Sales analytics and detailed reporting

## Database Schema

The schema design includes the following tables:

- **users**: Manages user logins and contact info.
- **categories**: Organizes product classifications, even allowing sub-categories.
- **products**: Holds all product details with pricing, stock, and descriptions.
- **product_images**: Stores URLs for product images.
- **customers**: Links user accounts to customer data.
- **addresses**: Manages shipping and billing addresses.
- **payment_methods**: Stores payment details (credit/debit, etc.).
- **orders & order_items**: Capture order details and individual items.
- **coupons & order_coupons**: Handles discounts and promotions.
- **reviews**: Allows customers to review products.
- **wishlists & wishlist_items**: Keeps track of customer wishlist items.
- **shopping_cart & cart_items**: Maintains a persistent shopping cart.
- **inventory_log**: Keeps an audit trail of stock changes.

See the `schema.sql` file for the complete definition.

## Installation & Setup

1. **Clone this repository:**

   ```bash
   git clone https://github.com/YOUR_USERNAME/ecommerce-db.git
   cd ecommerce-db

1. 
Set up your MySQL (or MariaDB) instance.

2. 
Create the database and tables:
Open your MySQL client and run:
sqlDownloadCopy code WrapSOURCE schema.sql;
This will create the ecommerce_db database and all required tables.

3. 
Load sample data (optional):
If you want some initial data to play with, execute:
sqlDownloadCopy code WrapSOURCE sample-data.sql;


Features

* 
Comprehensive Schema:
Full tables for user management, product inventory, orders, reviews, etc.

* 
Stored Procedures:

process_new_order: Processes orders, handles discounts, updates inventory, and clears shopping carts.
get_product_recommendations: Suggests products based on purchase history.


* 
Triggers:

after_review_insert: Automatically updates product ratings after a new review is inserted.
before_order_item_insert: Checks stock levels before an order item is added.


* 
Views:

product_sales_summary: Summarizes sales data for products.
customer_purchase_history: Aggregates detailed purchase history for each customer.


* 
Advanced Queries:
Useful queries for sales analysis, best selling products, and customer segmentation.


Stored Procedures
The repository includes several procedures. Two key ones are:

* process_new_order: Handles all aspects of order processing including coupon application, tax calculation, and updating stock levels.
* get_product_recommendations: Provides product recommendations based on similar customer purchase history.

Triggers
There are triggers designed to improve data integrity:

* after_review_insert: Recalculates the average product rating every time a new review is added.
* before_order_item_insert: Prevents adding an order item if there isn’t enough stock.

Views
Views are implemented for easier reporting:

* product_sales_summary: For summarizing total quantity sold, revenue, and review metrics for products.
* customer_purchase_history: Shows detailed order and spending information for customers.

Advanced Queries
I’ve written additional advanced queries to analyze:

* Sales by month and year.
* Best selling products across categories.
* Customer segmentation based on purchasing behaviors.

Extensions & Optimizations
Future enhancements and optimization ideas include:

* Implementing full-text search for products.
* Adding geospatial support for store locators.
* Data partitioning for large transaction tables.
* Creating a lightweight data warehouse for analytics.
* Using query caching and tuning MySQL configurations.

