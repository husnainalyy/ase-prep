# Day 3 — DBMS

**Topic:** Fundamentals

---

## 1. What is a table, row, column, and field?

### Answer

A table stores one kind of thing in a grid. A row is one item, a column is one kind of fact, and a field is one single value.

- A **table** is a named grid, such as `students`. It holds related data and nothing else.
- A **row** is one complete item, also called a record. Ali's id, name, and city together are one row.
- A **column** is one kind of fact for every row, also called an attribute. `city` is a column.
- A **field** is the cell where one row meets one column. Ali's city, Lahore, is one field.
- A column describes the fact. A field is the actual value stored for one row.

### Interview

A table is a grid of related data. A row is one record, such as one student. A column is one attribute, such as the city. A field is the single value at the crossing of that row and column, such as Ali's city being Lahore.

#### Example

**students**

| student_id | name | city    |
| ---------- | ---- | ------- |
| 1          | Ali  | Lahore  |
| 2          | Sara | Karachi |

The whole grid is the table. Ali's line is a row. `city` is a column. The value `Lahore` is a field.

---

## 2. What is a schema in a database?

### Answer

A schema is the plan of the database. It describes the structure, not the rows stored today.

- It names the tables and the columns in each table.
- It sets the type of each column, such as a number or text, and which columns can be empty.
- It records the keys and the links between tables.
- The schema stays the same while rows are added and deleted. Changing the schema means changing the design.
- In MySQL and PostgreSQL, a schema can also mean a named folder that holds tables. In an interview, say the structure first, then mention this second meaning.

### Interview

A schema is the design of the database: the tables, their columns, the data types, the keys, and how the tables are linked. It is the plan, not the data. Adding a student does not change the schema. Adding a new column does. In some products, schema is also the name of a container that groups tables.

#### Example

This is a schema. It has no student names in it yet:

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    class_id INT
);
```

The rule is fixed: an id, a name that cannot be empty, and a class id. Ali and Sara are data that can be inserted later. They are not part of the schema.
