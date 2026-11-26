# Day 3 — SQL

**Topic:** Basic SELECT Queries

Use this table for the queries below.

| employee_id | name   | salary |
| ----------- | ------ | ------ |
| 1           | Ali    | 40000  |
| 2           | Bilal  | 60000  |
| 3           | Alina  | 75000  |
| 4           | Hassan | 30000  |
| 5           | Sara   | 90000  |

---

## 1. Find employees whose names contain Ali.

### Answer

`LIKE '%Ali%'` matches the letters Ali anywhere in the name: at the start, in the middle, or at the end.

- `%` stands for any characters, including none. One `%` on each side means "Ali" can sit anywhere.
- `WHERE name LIKE '%Ali%'` is the filter.
- On a typical MySQL collation this ignores case, so `ali` inside a name matches too.
- Ali matches because the whole name is Ali. Alina matches because it begins with Ali.
- Bilal does not match. Those letters are b-i-l-a-l, which never forms a-l-i in a row.

### Interview

I use `LIKE` with a percent sign on both sides: `SELECT * FROM Employees WHERE name LIKE '%Ali%'`. That finds Ali anywhere inside the name. On this table the result is Ali and Alina.

#### Example

```sql
SELECT *
FROM Employees
WHERE name LIKE '%Ali%';
```

| employee_id | name  | salary |
| ----------- | ----- | ------ |
| 1           | Ali   | 40000  |
| 3           | Alina | 75000  |

---

## 2. Retrieve employees whose salaries are between 40,000 and 80,000.

### Answer

`BETWEEN` keeps values from the low number through the high number. Both ends count.

- `WHERE salary BETWEEN 40000 AND 80000` is the same test as `salary >= 40000 AND salary <= 80000`.
- 40000 is included. 80000 would be included. 39999 and 80001 are not.
- Write the smaller number first.
- Do not put quotes around the numbers.
- On this table Ali, Bilal, and Alina pass. Hassan is below the range. Sara is above it.

### Interview

I filter the range with `BETWEEN`: `SELECT * FROM Employees WHERE salary BETWEEN 40000 AND 80000`. Both 40000 and 80000 are included. The result is Ali, Bilal, and Alina.

#### Example

```sql
SELECT *
FROM Employees
WHERE salary BETWEEN 40000 AND 80000;
```

| employee_id | name  | salary |
| ----------- | ----- | ------ |
| 1           | Ali   | 40000  |
| 2           | Bilal | 60000  |
| 3           | Alina | 75000  |
