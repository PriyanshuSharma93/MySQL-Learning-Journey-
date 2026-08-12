# MySQL Learning Journey — Day 11

## 📌 Overview

Today I continued my MySQL learning journey by mastering **Comparison Operators in SQL**. These operators are essential for comparing values and filtering specific records from database tables.

## 🎯 Concepts Covered

* Equal to `=`
* Not equal to `!=` and `<>`
* Greater than `>`
* Less than `<`
* Greater than or equal to `>=`
* Less than or equal to `<=`
* Comparison operators with `WHERE`
* Combining comparison conditions

## 🔍 Comparison Operators

| Operator | Meaning                  | Example           |
| -------- | ------------------------ | ----------------- |
| `=`      | Equal to                 | `salary = 50000`  |
| `!=`     | Not equal to             | `salary != 50000` |
| `<>`     | Not equal to             | `salary <> 50000` |
| `>`      | Greater than             | `salary > 50000`  |
| `<`      | Less than                | `salary < 50000`  |
| `>=`     | Greater than or equal to | `salary >= 50000` |
| `<=`     | Less than or equal to    | `salary <= 50000` |

## 💻 Practical SQL Examples

```sql
SELECT *
FROM employees
WHERE salary = 50000;
```

```sql
SELECT *
FROM employees
WHERE salary > 50000;
```

```sql
SELECT *
FROM employees
WHERE salary < 50000;
```

```sql
SELECT *
FROM employees
WHERE salary >= 50000;
```

```sql
SELECT *
FROM employees
WHERE salary <= 50000;
```

```sql
SELECT *
FROM employees
WHERE department != 'HR';
```
# Commands

-- StoreDB Complete SQL Script

-- This script creates a sample database with products and orders tables

-- and demonstrates various SQL query examples

-- Create the database

CREATE DATABASE StoreDB;

USE StoreDB;

-- Create products table

CREATE TABLE products (

    product_id INT AUTO_INCREMENT PRIMARY KEY,
    product_name VARCHAR(50),
    category VARCHAR(50),
    price DECIMAL(10,2),
    stock INT
);

-- Insert sample data into products table

INSERT INTO products (product_name, category, price, stock) VALUES

('Laptop', 'Electronics', 1200.00, 10),
('Phone', 'Electronics', 800.00, 15),
('Tablet', 'Electronics', 600.00, 20),
('Headphones', 'Accessories', 150.00, 50),
('Mouse', 'Accessories', 30.00, 100),
('Keyboard', 'Accessories', 45.00, 80);

-- Create orders table

CREATE TABLE orders (

    order_id INT AUTO_INCREMENT PRIMARY KEY,
    order_date DATE,
    customer_name VARCHAR(50)
);

-- Insert sample data into orders table

INSERT INTO orders (order_date, customer_name) VALUES

('2024-02-01', 'Alice'),
('2024-02-05', 'Bob'),
('2024-02-10', 'Charlie'),
('2024-02-15', 'David');

-- ========================================
-- QUERY EXAMPLES
-- ========================================

-- Get all products with a price of exactly 600

SELECT * FROM products WHERE price = 600;


-- Get all products that are NOT priced at 800

SELECT * FROM products WHERE price <> 800;
SELECT * FROM products WHERE price != 800;

-- Get all products priced below 500

SELECT * FROM products WHERE price < 500;

-- Get all products priced above 700

SELECT * FROM products WHERE price > 700;

-- Get all products priced at or below 150

SELECT * FROM products WHERE price <= 150;

-- Get all products priced at or above 800

SELECT * FROM products WHERE price >= 800;

-- Get all products where the category is exactly "Electronics"

SELECT * FROM products WHERE category = 'Electronics';

-- Retrieve Orders Placed Before February 10, 2024

SELECT * FROM orders WHERE order_date < '2024-02-10';

-- String comparison example (alphabetical ordering)

SELECT * FROM products WHERE product_name > 'Mouse';

-- Numeric comparison with strings (lexicographic comparison)

SELECT '100' < '2';

-- Another string comparison example (lexicographic ordering)


SELECT 100 < '211fcfc';


## 🔗 Combining Comparison Operators

Comparison operators can be combined with logical operators such as `AND`, `OR`, and `NOT` to create more precise filtering conditions.

```sql
SELECT *
FROM employees
WHERE salary > 50000
AND experience >= 3;
```

```sql
SELECT *
FROM employees
WHERE salary < 40000
OR department = 'HR';
```

## 🧠 Key Takeaways

* Comparison operators are fundamental for filtering records.
* `=` checks whether two values are equal.
* `!=` and `<>` represent not equal.
* `>`, `<`, `>=`, and `<=` compare numerical or other comparable values.
* Comparison operators are commonly used with the `WHERE` clause.
* Multiple conditions can be combined using logical operators.

## 📸 Screenshots / Proof of Learning

<img width="1920" height="1080" alt="Screenshot 2026-08-12 190011" src="https://github.com/user-attachments/assets/f969f1b5-a626-4804-9c45-ff1842dd6a29" />
<img width="1920" height="1080" alt="Screenshot 2026-08-12 185923" src="https://github.com/user-attachments/assets/86d313ac-45e6-4262-be25-19e3e6286bc3" />
<img width="1920" height="1080" alt="Screenshot 2026-08-12 185913" src="https://github.com/user-attachments/assets/31eba661-115a-4801-a3c7-f65ffb7c082b" />
<img width="1920" height="1080" alt="Screenshot 2026-08-12 185900" src="https://github.com/user-attachments/assets/0ed488c8-60f5-492c-bba8-f620adebff4b" />


## ✅ Day 11 Progress

* [x] Equal to `=`
* [x] Not equal to `!=`
* [x] Not equal to `<>`
* [x] Greater than `>`
* [x] Less than `<`
* [x] Greater than or equal to `>=`
* [x] Less than or equal to `<=`
* [x] Used comparison operators with `WHERE`
* [x] Practiced combining comparison conditions

## 🚀 What's Next?

Continue building my MySQL foundation by learning more SQL filtering, sorting, grouping, aggregate functions, and advanced querying techniques.

## 💭 Learning Reflection

Understanding comparison operators has strengthened my ability to write precise SQL queries and retrieve exactly the records I need from a database.

## 🏷️ Tags

#MySQL #SQL #ComparisonOperators #Database #SQLLearning #MySQLLearning #DatabaseManagement #BackendDevelopment #JavaDeveloper #FullStackDevelopment #LearningJourney #GitHub #Day11
