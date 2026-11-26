# Day 1 — DBMS

**Topic:** Fundamentals

---

## 1. What is a database?

### Answer

A database is an organized store of related data, kept so you can find a fact and update it later.

- Data means facts, such as a name, a phone number, a mark, or a price.
- The facts are arranged on purpose. You are not hunting through loose files and notes.
- The usual picture is a table. A column is one kind of fact. A row is one complete item.
- One database can hold many tables, such as students, teachers, and fees.
- A phone contact list is a small database. Each person is a row. Name and number are columns.

### Interview

A database is an organized collection of related data. We store it so we can search, add, and update it later. In the common form, the data sits in tables. A column is one kind of fact, such as a name, and a row is one item, such as one student. A phone contact list is a database: each person is a row, and the name and number are columns.

#### Example

A shop keeps customers like this:

| id | name | city    |
| -- | ---- | ------- |
| 1  | Ali  | Lahore  |
| 2  | Sara | Karachi |

The full customer list is the database. Ali's line is one row. `city` is one column.

---

## 2. What is a DBMS?

### Answer

A DBMS is the software that creates a database and looks after it. DBMS means Database Management System.

- The database is the stored data. The DBMS is the program that controls that data.
- You ask the DBMS to add, read, update, or delete data. Those four jobs are called CRUD: Create, Read, Update, Delete.
- Many people can use the same data at the same time, and the DBMS keeps those requests in order.
- It decides who is allowed to see or change the data.
- MySQL, PostgreSQL, Oracle, and SQL Server are DBMS products. In an interview, the product is the DBMS. The tables inside it are the database.

### Interview

A DBMS is the software that manages a database. The database is the data. The DBMS stores that data and handles requests to create, read, update, and delete it. It also controls who can see the data, and it lets many users work at the same time. MySQL and PostgreSQL are examples of a DBMS.

#### Example

The saved contact list is the database. The Phone app is doing the DBMS job: you tap add, edit, or delete, and the app changes the stored list. You never open the hidden storage file and type into it yourself.

---

## 3. What is the difference between DBMS and RDBMS?

### Answer

A DBMS is any software that manages a database. An RDBMS is a DBMS that stores the data in related tables. The R stands for Relational.

- An RDBMS keeps data in tables of rows and columns, and it links those tables.
- A primary key identifies one row, such as `student_id`. Two rows do not share the same primary key.
- A foreign key is a column that points at a row in another table, such as a student row storing `class_id`.
- The link lets a fact live in one place. The class name stays in the class table, and each student stores only the class id. Splitting repeated facts like this is called normalization.
- You talk to an RDBMS with SQL. MySQL, PostgreSQL, Oracle, and SQL Server are RDBMS products.
- Some DBMS products use a different shape. MongoDB stores documents. An RDBMS stores related tables.

### Interview

A DBMS is software that manages stored data. An RDBMS is a DBMS that keeps data in tables and links the tables with keys. A primary key identifies one row. A foreign key points to a row in another table, so the same fact is stored once. We use SQL with an RDBMS. MySQL and PostgreSQL are RDBMS products. MongoDB is a DBMS that stores documents rather than related tables.

#### Example

Two linked tables:

**classes**

| class_id | class_name |
| -------- | ---------- |
| 1        | Math       |

**students**

| student_id | name | class_id |
| ---------- | ---- | -------- |
| 1          | Ali  | 1        |

`student_id` is the primary key of `students`. `class_id` in `students` is a foreign key. It points to Math in `classes`. The class name is stored once.

```sql
SELECT name
FROM students
WHERE student_id = 1;
```

This asks the RDBMS for the name in `students` whose id is 1. The result is Ali.

---
