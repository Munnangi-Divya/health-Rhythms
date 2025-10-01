# Assignment Submission

## Task Details
1. Converted the provided UXPin design into an **HTML version using Tailwind CSS**.
2. Wrote an SQL query to fetch the **second-highest-paying employee** details (Employee ID, Name, Department).

## Notes
- The implementation follows the given UXPin design.
- **This version is not responsive** (as per the assignment scope).
- Tested on desktop resolution.

## SQL Query
```sql
SELECT employee_id, name, department
FROM employees
WHERE salary = (
  SELECT MAX(salary)
  FROM employees
  WHERE salary < (SELECT MAX(salary) FROM employees)
);
