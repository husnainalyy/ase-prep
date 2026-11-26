# Day 2 — DBMS

**Topic:** Fundamentals

---

## 1. What are the advantages of using a DBMS?

### Answer

A DBMS keeps the data in one controlled place. Many people can use it, and the facts stay correct.

- The same fact is stored once. You do not keep old and new copies in separate files.
- Many users can read and update the data at the same time. The DBMS puts those requests in order.
- Access rules decide who can see or change each part of the data.
- Rules on the columns block bad data, such as an empty name or two rows with the same id.
- The DBMS can take a backup and restore it if the data is lost or damaged.
- You search with a query instead of opening files and reading them by hand.

### Interview

A DBMS stores data in one place and controls how people use it. It avoids repeated copies, lets many users work at the same time, and limits who can see or change the data. It also rejects bad data, and it can restore a backup if something goes wrong. We ask for the data with a query instead of editing files by hand.

#### Example

Without a DBMS, the class list is one spreadsheet and the fee list is another. Ali's phone number is typed in both, and one copy is old. With a DBMS, the number lives only in the student table. The fee table stores Ali's id. Both screens read the same number.

---

## 2. What is a relational database?

### Answer

A relational database stores data in tables and links those tables with keys. Each table holds one kind of thing.

- A table is made of rows and columns. A row is one item. A column is one kind of fact.
- A primary key identifies one row. Two rows in that table do not share the same primary key.
- A foreign key is a column that points at a primary key in another table.
- Because of that link, a shared fact is stored once. A student row stores `class_id`, not a second copy of the class name.
- SQL is the language used to read and change a relational database.
- MySQL and PostgreSQL are products that store relational databases.

### Interview

A relational database keeps data in tables of rows and columns, and it links the tables with keys. A primary key identifies one row. A foreign key points to a row in another table, so a shared fact is stored once. We use SQL to read and change that data. MySQL and PostgreSQL store relational databases.

#### Example

**classes**

| class_id | class_name |
| -------- | ---------- |
| 1        | Math       |

**students**

| student_id | name | class_id |
| ---------- | ---- | -------- |
| 1          | Ali  | 1        |

`student_id` is the primary key of `students`. `class_id` in `students` is a foreign key. It points to Math in `classes`. The class name is stored once, and Ali's row only stores the number `1`.

```sql
SELECT students.name, classes.class_name
FROM students
JOIN classes ON students.class_id = classes.class_id;
```

This reads Ali together with his class name. The result is Ali and Math.
