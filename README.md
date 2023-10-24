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
    SELECT emp.first_name, dep.department_name, loc.city
    FROM employees AS emp
    INNER JOIN departments AS dep
    ON emp.department_id = dep.id
    INNER JOIN locations AS loc
    ON dep.location_id = loc.id
    WHERE emp.department_id IN (1,6)
    ORDER BY emp.first_name;
```

```bash

    SELECT emp.first_name, emp.last_name, dep.department_name, loc.city
    FROM employees AS emp
    INNER JOIN departments AS dep
    ON emp.department_id = dep.id
    INNER JOIN locations AS loc
    ON dep.location_id = loc.id;
```
# insert, delete, update
```bash
INSERT INTO jobs (title, min_salary, max_salary)
VALUES ('Business Analyst', 8000, 12000);
```
```bash
UPDATE jobs
SET min_salary = 3500
WHERE min_salary < 3500;
```
```bash
    UPDATE employees
    SET email = REPLACE(email, '@yahoo.com', '@gmail.com')
    WHERE job_id = 2;
     
    SELECT * FROM employees
    WHERE job_id = 2;
```

# zwiększ min salary o 5% 
# min_salary * 1,05 !!!
```bash
    UPDATE jobs
    SET min_salary = min_salary * 1.05;
     
    SELECT * FROM jobs;
```
```bash
    UPDATE departments
    SET location_id =
    (
        SELECT id FROM locations
        WHERE city = 'Opole'
    )
    WHERE location_id =
    (
        SELECT id FROM locations
        WHERE city = 'Cracow'
    );
     
    SELECT * FROM departments;
```
```bash
    DELETE FROM employees
    WHERE first_name = 'Adam' 

    AND last_name = 'Irwin';
```

```bash
    DELETE FROM employees
    WHERE email LIKE '%@gmail.com';
     
 ```
```bash
    DELETE employees FROM employees
    INNER JOIN departments
    ON employees.department_id = departments.id
    INNER JOIN locations
    ON departments.location_id = locations.id
    WHERE locations.city = 'Gdynia';
     
    SELECT * FROM employees;
```
```bash
DELETE FROM employees
WHERE department_id = 3
ORDER BY birth_date DESC
LIMIT 1;
```
