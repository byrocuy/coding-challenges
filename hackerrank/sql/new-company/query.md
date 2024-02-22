# Problem

write a query to print the company_code, founder name, total number of lead managers, total number of senior managers, total number of managers, and total number of employees. Order your output by ascending company_code.

Note:

The tables may contain duplicate records.
The company_code is string, so the sorting should not be numeric. For example, if the company_codes are C_1, C_2, and C_10, then the ascending company_codes will be C_1, C_10, and C_2.

# Solution
```sql
SELECT c.company_code, 
	c.founder, 
    count(distinct l.lead_code) as count_lead,
    count(distinct s.senior_code) as count_senior,
    count(distinct m.manager_code) as count_manager,
    count(distinct e.employee_code) as count_employee
from company c
JOIN (lead_manager l, senior_manager s, manager m, employee e)
ON (c.company_code = l.company_code AND l.company_code = s.company_code AND s.company_code = m.company_code AND m.company_code = e.company_code)
group by c.company_code, c.founder
```