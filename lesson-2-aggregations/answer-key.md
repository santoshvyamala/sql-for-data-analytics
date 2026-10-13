# SQL Lesson 2 — Answer Key

## Exercise 1

```sql
SELECT COUNT(*), AVG(salary)
FROM employees;
```

Result: 10 employees, average salary 77000.

## Exercise 2

```sql
SELECT department, COUNT(*), AVG(salary)
FROM employees
GROUP BY department;
```

| department  | COUNT | AVG salary |
|-------------|-------|------------|
| Engineering | 3     | 95000      |
| Marketing   | 2     | 70500      |
| Sales       | 3     | 75000      |
| HR          | 2     | 59500      |

## Exercise 3

```sql
SELECT department, COUNT(*)
FROM employees
WHERE salary > 80000
GROUP BY department
ORDER BY COUNT(*) DESC;
```

| department  | COUNT |
|-------------|-------|
| Engineering | 3     |
| Sales       | 1     |

Marketing and HR have no employees over 80000, so they don't appear —
WHERE removed their rows before grouping.
