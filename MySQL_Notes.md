**MySQL: Notes**

- **What is MySQL?**
  - Open-source relational database management system (RDBMS).
  - Uses Structured Query Language (SQL) for accessing and managing data.
  - Commonly used for web applications and online data storage.

**Basic Concepts:**

- **Database**: A collection of related data.
- **Table**: A structured format that holds data in rows and columns.
- **Row**: A single, data-containing record in a table.
- **Column**: A field in a table representing an attribute of the data.

**Data Types:**

- **Numeric**: `INT`, `FLOAT`, `DOUBLE`, `DECIMAL`.
- **String**: `CHAR`, `VARCHAR`, `TEXT`, `BLOB`.
- **Date/Time**: `DATE`, `TIME`, `DATETIME`, `TIMESTAMP`.

**Basic SQL Commands:**

- **Create Database**:
  ```sql
  CREATE DATABASE my_database;
  ```

- **Create Table**:
  ```sql
  CREATE TABLE users (
      id INT AUTO_INCREMENT PRIMARY KEY,
      name VARCHAR(100),
      email VARCHAR(100)
  );
  ```

- **Insert Data**:
  ```sql
  INSERT INTO users (name, email) VALUES ('Alice', 'alice@example.com');
  ```

- **Select Data**:
  ```sql
  SELECT * FROM users;
  ```

- **Update Data**:
  ```sql
  UPDATE users SET email = 'new_email@example.com' WHERE id = 1;
  ```

- **Delete Data**:
  ```sql
  DELETE FROM users WHERE id = 1;
  ```

**Joins:**

- **Inner Join**: Combines rows from two tables where conditions are met.
  ```sql
  SELECT orders.id, customers.name 
  FROM orders 
  INNER JOIN customers ON orders.customer_id = customers.id;
  ```

- **Left Join**: Returns all rows from the left table and matched rows from the right table.
  ```sql
  SELECT orders.id, customers.name 
  FROM orders 
  LEFT JOIN customers ON orders.customer_id = customers.id;
  ```

**Indexes:**

- Improve query performance by creating indexes on columns.
  ```sql
  CREATE INDEX idx_name ON users (name);
  ```

**Transactions:**

- Ensure data integrity with `START TRANSACTION`, `COMMIT`, and `ROLLBACK`.
  ```sql
  START TRANSACTION;
  UPDATE account SET balance = balance - 100 WHERE id = 1;
  UPDATE account SET balance = balance + 100 WHERE id = 2;
  COMMIT;
  ```

**Best Practices:**

- Use indexes to speed up queries.
- Normalize database to reduce redundancy.
- Regularly backup data.
- Secure MySQL server with strong passwords and access controls.

