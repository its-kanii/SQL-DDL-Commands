# DDL Commands in SQL (Data Definition Language)

## 📌 Introduction
DDL (**Data Definition Language**) commands are used to define and manage the structure of a database. These commands include **CREATE, ALTER, DROP, TRUNCATE, and RENAME**.

---

## 🔹 **1. CREATE TABLE**
The `CREATE TABLE` command is used to define a new table in the database.

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name TEXT,
    salary REAL
);
```
✅ **Real-World Example**: Creating an `employees` table to store company employee details.

---

## 🔹 **2. ALTER TABLE**
The `ALTER TABLE` command is used to modify an existing table (add, delete, or modify columns).

```sql
ALTER TABLE employees ADD COLUMN department TEXT;
```
✅ **Real-World Example**: Adding a `department` column to an existing table.

---

## 🔹 **3. DROP TABLE**
The `DROP TABLE` command is used to delete an entire table, including its structure and data.

```sql
DROP TABLE employees;
```
✅ **Real-World Example**: Removing an outdated table permanently.

---

## 🔹 **4. DELETE vs TRUNCATE**
The `TRUNCATE` command is used to delete all records from a table without removing its structure.

### ❌ **Incorrect (Not Supported in SQLite)**
```sql
TRUNCATE TABLE employees;
```

### ✅ **Correct (SQLite Alternative)**
```sql
DELETE FROM employees;
VACUUM;
```
✅ **Real-World Example**: Removing all employee records while keeping the table structure intact.

---

## 🔹 **5. RENAME TABLE**
The `RENAME` command is used to change the name of a table.

```sql
ALTER TABLE employees RENAME TO staff;
```
✅ **Real-World Example**: Renaming `employees` table to `staff` for better clarity.

---

## 🚀 **How to Run These Commands in Jupyter Notebook?**
### **Method 1: Using SQLite in Python**
```python
import sqlite3

conn = sqlite3.connect(":memory:")
cursor = conn.cursor()

cursor.execute("CREATE TABLE employees (employee_id INT PRIMARY KEY, employee_name TEXT, salary REAL)")
cursor.execute("ALTER TABLE employees ADD COLUMN department TEXT")
cursor.execute("DELETE FROM employees")
cursor.execute("VACUUM")
cursor.execute("ALTER TABLE employees RENAME TO staff")

conn.commit()
conn.close()
```

### **Method 2: Using SQL Magic in Jupyter Notebook**
```python
!pip install ipython-sql
%load_ext sql
%sql sqlite:///:memory:
```
```sql
%%sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name TEXT,
    salary REAL
);
```

---

## 📌 **Conclusion**
These **DDL commands** are essential for managing database structures efficiently. Whether you're working in **MySQL, PostgreSQL, or SQLite**, understanding these commands is crucial for any database-related project.

💡 **Tip:** Always back up your database before using `DROP TABLE` or `TRUNCATE`!

---

## 🔗 **Connect with Me**
- GitHub: [your-github-link](https://github.com/its-kanii)
- LinkedIn: [your-linkedin-link](https://www.linkedin.com/in/kanimozhi-kathirvel-3630182a5/)

🚀 Happy Learning! 😊
