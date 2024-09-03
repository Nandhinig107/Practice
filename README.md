# Stock Management System

## Overview
This Stock Management System is a Java-based application that allows users to manage products, suppliers, and orders. The system interacts with a MySQL database using JDBC, providing a seamless way to add, view, update, and delete records for products, suppliers, and orders.

## Features

### Product Management
- **Add a new product:** Add details like name, description, price, and quantity in stock.
- **View all products:** Retrieve and display all products stored in the database.
- **View product by ID:** Fetch details of a specific product using its unique ID.
- **Update product by ID:** Modify product details using its ID.
- **Delete product by ID:** Remove a product from the database using its ID.

### Supplier Management
- **Add a new supplier:** Register a new supplier with details like name, email, phone number, and address.
- **View all suppliers:** Retrieve and display all suppliers in the database.
- **View supplier by ID:** Fetch details of a specific supplier using its unique ID.
- **Update supplier by ID:** Modify supplier details using its ID.
- **Delete supplier by ID:** Remove a supplier from the database using its ID.

### Order Management
- **Place a new order:** Create a new order by specifying the product, supplier, and quantity.
- **View all orders:** Retrieve and display all orders in the database.
- **View order by ID:** Fetch details of a specific order using its unique ID.
- **Update order by ID:** Modify the quantity of an existing order using its ID.
- **Cancel an order:** Remove an order from the database using its ID.

## Usage
After running the application, you will be presented with a menu-driven console interface that allows you to manage products, suppliers, and orders. 

## Technologies Used
- **Java**: The core programming language used for developing the application.
- **JDBC (Java Database Connectivity)**: Used for connecting the application to the MySQL database.
- **MySQL**: The relational database used to store data about products, suppliers, and orders.

## Setup Instructions

### Prerequisites
- Java Development Kit (JDK) installed
- MySQL server installed and running
- JDBC driver for MySQL added to the project classpath

### Database Setup
1. Create a MySQL database named `stock_management`.
2. Run the following SQL script to create the necessary tables:

    ```sql
    CREATE TABLE Product (
        product_id INT PRIMARY KEY AUTO_INCREMENT,
        name VARCHAR(255),
        description TEXT,
        price DOUBLE,
        quantity_in_stock INT
    );

    CREATE TABLE Supplier (
        supplier_id INT PRIMARY KEY AUTO_INCREMENT,
        name VARCHAR(255),
        email VARCHAR(255),
        phone_number VARCHAR(20),
        address TEXT
    );

    CREATE TABLE `Order` (
        order_id INT PRIMARY KEY AUTO_INCREMENT,
        product_id INT,
        supplier_id INT,
        quantity INT,
        FOREIGN KEY (product_id) REFERENCES Product(product_id),
        FOREIGN KEY (supplier_id) REFERENCES Supplier(supplier_id)
    );
    ```
## Sample Data

To test the application, you can insert some sample data into each table. Below are example SQL statements to add sample records to the `Product`, `Supplier`, and `Order` tables:

### Insert Sample Data

**Product Table:**

```sql
INSERT INTO Product (name, description, price, quantity_in_stock) VALUES
('Laptop', '15-inch laptop with 16GB RAM', 1200.00, 50),
('Smartphone', 'Latest model smartphone with 128GB storage', 700.00, 100),
('Headphones', 'Noise-cancelling over-ear headphones', 150.00, 200);

INSERT INTO Supplier (name, email, phone_number, address) VALUES
('Tech Supplies Ltd.', 'contact@techsupplies.com', '123-456-7890', '123 Tech Street, Tech City'),
('Gadget World', 'info@gadgetworld.com', '987-654-3210', '456 Gadget Avenue, Gadget Town');

INSERT INTO `Order` (product_id, supplier_id, quantity) VALUES
(1, 1, 10),  -- 10 laptops from Tech Supplies Ltd.
(2, 2, 25);  -- 25 smartphones from Gadget World

This version provides clear instructions on how to insert sample data into each table, including example SQL statements for the `Product`, `Supplier`, and `Order` tables.

### Running the Application
1. Clone the repository to your local machine.
   ```bash
   git clone https://github.com/yourusername/stock-management-system.git
