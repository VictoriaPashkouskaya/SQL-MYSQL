# Proyecto de Base de Datos de Mi Empresa

## Objetivos del Proyecto
- Entender qué es una base de datos relacional.
- Comprender cómo realizar consultas a una base de datos.
- Aprender a interactuar con los datos almacenados en la base de datos.

## Pasos para Realizar el Proyecto

### 1. Creación de la Base de Datos

#### 1.1. Creación de la Base de Datos y la Tabla

1. Conéctese a su servidor de base de datos MySQL utilizando un cliente como MySQL Workbench o el terminal.
2. Cree la base de datos `my_company_database`:
    ```sql
    CREATE DATABASE my_company_database;
    ```
3. Cambie a la nueva base de datos:
    ```sql
    USE my_company_database;
    ```
4. Cree la tabla `employees` con los campos indicados:
    ```sql
    CREATE TABLE employees (
        id INT AUTO_INCREMENT PRIMARY KEY,
        birth_date DATE,
        first_name VARCHAR(50),
        last_name VARCHAR(50),
        gender CHAR(1)
    );
    ```

#### 1.2. Añadir Nuevas Columnas

5. Añada nuevas columnas a la tabla `employees`:
    ```sql
    ALTER TABLE employees
    ADD COLUMN salary DECIMAL(10, 2),
    ADD COLUMN title VARCHAR(50),
    ADD COLUMN title_date DATE;
    ```

### 2. Ejecución de Consultas SQL

#### 2.1. Insertar Datos

6. Inserte al menos 15 nuevos empleados:
    ```sql
    INSERT INTO employees (birth_date, first_name, last_name, gender, salary, title, title_date)
    VALUES
    ('1980-01-01', 'John', 'Doe', 'M', 45000.00, 'Manager', '2020-01-15'),
    ('1985-05-20', 'Jane', 'Smith', 'F', 38000.00, 'Engineer', '2020-03-22'),
    ('1990-07-15', 'John', 'Davis', 'M', 52000.00, 'Director', '2019-11-01'),
    ('1978-11-23', 'Alice', 'Brown', 'F', 15000.00, 'Technician', '2021-05-05'),
    ('1983-03-30', 'Michael', 'Johnson', 'M', 10000.00, 'Intern', '2021-07-12'),
    ('1995-09-17', 'John', 'Wilson', 'M', 22000.00, 'Clerk', '2020-10-25'),
    ('1982-02-02', 'Emily', 'Moore', 'F', 7000.00, 'Assistant', '2018-12-15'),
    ('1991-06-12', 'Sophia', 'Taylor', 'F', 5000.00, 'Secretary', '2020-04-17'),
    ('1987-08-08', 'Chris', 'Anderson', 'M', 13000.00, 'HR', '2017-09-01'),
    ('1994-12-21', 'Matthew', 'Thomas', 'M', 30000.00, 'Sales', '2020-01-11'),
    ('1989-01-31', 'David', 'Jackson', 'M', 27000.00, 'Developer', '2019-03-03'),
    ('1976-10-10', 'Sarah', 'White', 'F', 45000.00, 'Manager', '2016-08-21'),
    ('1993-11-16', 'James', 'Harris', 'M', 25000.00, 'Designer', '2019-12-14'),
    ('1992-04-24', 'Laura', 'Martin', 'F', 16000.00, 'PR', '2020-06-30'),
    ('1997-07-07', 'Robert', 'Thompson', 'M', 5000.00, 'Intern', '2021-03-20');
    ```

#### 2.2. Actualizar Datos

7. Actualice el nombre de un empleado específico:
    ```sql
    UPDATE employees
    SET first_name = 'Jonathan'
    WHERE first_name = 'John' AND last_name = 'Wilson' AND birth_date = '1995-09-17';
    ```

#### 2.3. Obtener Datos

8. Seleccione empleados con un salario superior a 20,000:
    ```sql
    SELECT * FROM employees WHERE salary > 20000;
    ```

9. Seleccione empleados con un salario inferior a 10,000:
    ```sql
    SELECT * FROM employees WHERE salary < 10000;
    ```

10. Seleccione empleados con un salario entre 14,000 y 50,000:
    ```sql
    SELECT * FROM employees WHERE salary BETWEEN 14000 AND 50000;
    ```

11. Seleccione el número total de empleados:
    ```sql
    SELECT COUNT(*) FROM employees;
    ```

12. Seleccione los títulos del año 2019:
    ```sql
    SELECT title FROM employees WHERE YEAR(title_date) = 2019;
    ```

13. Seleccione solo los nombres de los empleados en mayúsculas:
    ```sql
    SELECT UPPER(first_name) FROM employees;
    ```

14. Seleccione nombres únicos de empleados:
    ```sql
    SELECT DISTINCT first_name FROM employees;
    ```

#### 2.4. Borrar Datos

15. Elimine al empleado con id = 5:
    ```sql
    DELETE FROM employees WHERE id = 5;
    ```

16. Elimine a todos los empleados con un salario superior a 20,000:
    ```sql
    DELETE FROM employees WHERE salary > 20000;
    ```

## Conclusión

Siguiendo estos pasos, podrá crear y gestionar una base de datos relacional básica, realizar consultas SQL y gestionar datos en la tabla. Esto le ayudará a comprender mejor el trabajo con bases de datos y mejorar sus habilidades en SQL.


mysql> DELETE FROM employees WHERE salary > 20000;
Query OK, 8 rows affected (0.01 sec)

mysql>
