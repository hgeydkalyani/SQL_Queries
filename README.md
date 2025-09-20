This repository contains basic SQL commands to work with databases and tables. These commands are useful for beginners learning how to manage databases using SQL.

---

# 1. Show All Databases

To list all databases in your MySQL server:

```1
SHOW DATABASES;
---Example
+--------------------+
| Database           |
+--------------------+
| collagedb          |
| demo               |
| demo1              |
| employee           |
| hotel&tourism      |
| hoteltourism       |
| information_schema |
| kiran              |
| mysql              |
| performance_schema |
| periodtacker       |
| sys                |
+--------------------+


2.Select a Database
```2
To select a specific database to work with:
USE demo1;
---Example
 use demo1;
Database changed


3. Show All Tables

To display all tables in the current database:

SHOW TABLES;
---Example
 show tables;
+-----------------+
| Tables_in_demo1 |
+-----------------+
| department      |
| employee        |
| employee1       |
| employees       |
+-----------------+

4. Describe Table Structure

To see the structure of a table, including column names, types, and constraints:

DESC employee1;
---Example
 DESC employee1;
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| name       | varchar(20) | YES  |     | NULL    |       |
| id         | int         | YES  |     | NULL    |       |
| age        | int         | YES  |     | NULL    |       |
| email      | varchar(50) | YES  |     | NULL    |       |
| phoneNo    | bigint      | YES  |     | NULL    |       |
| gender     | varchar(40) | YES  |     | NULL    |       |
| state      | varchar(50) | YES  |     | NULL    |       |
| country    | varchar(50) | YES  |     | NULL    |       |
| address    | varchar(50) | YES  |     | NULL    |       |
| department | varchar(50) | YES  |     | NULL    |       |
| role       | varchar(50) | YES  |     | NULL    |       |
| exp        | int         | YES  |     | NULL    |       |
| sal        | bigint      | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+

#2-create-table

INSERT INTO employee1 (id, name, age, email, phoneNo, gender, state, country, address, department, role, exp, sal)
VALUES (1, 'Kalyani Wasane', 22, 'kalyani@123.com', 9876543210, 'Female', 'MP', 'India', 'Indore', 'IT', 'Developer', 1, 25000.00);
(2, 'Ravi Kumar', 28, 'ravi@123.com', 9876543211, 'Male', 'MH', 'India', 'Mumbai', 'HR', 'Manager', 5, 45000.00),
(3, 'Anjali Singh', 32, 'anjali@123.com', 9876543212, 'Female', 'UP', 'India', 'Lucknow', 'Finance', 'Analyst', 7, 55000.00),
(4, 'Suresh Patil', 26, 'suresh@123.com', 9876543213, 'Male', 'MH', 'India', 'Pune', 'IT', 'Developer', 3, 30000.00),
(5, 'Priya Sharma', 30, 'priya@123.com', 9876543214, 'Female', 'DL', 'India', 'Delhi', 'Marketing', 'Executive', 6, 40000.00),
(6, 'Amit Verma', 35, 'amit@123.com', 9876543215, 'Male', 'UP', 'India', 'Kanpur', 'Finance', 'Manager', 10, 65000.00),
(7, 'Sneha Joshi', 24, 'sneha@123.com', 9876543216, 'Female', 'MP', 'India', 'Bhopal', 'IT', 'Tester', 2, 28000.00),
(8, 'Rohan Mehta', 29, 'rohan@123.com', 9876543217, 'Male', 'MH', 'India', 'Nagpur', 'Marketing', 'Coordinator', 4, 35000.00),
(9, 'Pooja Dixit', 27, 'pooja@123.com', 9876543218, 'Female', 'DL', 'India', 'Delhi', 'HR', 'Executive', 3, 37000.00),
(10, 'Vikram Singh', 33, 'vikram@123.com', 9876543219, 'Male', 'MP', 'India', 'Indore', 'IT', 'Team Lead', 8, 60000.00),
(11, 'Neha Gupta', 25, 'neha@123.com', 9876543220, 'Female', 'MH', 'India', 'Mumbai', 'Finance', 'Analyst', 2, 32000.00);


