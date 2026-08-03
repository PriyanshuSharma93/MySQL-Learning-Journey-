

# "MySQL Data Types Mastery: VARCHAR vs INT vs DATETIME vs BLOB"



Include the following sections:

1. 🚀 Title
   - MySQL Learning Journey — Day 5
   - Mention that today I learned about MySQL Data Types and their importance in database design.

2. 📚 What I Learned Today
   - Write a short introduction explaining why choosing the correct data type is important for performance, storage efficiency, and data integrity.

3. 🗂️ Understanding MySQL Data Types
   Explain the major categories of MySQL data types:
   - Numeric Data Types
   - String Data Types
   - Date & Time Data Types
   - Binary Data Types

4. 🔢 Numeric Data Types
   Explain:
   - INT
   - BIGINT
   - SMALLINT
   - DECIMAL
   - FLOAT
   - DOUBLE

   Include:
   - Purpose
   - Syntax
   - Practical examples
   - When to use each type

5. 📝 String Data Types
   Explain:
   - CHAR
   - VARCHAR
   - TEXT

   Include:
   - Difference between CHAR and VARCHAR
   - Storage behavior
   - Practical examples

6. 📅 Date & Time Data Types
   Explain:
   - DATE
   - TIME
   - DATETIME
   - TIMESTAMP
   - YEAR

   Include examples of storing dates and timestamps.

7. 📦 Binary Data Types
   Explain:
   - BLOB
   - BINARY
   - VARBINARY

   Mention common use cases such as storing images, files, and binary data.

8. ⚖️ Comparison Tables
   Create Markdown tables comparing:
   - CHAR vs VARCHAR
   - INT vs BIGINT
   - DATETIME vs TIMESTAMP
   - TEXT vs BLOB

9. 💻 SQL Examples
   Include SQL code examples demonstrating different data types:

   ```sql
   CREATE TABLE product_details (
       id INT PRIMARY KEY,
       product_name VARCHAR(100),
       description TEXT,
       price DECIMAL(10,2),
       created_at DATETIME,
       image BLOB
   );

# Project Screenshots 
<img width="1920" height="1080" alt="Screenshot 2026-08-03 195544" src="https://github.com/user-attachments/assets/c971e2b3-3042-4871-acb4-6b16be3acbcb" />
<img width="1920" height="1080" alt="Screenshot 2026-08-03 195423" src="https://github.com/user-attachments/assets/b9e8978a-607f-4d53-b01a-e1307f43f844" />
<img width="1920" height="1080" alt="Screenshot 2026-08-03 195417" src="https://github.com/user-attachments/assets/330b34ad-67f2-4424-90b1-bacd05fa539d" />
