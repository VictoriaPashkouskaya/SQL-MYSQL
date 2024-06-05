mysql> CREATE DATABASE my_company_database;
Query OK, 1 row affected (0.00 sec)

mysql> USE my_company_database;
Database changed
mysql> CREATE TABLE employees (
    ->     id INT AUTO_INCREMENT PRIMARY KEY,
    ->     birth_date DATE,
    ->     first_name VARCHAR(50),
    ->     last_name VARCHAR(50),
    ->     gender CHAR(1)
    -> );
Query OK, 0 rows affected (0.05 sec)

mysql> ALTER TABLE employees
    -> ADD COLUMN salary DECIMAL(10, 2),
    -> ADD COLUMN title VARCHAR(50),
    -> ADD COLUMN title_date DATE;
Query OK, 0 rows affected (0.04 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> INSERT INTO employees (birth_date, first_name, last_name, gender, salary, title, title_date)
    -> VALUES
    -> ('1980-01-01', 'John', 'Doe', 'M', 45000.00, 'Manager', '2020-01-15'),
    
    -> ('1985-05-20', 'Jane', 'Smith', 'F', 38000.00, 'Engineer', '2020-03-22'),
    
    -> ('1990-07-15', 'John', 'Davis', 'M', 52000.00, 'Director', '2019-11-01'),
    
    -> ('1978-11-23', 'Alice', 'Brown', 'F', 15000.00, 'Technician', '2021-05-05'),
    
    -> ('1983-03-30', 'Michael', 'Johnson', 'M', 10000.00, 'Intern', '2021-07-12'),
    -> ('1995-09-17', 'John', 'Wilson', 'M', 22000.00, 'Clerk', '2020-10-25'),
    -> ('1982-02-02', 'Emily', 'Moore', 'F', 7000.00, 'Assistant', '2018-12-15'),
    -> ('1991-06-12', 'Sophia', 'Taylor', 'F', 5000.00, 'Secretary', '2020-04-17'),
    -> ('1987-08-08', 'Chris', 'Anderson', 'M', 13000.00, 'HR', '2017-09-01'),
    -> ('1994-12-21', 'Matthew', 'Thomas', 'M', 30000.00, 'Sales', '2020-01-11'),
    -> ('1989-01-31', 'David', 'Jackson', 'M', 27000.00, 'Developer', '2019-03-03'),
    -> ('1976-10-10', 'Sarah', 'White', 'F', 45000.00, 'Manager', '2016-08-21'),
    -> ('1993-11-16', 'James', 'Harris', 'M', 25000.00, 'Designer', '2019-12-14'),
    -> ('1992-04-24', 'Laura', 'Martin', 'F', 16000.00, 'PR', '2020-06-30'),
    -> ('1997-07-07', 'Robert', 'Thompson', 'M', 5000.00, 'Intern', '2021-03-20');
Query OK, 15 rows affected (0.02 sec)
Records: 15  Duplicates: 0  Warnings: 0

mysql> UPDATE employees
    -> SET first_name = 'Jonathan'
    -> WHERE first_name = 'John' AND last_name = 'Wilson' AND birth_date = '1995-09-17';
Query OK, 1 row affected (0.02 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> SELECT * FROM employees WHERE salary > 20000;

+----+------------+------------+-----------+--------+----------+-----------+------------+
| id | birth_date | first_name | last_name | gender | salary   | title     | title_date |
+----+------------+------------+-----------+--------+----------+-----------+------------+
|  1 | 1980-01-01 | John       | Doe       | M      | 45000.00 | Manager   | 2020-01-15 |
|  2 | 1985-05-20 | Jane       | Smith     | F      | 38000.00 | Engineer  | 2020-03-22 |
|  3 | 1990-07-15 | John       | Davis     | M      | 52000.00 | Director  | 2019-11-01 |
|  6 | 1995-09-17 | Jonathan   | Wilson    | M      | 22000.00 | Clerk     | 2020-10-25 |
| 10 | 1994-12-21 | Matthew    | Thomas    | M      | 30000.00 | Sales     | 2020-01-11 |
| 11 | 1989-01-31 | David      | Jackson   | M      | 27000.00 | Developer | 2019-03-03 |
| 12 | 1976-10-10 | Sarah      | White     | F      | 45000.00 | Manager   | 2016-08-21 |
| 13 | 1993-11-16 | James      | Harris    | M      | 25000.00 | Designer  | 2019-12-14 |
+----+------------+------------+-----------+--------+----------+-----------+------------+


mysql> SELECT * FROM employees WHERE salary < 10000;

+----+------------+------------+-----------+--------+---------+-----------+------------+
| id | birth_date | first_name | last_name | gender | salary  | title     | title_date |
+----+------------+------------+-----------+--------+---------+-----------+------------+
|  7 | 1982-02-02 | Emily      | Moore     | F      | 7000.00 | Assistant | 2018-12-15 |
|  8 | 1991-06-12 | Sophia     | Taylor    | F      | 5000.00 | Secretary | 2020-04-17 |
| 15 | 1997-07-07 | Robert     | Thompson  | M      | 5000.00 | Intern    | 2021-03-20 |
+----+------------+------------+-----------+--------+---------+-----------+------------+
3 rows in set (0.01 sec)

mysql> SELECT COUNT(*) FROM employees;
+----------+
| COUNT(*) |
+----------+
|       15 |
+----------+
1 row in set (0.01 sec)

mysql> SELECT UPPER(first_name) FROM employees;
+-------------------+
| UPPER(first_name) |
+-------------------+
| JOHN              |
| JANE              |
| JOHN              |
| ALICE             |
| MICHAEL           |
| JONATHAN          |
| EMILY             |
| SOPHIA            |
| CHRIS             |
| MATTHEW           |
| DAVID             |
| SARAH             |
| JAMES             |
| LAURA             |
| ROBERT            |
+-------------------+
15 rows in set (0.01 sec)

mysql> DELETE FROM employees WHERE id = 5;
Query OK, 1 row affected (0.01 sec)

mysql> DELETE FROM employees WHERE salary > 20000;
Query OK, 8 rows affected (0.01 sec)

mysql>
