# SQL Lesson 2 — Exercises

Uses the `employees` table from the Lesson 2 cheat sheet
(name, department, salary — 10 rows, departments: Engineering, Marketing,
Sales, HR).

Three exercises, each one harder than the last. Answers are in
`answer-key.md` — don't peek until you've tried.

## Exercise 1 — One number for the whole table

How many employees are there in total, and what is the average salary across
the whole company?

_Hint: no GROUP BY needed. Two aggregate functions in one SELECT._

## Exercise 2 — One row per group

Show each department with its headcount and its average salary.

_Hint: this is the classic GROUP BY pattern — the plain column (department)
must appear in GROUP BY._

## Exercise 3 — Filter, then group, then rank

Among employees earning **more than 80000**, how many does each department
have? Show the count per department, sorted highest count first.

_Hint: combine Lesson 1 (WHERE, ORDER BY DESC) with Lesson 2 (GROUP BY).
Departments with zero such employees simply won't appear._
