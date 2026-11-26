# Day 2 — SQL

**Topic:** Basic SELECT Queries

Use this table for the queries below.

| employee_id | name   | salary |
| ----------- | ------ | ------ |
| 1           | Ali    | 40000  |
| 2           | Bilal  | 60000  |
| 3           | Sara   | 55000  |
| 4           | Hassan | 30000  |

---

## 1. Find employees whose names start with the letter B.

### Answer

`LIKE` matches a pattern in text. `B%` means the name starts with B, and the rest can be anything.

- `WHERE name LIKE 'B%'` is the filter.
- `%` stands for any number of characters, including none.
- The letter before `%` is fixed, so the name must begin with B.
- In MySQL the usual collation ignores case, so `B%` also matches `bilal`.
- On this table only Bilal matches. Ali, Sara, and Hassan do not.

### Interview

I use `LIKE` with a percent sign: `SELECT * FROM Employees WHERE name LIKE 'B%'`. `B%` means the name starts with B. The result on this table is Bilal.

#### Example

```sql
SELECT *
FROM Employees
WHERE name LIKE 'B%';
```

| employee_id | name  | salary |
| ----------- | ----- | ------ |
| 2           | Bilal | 60000  |

---

## 2. Find employees whose names end with n.

### Answer

Put the percent sign first. `%n` means any characters, then an n at the end.

- `WHERE name LIKE '%n'` keeps names that end with n.
- `%` can be empty, so a name that is only `n` would also match.
- The pattern is case-insensitive on a typical MySQL collation, so `N` at the end matches too.
- On this table Hassan matches. Ali, Bilal, and Sara do not.
- A name such as `Noman` would not match, because it ends with m. A name such as `Ahsan` would match.

### Interview

The percent sign goes in front when the ending is fixed: `SELECT * FROM Employees WHERE name LIKE '%n'`. That keeps names ending in n. On this table the result is Hassan.

#### Example

```sql
SELECT *
FROM Employees
WHERE name LIKE '%n';
```

| employee_id | name   | salary |
| ----------- | ------ | ------ |
| 4           | Hassan | 30000  |