#4 Select (Retrieve Data)
-- All records
SELECT * FROM employee1;

--example
 SELECT * FROM employee1;

mysql> SELECT * FROM employee1;
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+-------------+------+---------+
| name           | id   | age  | email           | phoneNo    | gender | state | country | address | department | role        | exp  | sal     |
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+-------------+------+---------+
| kalyani wasane |   12 |   54 | sham@123.com    | 9876543212 | Female | MH    | india   | pimpri  | enginer    | software    |    2 | 9000000 |
| Kalyani Wasane |    1 |   22 | kalyani@123.com | 9876543210 | Female | MP    | India   | Indore  | IT         | Developer   |    1 |   25000 |
| Ravi Kumar     |    2 |   28 | ravi@123.com    | 9876543211 | Male   | MH    | India   | Mumbai  | HR         | Manager     |    5 |   45000 |
| Anjali Singh   |    3 |   32 | anjali@123.com  | 9876543212 | Female | UP    | India   | Lucknow | Finance    | Analyst     |    7 |   55000 |
| Suresh Patil   |    4 |   26 | suresh@123.com  | 9876543213 | Male   | MH    | India   | Pune    | IT         | Developer   |    3 |   30000 |
| Priya Sharma   |    5 |   30 | priya@123.com   | 9876543214 | Female | DL    | India   | Delhi   | Marketing  | Executive   |    6 |   40000 |
| Amit Verma     |    6 |   35 | amit@123.com    | 9876543215 | Male   | UP    | India   | Kanpur  | Finance    | Manager     |   10 |   65000 |
| Sneha Joshi    |    7 |   24 | sneha@123.com   | 9876543216 | Female | MP    | India   | Bhopal  | IT         | Tester      |    2 |   28000 |
| Rohan Mehta    |    8 |   29 | rohan@123.com   | 9876543217 | Male   | MH    | India   | Nagpur  | Marketing  | Coordinator |    4 |   35000 |
| Pooja Dixit    |    9 |   27 | pooja@123.com   | 9876543218 | Female | DL    | India   | Delhi   | HR         | Executive   |    3 |   37000 |
| Vikram Singh   |   10 |   33 | vikram@123.com  | 9876543219 | Male   | MP    | India   | Indore  | IT         | Team Lead   |    8 |   60000 |
| Neha Gupta     |   11 |   25 | neha@123.com    | 9876543220 | Female | MH    | India   | Mumbai  | Finance    | Analyst     |    2 |   32000 |
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+-------------+------+---------+



-- Specific columns
SELECT name, email, sal FROM employee1;
--example
mysql> SELECT name, email, sal FROM employee1;
+----------------+-----------------+---------+
| name           | email           | sal     |
+----------------+-----------------+---------+
| kalyani wasane | sham@123.com    | 9000000 |
| Kalyani Wasane | kalyani@123.com |   25000 |
| Ravi Kumar     | ravi@123.com    |   45000 |
| Anjali Singh   | anjali@123.com  |   55000 |
| Suresh Patil   | suresh@123.com  |   30000 |
| Priya Sharma   | priya@123.com   |   40000 |
| Amit Verma     | amit@123.com    |   65000 |
| Sneha Joshi    | sneha@123.com   |   28000 |
| Rohan Mehta    | rohan@123.com   |   35000 |
| Pooja Dixit    | pooja@123.com   |   37000 |
| Vikram Singh   | vikram@123.com  |   60000 |
| Neha Gupta     | neha@123.com    |   32000 |
+----------------+-----------------+---------+


