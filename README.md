# SQL Lab 2 – Table Creation and Modification

## 📌 Overview

This lab focuses on creating new tables and modifying existing table structures using SQL DDL commands in MySQL.

## 🎯 Objectives

- Create new tables using `CREATE TABLE`
- Modify existing tables using `ALTER TABLE`
- Add new columns to existing tables
- Modify existing column definitions
- Understand how table structures can be updated according to business requirements

## 🗄️ Database

**Database:** `BankingDB`

## 📋 Tables Created

The following banking tables were created:

- `Accounts`
- `Transactions`
- `Branches`
- `AccountBranches`
- `Loans`

## 🏗️ Table Creation

### Accounts

Stores bank account information.

```sql
CREATE TABLE Accounts (
    AccountID INT,
    AccountType VARCHAR(20),
    Balance DECIMAL(10,2)
);
```

### Transactions

Stores transaction details.

```sql
CREATE TABLE Transactions (
    TransactionID INT,
    TransactionDate DATE,
    Amount DECIMAL(10,2),
    TransactionType VARCHAR(20)
);
```

### Branches

Stores bank branch information.

```sql
CREATE TABLE Branches (
    BranchID INT,
    BranchName VARCHAR(100),
    BranchAddress VARCHAR(200),
    BranchPhone VARCHAR(15)
);
```

### AccountBranches

Stores account branch-related information.

```sql
CREATE TABLE AccountBranches (
    AssignmentDate DATE
);
```

### Loans

Stores loan details.

```sql
CREATE TABLE Loans (
    LoanID INT,
    LoanAmount DECIMAL(10,2),
    InterestRate DECIMAL(5,2),
    StartDate DATE,
    EndDate DATE
);
```

## 🔧 Table Modification

The `ALTER TABLE` command was used to modify existing table structures without deleting the table.

### Add New Column

A new `DateOfBirth` column was added to the `Customers` table.

```sql
ALTER TABLE Customers
ADD DateOfBirth DATE;
```

### Modify Existing Column

The size of the `Phone` column was increased.

```sql
ALTER TABLE Customers
MODIFY Phone VARCHAR(20);
```

### Add Constraint

A minimum balance constraint was added to the `Accounts` table.

```sql
ALTER TABLE Accounts
ADD CONSTRAINT chk_MinBalance
CHECK (Balance >= 1000);
```

## 🛠️ Commands Used

- `CREATE TABLE`
- `ALTER TABLE`
- `ADD`
- `MODIFY`

## 🛠️ Tools & Technologies

- **Database:** MySQL
- **Tool:** MySQL Workbench
- **Language:** SQL

## ✅ Lab Outcome

After completing this lab, I learned how to:

- Create banking-related tables using SQL
- Modify existing table structures
- Add new columns
- Modify existing columns
- Update database structures according to requirements
- Use DDL commands in MySQL

## 📁 Project Structure

```text
SQL-Lab-2/
│
├── README.md
└── SQL-Lab-2.sql
```

## 🚀 GitHub

The completed SQL lab files are maintained in this repository for practice and version control.

### Git Commands

```bash
git add .
git commit -m "Completed SQL Lab 2"
git push origin branchName
```

Replace `branchName` with your actual branch name.

## 👩‍💻 Author

**Sakshi Shinde**
