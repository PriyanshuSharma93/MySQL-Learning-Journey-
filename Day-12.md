#  Day 12 of my Learning SQL/MySQL 

# Today’s Topic:
"ORDER BY in MySQL: Single Field, Multiple Fields, Functions, CASE & NULL Handling"

# Title
   MySQL Learning Journey — Day 12: Mastering ORDER BY

# Overview
   Briefly explain the purpose of ORDER BY and why sorting query results is important when working with relational databases.

# Concepts Covered
   - ORDER BY basics
   - Sorting by a single field
   - Sorting by multiple fields
   - ASC and DESC
   - Sorting using expressions/functions
   - Sorting using CASE
   - NULL handling while sorting

# ORDER BY Basics
   Explain the syntax:

   SELECT column1, column2
   FROM table_name
   ORDER BY column_name ASC;

   Explain ASC vs DESC.

# Sorting by a Single Field
   Provide practical MySQL examples using an employees table.

# Sorting by Multiple Fields
   Explain how multiple columns can be used for sorting and how MySQL applies the secondary sort when values in the first field are equal.

   Include an example such as:

   SELECT *
   FROM employees
   ORDER BY department ASC, salary DESC;

# ORDER BY with Functions / Expressions
   Explain that ORDER BY can sort using expressions or functions.

   Include practical examples such as:
   - Sorting by LENGTH(name)
   - Sorting by calculated salary
   - Sorting using an expression

# ORDER BY with CASE
   Explain how CASE can be used to implement custom sorting logic.

   Include a practical example such as prioritizing departments:

   ORDER BY CASE
       WHEN department = 'IT' THEN 1
       WHEN department = 'HR' THEN 2
       WHEN department = 'Finance' THEN 3
       ELSE 4
   END;

   Briefly explain how the custom ranking works.

# NULL Handling
   Explain how MySQL sorts NULL values and how CASE or IS NULL can be used when custom NULL ordering is required.

   Include practical examples for:
   - NULL values first
   - NULL values last

# Practical SQL Examples
    Create a realistic employees table scenario and demonstrate:
    - Single-column sorting
    - Multiple-column sorting
    - ASC
    - DESC
    - Function-based sorting
    - CASE-based sorting
    - NULL handling

# Quick Reference Table

    Create a professional Markdown table:

    | Technique | Purpose | Example |
    |---|---|---|
    | ORDER BY column | Sort by one field | ORDER BY salary DESC |
    | Multiple fields | Apply secondary sorting | ORDER BY department, salary DESC |
    | ASC | Ascending order | ORDER BY name ASC |
    | DESC | Descending order | ORDER BY salary DESC |
    | Function | Sort using calculated value | ORDER BY LENGTH(name) |
    | CASE | Custom sorting order | ORDER BY CASE ... END |
    | NULL handling | Control NULL position | ORDER BY CASE WHEN salary IS NULL THEN 1 ELSE 0 END |

# Key Takeaways
    Add 5–7 concise technical points summarizing today's learning.

# Hands-on Practice / Screenshots
<img width="1920" height="1080" alt="Screenshot 2026-08-14 120214" src="https://github.com/user-attachments/assets/81714a2c-d836-4444-9c28-a902b30c0115" />


# Progress Checklist

    - [x] ORDER BY
    - [x] Single-field sorting
    - [x] Multiple-field sorting
    - [x] ASC
    - [x] DESC
    - [x] Function-based sorting
    - [x] Expression-based sorting
    - [x] CASE-based custom sorting
    - [x] NULL handling
    - [x] Practical MySQL queries

# Learning Reflection
    Write a short professional reflection explaining how mastering ORDER BY improves the ability to organize, analyze, and present database results effectively.

# What's Next
    Briefly mention that I will continue learning advanced SQL querying and data analysis techniques.

# Technologies
    - MySQL
    - SQL
    - MySQL Workbench

# Tags
    #MySQL #SQL #OrderBy #Database #SQLLearning #MySQLLearning #DatabaseManagement #BackendDevelopment #JavaDeveloper #FullStackDevelopment #LearningJourney #GitHub #Day12

IMPORTANT:
- Generate ONLY the final README.md content.
- Do not add any explanation before or after the README.
- Keep the writing professional and technically accurate.
- Use clean Markdown headings, tables, checklists, and code blocks.
- All SQL examples must use valid MySQL syntax.

  # SQL Commands used :

  /*
SQL Sorting and ORDER BY Tutorial
================================
This SQL script demonstrates various techniques for sorting data using ORDER BY
and includes examples ranging from basic to advanced sorting concepts.
*/

