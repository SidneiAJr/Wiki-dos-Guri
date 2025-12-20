# ⚙️ SQL Commands Explained (Text-Only Overview)

## 🧠 What Are SQL Commands?
SQL commands are **instructions** used to interact with relational databases.  
They are grouped into categories based on their purpose — such as data retrieval, modification, and database structure management.

---

## 📂 1. DDL — Data Definition Language
These commands define and modify the **structure** of database objects (tables, schemas, indexes, etc.).

### CREATE
Used to **create** new database objects like tables, views, or indexes.

### ALTER
Used to **modify** existing objects — for example, adding or removing columns in a table.

### DROP
Used to **delete** existing objects permanently from the database.

### TRUNCATE
Used to **remove all data** from a table quickly, while keeping its structure.

### RENAME
Used to **change the name** of a database object, such as a table or column.

---

## 🧾 2. DML — Data Manipulation Language
These commands manage the **data** stored inside tables.

### SELECT
Used to **retrieve** data from one or more tables.  
It’s the most common SQL command for reading information.

### INSERT
Used to **add** new records into a table.

### UPDATE
Used to **modify** existing data within a table.

### DELETE
Used to **remove** specific records from a table.

---

## 🔒 3. DCL — Data Control Language
These commands manage **permissions** and **access control** for users and roles.

### GRANT
Used to **give privileges** or access rights to users.

### REVOKE
Used to **remove privileges** previously granted to users.

---

## 🔁 4. TCL — Transaction Control Language
These commands handle **transactions**, ensuring data integrity and consistency.

### COMMIT
Used to **save** all changes made during the current transaction permanently.

### ROLLBACK
Used to **undo** changes made during the current transaction, restoring the previous state.

### SAVEPOINT
Used to **set a temporary checkpoint** within a transaction, allowing partial rollbacks.

### SET TRANSACTION
Used to **define properties** for a transaction, such as isolation level or access mode.

---

## 🧩 5. DQL — Data Query Language
Technically, this category contains mainly one command:

### SELECT
Used to **query and retrieve** information from tables.  
It’s sometimes listed separately because it focuses only on data retrieval, not modification.

---

## 📊 6. Utility or Miscellaneous Commands
These are special commands used for database management and optimization.

### EXPLAIN
Used to **analyze** how a query will be executed by the database engine.

### DESCRIBE
Used to **view table structure**, such as column names and data types.

### SHOW
Used to **display** information about databases, tables, users, or configurations.

---

## 🧱 Summary of Command Categories

| Category | Meaning | Purpose |
|-----------|----------|----------|
| DDL | Data Definition Language | Defines the database structure |
| DML | Data Manipulation Language | Manages and modifies data |
| DCL | Data Control Language | Controls access and permissions |
| TCL | Transaction Control Language | Manages transactions and ensures consistency |
| DQL | Data Query Language | Retrieves information from tables |

---

## 🧠 Final Notes
- SQL commands are **not case-sensitive**, but traditionally written in **uppercase** for clarity.  
- Each command has **variations** depending on the database system (MySQL, PostgreSQL, SQL Server, Oracle, etc.).  
- Understanding these command groups helps in designing, managing, and maintaining databases effectively.

---