-- With condition
SELECT * FROM employee1 WHERE state = 'MP';
--example
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+-----------+------+-------+
| name           | id   | age  | email           | phoneNo    | gender | state | country | address | department | role      | exp  | sal   |
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+-----------+------+-------+
| Kalyani Wasane |    1 |   22 | kalyani@123.com | 9876543210 | Female | MP    | India   | Indore  | IT         | Developer |    1 | 25000 |
| Sneha Joshi    |    7 |   24 | sneha@123.com   | 9876543216 | Female | MP    | India   | Bhopal  | IT         | Tester    |    2 | 28000 |
| Vikram Singh   |   10 |   33 | vikram@123.com  | 9876543219 | Male   | MP    | India   | Indore  | IT         | Team Lead |    8 | 60000 |
+----------------+------+------+-----------------+------------+--

-- With sorting
SELECT * FROM employee1 ORDER BY sal DESC;
--example
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+-------------+------+---------+
| name           | id   | age  | email           | phoneNo    | gender | state | country | address | department | role        | exp  | sal     |
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+-------------+------+---------+
| kalyani wasane |   12 |   54 | sham@123.com    | 9876543212 | Female | MH    | india   | pimpri  | enginer    | software    |    2 | 9000000 |
| Amit Verma     |    6 |   35 | amit@123.com    | 9876543215 | Male   | UP    | India   | Kanpur  | Finance    | Manager     |   10 |   65000 |
| Vikram Singh   |   10 |   33 | vikram@123.com  | 9876543219 | Male   | MP    | India   | Indore  | IT         | Team Lead   |    8 |   60000 |
| Anjali Singh   |    3 |   32 | anjali@123.com  | 9876543212 | Female | UP    | India   | Lucknow | Finance    | Analyst     |    7 |   55000 |
| Ravi Kumar     |    2 |   28 | ravi@123.com    | 9876543211 | Male   | MH    | India   | Mumbai  | HR         | Manager     |    5 |   45000 |
| Priya Sharma   |    5 |   30 | priya@123.com   | 9876543214 | Female | DL    | India   | Delhi   | Marketing  | Executive   |    6 |   40000 |
| Pooja Dixit    |    9 |   27 | pooja@123.com   | 9876543218 | Female | DL    | India   | Delhi   | HR         | Executive   |    3 |   37000 |
| Rohan Mehta    |    8 |   29 | rohan@123.com   | 9876543217 | Male   | MH    | India   | Nagpur  | Marketing  | Coordinator |    4 |   35000 |
| Neha Gupta     |   11 |   25 | neha@123.com    | 9876543220 | Female | MH    | India   | Mumbai  | Finance    | Analyst     |    2 |   32000 |
| Suresh Patil   |    4 |   26 | suresh@123.com  | 9876543213 | Male   | MH    | India   | Pune    | IT         | Developer   |    3 |   30000 |
| Sneha Joshi    |    7 |   24 | sneha@123.com   | 9876543216 | Female | MP    | India   | Bhopal  | IT         | Tester      |    2 |   28000 |
| Kalyani Wasane |    1 |   22 | kalyani@123.com | 9876543210 | Female | MP    | India   | Indore  | IT         | Developer   |    1 |   25000 |
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+-------------+------+---------+

#5 Update Data
UPDATE employee1
SET sal = 30000, role = 'Senior Developer'
WHERE id = 1;


