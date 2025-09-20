This repository contains basic SQL commands to work with databases and tables. These commands are useful for beginners learning how to manage databases using SQL.

---

## 1. Show All Databases

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
