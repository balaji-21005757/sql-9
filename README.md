## Experiment 9
## Aim:
To implement ROLLUP function.

## Algorithm:
1.Start MYSQL Workbench.

2.Create a database to store your data.

3.Use the database and create a table.

4.Inside the table ,create variables with appropriate datatype.

5.Insert values and apply logic to visualize the output.

## Program:
```
CREATE TABLE EMPLOYEE (  
 emp_id int identity,  
 fullname varchar(65),  
 occupation varchar(45),  
 gender varchar(30),  
 salary int,  
 country varchar(55)  
);  
INSERT INTO EMPLOYEE(fullname, occupation, gender, salary, country)  
VALUES ('John Doe', 'Writer', 'Male', 62000, 'USA'),  
('Mary Greenspan', 'Freelancer', 'Female', 55000, 'India'),  
('Grace Smith', 'Scientist', 'Male', 85000, 'USA'),  
('Mike Johnson', 'Manager', 'Male', 250000, 'India'),  
('Todd Astel', 'Business Analyst', 'Male', 42000, 'India');
SELECT country, SUM(salary) AS "Total Salary"  
FROM EMPLOYEE  
GROUP BY country;  
SELECT country, SUM(salary) AS "Total Salary"  
FROM EMPLOYEE  
GROUP BY ROLLUP (country);  
SELECT country, SUM(salary) AS "Total Salary"  
FROM EMPLOYEE  
GROUP BY country WITH ROLLUP;  
SELECT COALESCE(country, 'GRAND TOTAL' ) AS country, SUM(salary) AS "Total Salary"  
FROM EMPLOYEE  
GROUP BY ROLLUP (country); 
```
## Result:
Therefore we have successfully implemented ROLLUP function.
