# Day 9 of my MySQL Learning Journey


# Title
   MySQL Learning Journey — Day 9: SQL Logical Operators

# Overview
   Briefly explain what I learned today and why logical operators are important for writing precise SQL queries.

# Concepts Covered
   - AND Operator
   - OR Operator
   - NOT Operator
   - Combining Logical Operators
   - Operator Precedence
   - Using Parentheses

# AND Operator
   Explain its purpose, syntax, and provide a practical MySQL example.

# OR Operator
   Explain its purpose, syntax, and provide a practical MySQL example.

# NOT Operator
   Explain its purpose, syntax, and provide a practical MySQL example.

# Combining AND, OR & NOT
   Provide realistic examples showing how multiple conditions can be combined using parentheses.

# Operator Precedence
   Explain the evaluation order of NOT, AND, and OR and why parentheses are useful.

# Practical SQL Examples
   Use a realistic employees table and provide several valid MySQL queries demonstrating these operators.

# Quick Reference
    Create a professional Markdown table containing:
    Operator | Purpose | Example

# Key Takeaways
    Summarize the most important concepts learned today.

# Screenshots
<img width="1920" height="1080" alt="Screenshot 2026-08-11 131537" src="https://github.com/user-attachments/assets/488df56b-5cfe-446d-95d8-7c0afdc40974" />
<img width="1920" height="1080" alt="Screenshot 2026-08-11 131526" src="https://github.com/user-attachments/assets/cc92b95b-699e-4880-9956-a983e5cc8600" />


# Progress Checklist

   -- Logical operators are used in SQL to filter records based on multiple conditions in the WHERE clause


-- AND → Returns records where both conditions are TRUE
-- OR → Returns records where at least one condition is TRUE
-- NOT → Negates a condition (returns the opposite result)

CREATE DATABASE company_db;
USE company_db;
CREATE TABLE employees (
    emp_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    age INT,
    department VARCHAR(50),
    salary DECIMAL(10,2),
    city VARCHAR(50)
);


INSERT INTO employees (name, age, department, salary, city) VALUES
('Alice Johnson', 30, 'HR', 50000, 'New York'),
('Bob Smith', 25, 'IT', 70000, 'Los Angeles'),
('Charlie Brown', 35, 'IT', 80000, 'New York'),
('David Wilson', 40, 'Finance', 90000, 'Chicago'),
('Emily Davis', 28, 'HR', 48000, 'San Francisco'),
('Franklin Moore', 32, 'IT', 75000, 'Los Angeles'),
('Grace Adams', 45, 'Finance', 95000, 'Chicago');

select * from employees;

-- Find employees who work in the IT department and earn more than $70,000
select * from employees where department='IT' and salary > 70000;

-- Find employees who work in the HR department OR live in New York
select * from employees where department= 'hr' or city = 'New York'
 
-- Find employees who are NOT in the Finance department
select * from employees where not department= 'Finance'

-- Find employees who are in IT and earn more than $70,000 OR work in Finance
SELECT * FROM employees WHERE (department = 'IT' AND salary > 70000) OR department = 'Finance';

-- Find employees who are NOT in the IT department AND do not live in Chicago
select * from employees where not department = 'IT' and not city = 'Chicago'

# Learning Reflection
    Write a short professional reflection about how understanding logical operators improves SQL filtering and query-building skills.

# What's Next
    Briefly mention the next stage of my MySQL learning journey.

# Technologies
    - MySQL
    - SQL
    - MySQL Workbench

# Tags
    #MySQL #SQL #Database #SQLLearning #MySQLLearning #DatabaseManagement #BackendDevelopment #JavaDeveloper #FullStackDevelopment #LearningJourney #GitHub #Day9

IMPORTANT:
- Generate ONLY the final README.md content.

- Do not explain anything outside the README.

- Keep the writing professional and technically accurate.

- Avoid excessive emojis and unnecessary motivational quotes.

- Use proper Markdown headings, tables, checklists, and SQL code blocks.
- All SQL examples must use valid MySQL syntax.
- Keep the README suitable for a professional GitHub portfolio.