# 6 Filtering with WHERE
SELECT * FROM employee1 WHERE age > 25;
--example
+----------------+------+------+----------------+------------+--------+-------+---------+---------+------------+-------------+------+---------+
| name           | id   | age  | email          | phoneNo    | gender | state | country | address | department | role        | exp  | sal     |
+----------------+------+------+----------------+------------+--------+-------+---------+---------+------------+-------------+------+---------+
| kalyani wasane |   12 |   54 | sham@123.com   | 9876543212 | Female | MH    | india   | pimpri  | enginer    | software    |    2 | 9000000 |
| Ravi Kumar     |    2 |   28 | ravi@123.com   | 9876543211 | Male   | MH    | India   | Mumbai  | HR         | Manager     |    5 |   45000 |
| Anjali Singh   |    3 |   32 | anjali@123.com | 9876543212 | Female | UP    | India   | Lucknow | Finance    | Analyst     |    7 |   55000 |
| Suresh Patil   |    4 |   26 | suresh@123.com | 9876543213 | Male   | MH    | India   | Pune    | IT         | Developer   |    3 |   30000 |
| Priya Sharma   |    5 |   30 | priya@123.com  | 9876543214 | Female | DL    | India   | Delhi   | Marketing  | Executive   |    6 |   40000 |
| Amit Verma     |    6 |   35 | amit@123.com   | 9876543215 | Male   | UP    | India   | Kanpur  | Finance    | Manager     |   10 |   65000 |
| Rohan Mehta    |    8 |   29 | rohan@123.com  | 9876543217 | Male   | MH    | India   | Nagpur  | Marketing  | Coordinator |    4 |   35000 |
| Pooja Dixit    |    9 |   27 | pooja@123.com  | 9876543218 | Female | DL    | India   | Delhi   | HR         | Executive   |    3 |   37000 |
| Vikram Singh   |   10 |   33 | vikram@123.com | 9876543219 | Male   | MP    | India   | Indore  | IT         | Team Lead   |    8 |   60000 |
+----------------+------+------+----------------+------------+--------+-------+---------+---------+------------+-------------+------+---------+

SELECT * FROM employee1 WHERE sal BETWEEN 20000 AND 50000;
--example
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+------------------+------+-------+
| name           | id   | age  | email           | phoneNo    | gender | state | country | address | department | role             | exp  | sal   |
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+------------------+------+-------+
| Kalyani Wasane |    1 |   22 | kalyani@123.com | 9876543210 | Female | MP    | India   | Indore  | IT         | Senior Developer |    1 | 30000 |
| Ravi Kumar     |    2 |   28 | ravi@123.com    | 9876543211 | Male   | MH    | India   | Mumbai  | HR         | Manager          |    5 | 45000 |
| Suresh Patil   |    4 |   26 | suresh@123.com  | 9876543213 | Male   | MH    | India   | Pune    | IT         | Developer        |    3 | 30000 |
| Priya Sharma   |    5 |   30 | priya@123.com   | 9876543214 | Female | DL    | India   | Delhi   | Marketing  | Executive        |    6 | 40000 |
| Sneha Joshi    |    7 |   24 | sneha@123.com   | 9876543216 | Female | MP    | India   | Bhopal  | IT         | Tester           |    2 | 28000 |
| Rohan Mehta    |    8 |   29 | rohan@123.com   | 9876543217 | Male   | MH    | India   | Nagpur  | Marketing  | Coordinator      |    4 | 35000 |
| Pooja Dixit    |    9 |   27 | pooja@123.com   | 9876543218 | Female | DL    | India   | Delhi   | HR         | Executive        |    3 | 37000 |
| Neha Gupta     |   11 |   25 | neha@123.com    | 9876543220 | Female | MH    | India   | Mumbai  | Finance    | Analyst          |    2 | 32000 |
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+------------------+------+-------+


