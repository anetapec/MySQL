# MySQL
```bash
SELECT employees.first_name, employees.last_name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.id;
```
```bash
    SELECT locations.city, departments.department_name
    FROM locations
    LEFT JOIN departments 
    ON locations.id = departments.location_id
    ORDER BY locations.city;
```

```bash

    SELECT emp.first_name, emp.last_name, dep.department_name, loc.city
    FROM employees AS emp
    INNER JOIN departments AS dep
    ON emp.department_id = dep.id
    INNER JOIN locations AS loc
    ON dep.location_id = loc.id;
```
