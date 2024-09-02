# Stock Management System

## Overview

This Stock Management System is a console-based application developed using Core Java, MySQL, and JDBC. It allows users to manage products, suppliers, and orders.

### Features
- **Product Management**: Add, view, update, and delete products.
- **Supplier Management**: Add, view, update, and delete suppliers.
- **Order Management**: Place, view, update, and cancel orders.

## Project Structure


- `src/`: Contains the Java source files.
- `lib/`: Contains the MySQL JDBC driver.
- `README.md`: Provides setup and usage instructions.

## Prerequisites

- Java Development Kit (JDK) 8 or higher
- MySQL Server
- MySQL JDBC Driver

## Database Setup

1. **Create Database:**
   Run the following SQL command to create the database:

   ```sql
   CREATE DATABASE stock_management;
USE stock_management;

CREATE TABLE Product (
    product_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    description TEXT,
    price DOUBLE,
    quantity_in_stock INT
);

CREATE TABLE Supplier (
    supplier_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255),
    phone_number VARCHAR(50),
    address TEXT
);

CREATE TABLE `Order` (
    order_id INT AUTO_INCREMENT PRIMARY KEY,
    product_id INT,
    supplier_id INT,
    order_date DATE,
    delivery_date DATE,
    status VARCHAR(50),
    FOREIGN KEY (product_id) REFERENCES Product(product_id),
    FOREIGN KEY (supplier_id) REFERENCES Supplier(supplier_id)
);

## Setup Instructions

1. **Clone the Repository:**
   ```bash
   git clone <repository-url>

## Usage Instructions

### Product Management

- **Add Product**: Enter the product details when prompted.
- **View Product**: Enter the product ID to view the product details.
- **Update Product**: Enter the product ID and the new details to update the product.
- **Delete Product**: Enter the product ID to delete the product.

### Supplier Management

- **Add Supplier**: Enter the supplier details when prompted.
- **View Supplier**: Enter the supplier ID to view the supplier details.
- **Update Supplier**: Enter the supplier ID and the new details to update the supplier.
- **Delete Supplier**: Enter the supplier ID to delete the supplier.

### Order Management

- **Place Order**: Enter the product ID, supplier ID, order date, delivery date, and status to place a new order.
- **View Order**: Enter the order ID to view the order details.
- **Update Order**: Enter the order ID and the new details to update the order.
- **Cancel Order**: Enter the order ID to cancel the order.

## Troubleshooting

- **Database Connection Error**: 
  - Ensure that the MySQL server is running.
  - Verify that the database connection parameters in the `DatabaseUtil.java` file (such as the database URL, username, and password) are correct.
  - Check that the MySQL JDBC driver is correctly added to the project's classpath.

- **SQL Exceptions**:
  - Review the SQL syntax used in your queries.
  - Make sure that all foreign key constraints are respected (e.g., product IDs and supplier IDs should exist in their respective tables before creating an order).
  - Ensure that there are no NULL values where the database schema does not allow them.

- **Classpath Issues**:
  - Confirm that the MySQL JDBC driver (`mysql-connector-java-x.x.xx.jar`) is included in the `lib/` directory and is correctly added to the project's classpath in Eclipse.

- **Running the Application**:
  - If the application fails to run, ensure that you are using the correct JDK version (8 or higher).
  - Check for any compilation errors in the Eclipse IDE and resolve them before running the application.

