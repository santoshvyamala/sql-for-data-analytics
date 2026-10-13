# SQL Lesson 2 — Cheat Sheet (Aggregations)

## The big idea, in plain words

Lesson 1 gave you rows. **Aggregations collapse many rows into one number.**
"How many employees are there?" is one number. "What's the average salary?"
is one number. `GROUP BY` splits the rows into groups first, then gives you
one number *per group* — e.g. average salary *per department*.

## The new keywords

- **COUNT(*)** — how many rows
- **SUM(salary)** — total of a column
- **AVG(salary)** — average of a column
- **GROUP BY department** — one result row per department

Order matters, and it matches Lesson 1's pattern:

```
SELECT → FROM → WHERE → GROUP BY → ORDER BY → LIMIT
```

**WHERE runs before GROUP BY.** So "employees earning over 80000, counted per
department" filters the rows first, then groups what's left.

## Reference examples

Practice table: `employees` (name, department, salary)

```sql
-- One number for the whole table
SELECT COUNT(*), AVG(salary)
FROM employees;

-- One row per department
SELECT department, COUNT(*), AVG(salary)
FROM employees
GROUP BY department;

-- Filter first, then group, then rank
SELECT department, COUNT(*)
FROM employees
WHERE salary > 80000
GROUP BY department
ORDER BY COUNT(*) DESC;
```

## Habits to lock in early

1. **Every plain column in SELECT must be in GROUP BY.** `SELECT department,
   AVG(salary) ... GROUP BY department` works; leaving `department` out of
   GROUP BY is an error.
2. **WHERE filters rows, GROUP BY groups what's left.** Read the query top to
   bottom: SELECT → FROM → WHERE → GROUP BY → ORDER BY → LIMIT.
3. **COUNT(*) counts rows; AVG/SUM need a numeric column.** `AVG(name)` makes
   no sense and databases will tell you so.
4. **Aggregation answers "how much / how many" questions.** If the question
   starts with "how many per…", "average by…", or "total across…", you need
   GROUP BY.
