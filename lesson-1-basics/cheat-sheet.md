# SQL Lesson 1 — Cheat Sheet

_Date completed: 2026-10-09_

## The pattern every analyst uses

```
SELECT → FROM → WHERE → ORDER BY → LIMIT
```

- **SELECT** — the columns you want to see (`*` = all columns)
- **FROM** — the table you're pulling from
- **WHERE** — keep only rows matching a condition (text in single quotes, numbers without)
- **ORDER BY** — sort; add `DESC` for highest-first, `ASC` for lowest-first
- **LIMIT** — keep just the first N rows

## Reference examples

```sql
-- Everything, no filtering
SELECT * FROM employees;

-- Specific columns, filtered
SELECT name, salary
FROM employees
WHERE department = 'Marketing';

-- Filter + sort
SELECT name, salary
FROM employees
WHERE salary > 80000
ORDER BY salary DESC;

-- Top 2 by name
SELECT name
FROM employees
LIMIT 2;
```

## Habits to lock in early

1. **Use straight quotes** `'Sales'` — never curly quotes. Phone keyboards insert curly quotes and real databases reject them with a syntax error.
2. **LIMIT without ORDER BY is arbitrary** — you get *some* N rows, not the "top" N. Pair them when you want the highest/lowest.
3. **Column order in SELECT = column order in output.**
4. **WHERE filters rows before ORDER BY sorts them** — read the query top to bottom in the order: SELECT → FROM → WHERE → ORDER BY → LIMIT.

---
Next: Lesson 2 — aggregations (COUNT, SUM, AVG, GROUP BY), e.g. "average salary by department."