-- Section 1: Database and Table Setup
-- ----------------------------------
CREATE DATABASE db12;
USE db12;

-- Create a products table with various data types
CREATE TABLE products (
    product_id INT PRIMARY KEY,
    product_name VARCHAR(100),
    category VARCHAR(50),
    price DECIMAL(10,2),
    stock_quantity INT,
    last_updated TIMESTAMP
);

-- Insert initial sample data
INSERT INTO products VALUES
(1, 'Laptop Pro', 'Electronics', 1299.99, 50, '2024-01-15 10:00:00'),
(2, 'Desk Chair', 'Furniture', 199.99, 30, '2024-01-16 11:30:00'),
(3, 'Coffee Maker', 'Appliances', 79.99, 100, '2024-01-14 09:15:00'),
(4, 'Gaming Mouse', 'Electronics', 59.99, 200, '2024-01-17 14:20:00'),
(5, 'Bookshelf', 'Furniture', 149.99, 25, '2024-01-13 16:45:00');

-- Section 2: Basic Sorting Operations
-- ---------------------------------
-- Display all records (unsorted)
SELECT * FROM products;

-- Sort by price in ascending order (ASC is optional as it's the default)
SELECT * FROM products ORDER BY price ASC;

-- Sort by last updated timestamp
SELECT * FROM products ORDER BY last_updated;

-- Section 3: Advanced Sorting Techniques
-- ------------------------------------
-- Multiple column sorting (sort by category descending, then price descending)
SELECT * FROM products ORDER BY category DESC, price DESC;

-- Sort using column position (4 represents the price column)
SELECT * FROM products ORDER BY 4;

-- Combining WHERE clause with ORDER BY
SELECT * FROM products 
WHERE category = 'Electronics' 
ORDER BY price;

-- Case-sensitive sorting using BINARY
SELECT * FROM products ORDER BY BINARY category;

-- Section 4: Function-Based Sorting
-- -------------------------------
-- Sort by product name length
SELECT * FROM products ORDER BY LENGTH(product_name);

-- Sort by day of the month from timestamp
SELECT * FROM products ORDER BY DAY(last_updated);

-- Using LIMIT with ORDER BY to find highest stock quantity
SELECT * FROM products 
ORDER BY stock_quantity DESC 
LIMIT 1;

-- Section 5: Custom Sorting Orders
-- -----------------------------
-- Default category sorting
SELECT * FROM products ORDER BY category;

-- Custom category order using FIELD function
SELECT * FROM products 
ORDER BY FIELD(category, 'Electronics','Appliances','Furniture'), price DESC;

-- Section 6: Complex Sorting with Conditions
-- ---------------------------------------
-- Simple conditional sorting for low stock and high price items
SELECT *, 
    stock_quantity <= 50 AND price >= 200 AS priority_flag
FROM products 
ORDER BY (stock_quantity <= 50 AND price >= 200) DESC;

-- Advanced priority-based sorting using CASE
SELECT *,
    CASE
        WHEN stock_quantity <= 50 AND price >= 200 THEN 1
        WHEN stock_quantity <= 50 THEN 2
        ELSE 3
    END AS priority 
FROM products 
ORDER BY priority;

-- Section 7: Handling NULL Values
-- ----------------------------
-- Add records with NULL values for demonstration
INSERT INTO products VALUES
(6, 'Desk Lamp', 'Furniture', NULL, 45, '2024-01-18 13:25:00'),
(7, 'Keyboard', 'Electronics', 89.99, NULL, '2024-01-19 15:10:00');

-- Basic NULL handling in ORDER BY
SELECT * FROM products ORDER BY price;

-- Explicit NULL handling
SELECT *, 
    price IS NULL
FROM products 
ORDER BY price IS NULL;

-- Section 8: Working with Calculated Columns
-- --------------------------------------
-- Sort by total value (price * quantity)
SELECT *, 
    price * stock_quantity AS total_value 
FROM products 
ORDER BY total_value DESC;

-- Section 9: Query Performance Analysis
-- ---------------------------------
-- Examine query execution plan for multi-column sort
EXPLAIN SELECT * FROM products
ORDER BY category, price;

-- Compare with primary key sort performance
EXPLAIN SELECT * FROM products 
ORDER BY product_id;
- Keep explanations concise but technically useful.
- Avoid excessive emojis and unnecessary motivational quotes.
- Do not claim practical work that is not explicitly mentioned in this prompt.
