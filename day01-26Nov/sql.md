# Day 1 — SQL

**Topic:** Basic SELECT Queries

Use this table for the queries below.

| employee_id | name   | salary |
| ----------- | ------ | ------ |
| 1           | Ali    | 40000  |
| 2           | Bilal  | 60000  |
| 3           | Sara   | 55000  |
| 4           | Hassan | 30000  |

---

## 1. Retrieve all records from an Employees table.

### Answer

`SELECT *` reads every column of every row. The star means all columns.

- `SELECT` chooses the columns. `*` means do not leave any column out.
- `FROM Employees` names the table to read.
- There is no `WHERE`, so no row is filtered out.
- The result has the same columns as the table: id, name, and salary.
- Use `SELECT *` when you need the whole row. Name the columns when you only need some of them.

### Interview

To get every record, I use `SELECT * FROM Employees`. The star means all columns, and leaving out `WHERE` means all rows. The result is the full table.

#### Example

```sql
SELECT *
FROM Employees;
```

| employee_id | name   | salary |
| ----------- | ------ | ------ |
| 1           | Ali    | 40000  |
| 2           | Bilal  | 60000  |
| 3           | Sara   | 55000  |
| 4           | Hassan | 30000  |

---

## 2. Retrieve only employee names and salaries.

### Answer

Name the columns you want after `SELECT`. The other columns stay in the table, but they are not returned.

- `name, salary` asks for two columns, in that order.
- `employee_id` is not in the list, so it does not appear in the result.
- `FROM Employees` is still required. `SELECT` needs a table.
- There is no `WHERE`, so every employee is included.
- Listing columns is safer than `SELECT *` when a table later gains extra columns.

### Interview

I list the columns instead of using a star: `SELECT name, salary FROM Employees`. Every row comes back, but only those two columns. The id is stored in the table and is left out of this result.

#### Example

```sql
SELECT name, salary
FROM Employees;
```

| name   | salary |
| ------ | ------ |
| Ali    | 40000  |
| Bilal  | 60000  |
| Sara   | 55000  |
| Hassan | 30000  |

---

## 3. Find employees whose salary is greater than 50,000.

### Answer

`WHERE` keeps only the rows that pass a test. Here the test is `salary > 50000`.

- `SELECT *` still returns every column of the rows that pass.
- `WHERE` is the filter. Rows that fail the test are dropped.
- `>` means greater than, so 50000 itself is not included. Use `>=` if 50000 should count.
- Do not put quotes around the number. Quotes are for text.
- With this table, Bilal and Sara pass. Ali and Hassan do not.

### Interview

I filter with `WHERE`: `SELECT * FROM Employees WHERE salary > 50000`. The star returns the full row, and the condition keeps only salaries above 50000. On this table that is Bilal and Sara.

#### Example

```sql
SELECT *
FROM Employees
WHERE salary > 50000;
```

| employee_id | name  | salary |
| ----------- | ----- | ------ |
| 2           | Bilal | 60000  |
| 3           | Sara  | 55000  |
