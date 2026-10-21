# SQL Practice

## About SQL

SQL (Structured Query Language) is a standard language used to create, manage, and manipulate data in relational database management systems (RDBMS). It allows users to store data in tables, retrieve information, modify existing records, and maintain relationships between tables.

SQL is widely used in data analysis, application development, reporting, and database administration.

## Types of SQL Commands

### 1. DDL (Data Definition Language)

DDL commands are used to define and modify the structure of database objects such as tables.

- **CREATE:** Creates a new database or table.
- **ALTER:** Modifies the structure of an existing table.
- **DROP:** Deletes a database object.
- **TRUNCATE:** Removes all records from a table while retaining its structure.
- **RENAME:** Changes the name of a database object where supported.

Example:

```sql
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    email VARCHAR(100)
);
```

### 2. DML (Data Manipulation Language)

DML commands are used to manipulate the data stored in database tables.

- **INSERT:** Adds new records.
- **UPDATE:** Modifies existing records.
- **DELETE:** Removes records.

Example:

```sql
INSERT INTO customers
VALUES (101, 'Rahul', 'rahul@gmail.com');

UPDATE customers
SET email = 'rahul.sharma@gmail.com'
WHERE customer_id = 101;

DELETE FROM customers
WHERE customer_id = 101;
```

### 3. DQL (Data Query Language)

DQL is commonly used to describe commands that retrieve data from database tables.

**SELECT** retrieves all or selected columns from a table.

```sql
SELECT * FROM customers;

SELECT first_name, email
FROM customers
WHERE customer_id = 101;
```

### 4. DCL (Data Control Language)

DCL commands manage database access permissions.

- **GRANT:** Provides privileges to users.
- **REVOKE:** Removes previously granted privileges.

### 5. TCL (Transaction Control Language)

TCL commands manage database transactions.

- **COMMIT:** Saves transaction changes.
- **ROLLBACK:** Reverses uncommitted changes.
- **SAVEPOINT:** Creates a point within a transaction to which a rollback can be performed.

## SQL Data Types

Data types specify what kind of values a column can store.

- **INT:** Stores integer values.
- **VARCHAR:** Stores variable-length text.
- **CHAR:** Stores fixed-length text.
- **DECIMAL:** Stores exact numeric values, suitable for financial amounts.
- **DATE:** Stores date values.
- **DATETIME:** Stores date and time values.
- **BOOLEAN:** Represents true or false values where supported.

Choosing appropriate data types helps maintain data accuracy and use storage efficiently.

## SQL Constraints

Constraints enforce rules on the data stored in a table.

- **PRIMARY KEY:** Uniquely identifies each record and does not allow `NULL` values.
- **FOREIGN KEY:** Establishes a relationship between tables and maintains referential integrity.
- **NOT NULL:** Prevents a column from containing `NULL` values.
- **UNIQUE:** Prevents duplicate values in a column or combination of columns.
- **CHECK:** Restricts values according to a specified condition.
- **DEFAULT:** Assigns a predefined value when a column is omitted from an insert statement.

Example:

```sql
CREATE TABLE accounts (
    account_id INT PRIMARY KEY,
    customer_id INT NOT NULL,
    balance DECIMAL(12,2) DEFAULT 0,
    FOREIGN KEY (customer_id)
        REFERENCES customers(customer_id)
);
```

## Important SQL Operations

### Filtering Data

The `WHERE` clause filters records based on specified conditions.

```sql
SELECT *
FROM customers
WHERE customer_id = 101;
```

### Sorting Data

The `ORDER BY` clause sorts query results in ascending or descending order.

```sql
SELECT *
FROM customers
ORDER BY first_name ASC;
```

### Aggregate Functions

Aggregate functions perform calculations on multiple records.

- `COUNT()` — counts records.
- `SUM()` — calculates the total.
- `AVG()` — calculates the average.
- `MIN()` — returns the minimum value.
- `MAX()` — returns the maximum value.

Example:

```sql
SELECT COUNT(*) AS total_customers
FROM customers;
```

### GROUP BY and HAVING

`GROUP BY` groups records with matching values. `HAVING` filters grouped results, often using aggregate functions.

```sql
SELECT customer_id, COUNT(*) AS total_accounts
FROM accounts
GROUP BY customer_id
HAVING COUNT(*) > 1;
```

### Joins

Joins retrieve related information from multiple tables.

- **INNER JOIN:** Returns matching records from both tables.
- **LEFT JOIN:** Returns all records from the left table and matching records from the right table.
- **RIGHT JOIN:** Returns all records from the right table and matching records from the left table.
- **CROSS JOIN:** Returns combinations of records from both tables.

Example:

```sql
SELECT c.first_name, a.account_id, a.balance
FROM customers c
INNER JOIN accounts a
    ON c.customer_id = a.customer_id;
```

## Banking Database Concepts

Banking databases provide practical examples of relational database management. Customer information, account details, branch information, loan records, and transaction history can be stored in related tables.

- **Customers:** Stores customer details such as names, contact information, and customer identifiers.
- **Branches:** Stores information about bank branches and their locations.
- **Accounts:** Maintains account identifiers, account balances, and customer references.
- **Loans:** Stores loan-related information, including loan amounts and customer references.
- **Transactions:** Records account activities such as deposits, withdrawals, and transfers.

Primary keys uniquely identify records, while foreign keys connect related tables. These relationships help maintain data consistency and reduce unnecessary duplication.

## Entity Relationship Diagram (ERD)

An Entity Relationship Diagram represents the entities in a database, their attributes, and the relationships between them.

ER diagrams help visualize database design, identify primary and foreign keys, understand relationships, and plan the organization of relational tables.

## Importance of SQL

- Enables efficient storage and retrieval of data.
- Helps maintain data integrity through constraints.
- Supports relationships between related tables.
- Allows data filtering, sorting, grouping, and aggregation.
- Supports reporting and data analysis.
- Provides essential database skills for data analysts and software developers.

## Conclusion

SQL is an essential tool for working with relational databases. Practicing SQL commands, constraints, joins, aggregate functions, and database relationships helps develop the skills required to manage structured data and perform meaningful data analysis.