SELECT * FROM employee1 WHERE state IN ('MP', 'MH', 'UP');
--example
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+------------------+------+---------+
| name           | id   | age  | email           | phoneNo    | gender | state | country | address | department | role             | exp  | sal     |
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+------------------+------+---------+
| kalyani wasane |   12 |   54 | sham@123.com    | 9876543212 | Female | MH    | india   | pimpri  | enginer    | software         |    2 | 9000000 |
| Kalyani Wasane |    1 |   22 | kalyani@123.com | 9876543210 | Female | MP    | India   | Indore  | IT         | Senior Developer |    1 |   30000 |
| Ravi Kumar     |    2 |   28 | ravi@123.com    | 9876543211 | Male   | MH    | India   | Mumbai  | HR         | Manager          |    5 |   45000 |
| Anjali Singh   |    3 |   32 | anjali@123.com  | 9876543212 | Female | UP    | India   | Lucknow | Finance    | Analyst          |    7 |   55000 |
| Suresh Patil   |    4 |   26 | suresh@123.com  | 9876543213 | Male   | MH    | India   | Pune    | IT         | Developer        |    3 |   30000 |
| Amit Verma     |    6 |   35 | amit@123.com    | 9876543215 | Male   | UP    | India   | Kanpur  | Finance    | Manager          |   10 |   65000 |
| Sneha Joshi    |    7 |   24 | sneha@123.com   | 9876543216 | Female | MP    | India   | Bhopal  | IT         | Tester           |    2 |   28000 |
| Rohan Mehta    |    8 |   29 | rohan@123.com   | 9876543217 | Male   | MH    | India   | Nagpur  | Marketing  | Coordinator      |    4 |   35000 |
| Vikram Singh   |   10 |   33 | vikram@123.com  | 9876543219 | Male   | MP    | India   | Indore  | IT         | Team Lead        |    8 |   60000 |
| Neha Gupta     |   11 |   25 | neha@123.com    | 9876543220 | Female | MH    | India   | Mumbai  | Finance    | Analyst          |    2 |   32000 |
+----------------+------+------+-----------------+------------+--------+----

SELECT * FROM employee1 WHERE name LIKE 'K%';  -- starts with K
--example

+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+------------------+------+---------+
| kalyani wasane |   12 |   54 | sham@123.com    | 9876543212 | Female | MH    | india   | pimpri  | enginer    | software         |    2 | 9000000 |
| Kalyani Wasane |    1 |   22 | kalyani@123.com | 9876543210 | Female | MP    | India   | Indore  | IT         | Senior Developer |    1 |   30000 |
+----------------+------+------+-----------------+------------+--------+-------+---------+---------+------------+------------------+------+-----

#8. Aggregate Functions
SELECT COUNT(*) FROM employee1;      -- number of rows
--example
       SELECT COUNT(*) FROM employee1;
+----------+
| COUNT(*) |
+----------+
|       12 |
+----------+

SELECT MAX(sal) FROM employee1;      -- highest salary
--example
mysql> SELECT MAX(sal) FROM employee1;
+----------+
| MAX(sal) |
+----------+
|  9000000 |
+----------+

SELECT MIN(sal) FROM employee1;      -- lowest salary
--example
mysql> SELECT MIN(sal) FROM employee1;
+----------+
| MIN(sal) |
+----------+
|    28000 |
+----------+

SELECT AVG(sal) FROM employee1;      -- average salary
--example
mysql> SELECT AVG(sal) FROM employee1;
+-------------+
| AVG(sal)    |
+-------------+
| 788083.3333 |
+-------------+

SELECT SUM(sal) FROM employee1;      -- total salary
--example

mysql> SELECT SUM(sal) FROM employee1;
+----------+
| SUM(sal) |
+----------+
|  9457000 |
+----------+

#9. Group By & Having
-- Average salary by department
SELECT department, AVG(sal) AS avg_salary
FROM employee1
GROUP BY department;
--example
mysql> SELECT department, AVG(sal) AS avg_salary
    -> FROM employee1
    -> GROUP BY department;
+------------+--------------+
| department | avg_salary   |
+------------+--------------+
| enginer    | 9000000.0000 |
| IT         |   37000.0000 |
| HR         |   41000.0000 |
| Finance    |   50666.6667 |
| Marketing  |   37500.0000 |
+------------+--------------+

-- Departments with avg salary > 30000
SELECT department, AVG(sal) AS avg_salary
FROM employee1
GROUP BY department
HAVING AVG(sal) > 30000;
--example
mysql> SELECT department, AVG(sal) AS avg_salary
    -> FROM employee1
    -> GROUP BY department
    -> HAVING AVG(sal) > 30000;
+------------+--------------+
| department | avg_salary   |
+------------+--------------+
| enginer    | 9000000.0000 |
| IT         |   37000.0000 |
| HR         |   41000.0000 |
| Finance    |   50666.6667 |
| Marketing  |   37500.0000 |
+------------+--------------+
