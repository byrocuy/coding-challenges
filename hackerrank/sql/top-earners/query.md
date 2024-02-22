# Problem
We define an employee's total earnings to be their monthly $salary \times months$ worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as  space-separated integers.

# Solution

Solution 1
```sql
SELECT (months * salary) as earnings, count(*)
FROM employee
GROUP BY earnings
ORDER BY earnings DESC
LIMIT 1
```

Solution 2
```sql
SELECT MAX(salary*months) AS max_earnings, COUNT(*) AS num_max_earners
FROM employee
WHERE salary*months = (SELECT MAX(salary*months) FROM employee);
```