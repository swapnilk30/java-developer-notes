
--- MYSQL---

## What is diff between primary and unique key
## What is trigger

## write sql query to to fetch all data from specific column?
## write SQL query to get name starts with "a"
## write SQL query to get unique name from table
## How to move data from one table to another table
## Sql query to Update empname based on empid.



## To fetch only the first 10 records from a MySQL database, you can use the `LIMIT` clause in your SQL query.
    Here's an example query:
```sql
SELECT * FROM your_table_name LIMIT 10;
```
## To retrieve the last 10 records from a MySQL database, you can combine the `ORDER BY` and `LIMIT` clauses in your SQL query.
    Here's an example query:
```sql
SELECT * FROM your_table_name ORDER BY id DESC LIMIT 10;
```

# MYSQL

## What is a PRIMARY KEY ?

    The PRIMARY KEY constraint uniquely identifies each record in a table.
    Primary keys must contain UNIQUE values, and cannot contain NULL values.

    A table can not have more than one primary key.

    Rules for defining primary key:
        -two rows cant have the same primary key value.
        -the primary key field cannot be null.
        -the value in a primary key column can never be 
            modified or updated if any foreign key refers to that primary key.
        
## What is the FOREIGN KEY ?

    FOREIGN KEY is a column that creates a relationship between two tables.
    
    A FOREIGN KEY is a field (or collection of fields) in one table, that refers to the PRIMARY KEY in another table.

### create table
    CREATE TABLE employee(id int primary key, city varchar(255));

### add column
    ALTER TABLE employee ADD name varchar(255)

### modify column
    ALTER TABLE employee MODIFY name varchar(200)

### rename column 
    ALTER TABLE employee RENAME COLUMN name TO fullName

    note: RENAME COLUMN works from mysql 8

### drop column
    ALTER TABLE employee DROP COLUMN city


### 

    Write a SQL Query to find the name of the department where more than two employees are working.

    Write a SQL Query to calculate the average salary of each department which is higher than 75000. find department name also in descending order.

    Write a SQL Query to find the manager and employee who belongs to same city.

    Write a SQL Query to find those employee whose salary exists between 35000 and 90000 with the department and manager name 


```sql
CREATE TABLE Employee (    
    id INT PRIMARY KEY,    
    name VARCHAR(45),
    email VARCHAR(45),
    manager_id INT,
   country VARCHAR(45),	      
);
```



## DELETE
- To **delete all** the rows of the table :

```sql
DELETE FROM table_name;
```
- To delete the row of the table under some condtion :

```sql
DELETE FROM table_name WHERE condition;
```
## DROP

## TRUNCATE
- To truncate a table;

```sql
TRUNCATE table table_name;

TRUNCATE table_name;
```


## INDEX
- Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.

> Note: Updating a table with indexes takes more time than updating a table without (because the indexes also need an update). So, only create indexes on columns that will be frequently searched against.

```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);

CREATE UNIQUE INDEX index_name
ON table_name (column1, column2, ...);

CREATE INDEX idx_lastname
ON Persons (LastName);

CREATE INDEX idx_pname
ON Persons (LastName, FirstName);

ALTER TABLE table_name
DROP INDEX index_name;
```

## VIEW
- In SQL, a view is a virtual table based on the result-set of an SQL statement.
- A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.
- You can add SQL statements and functions to a view and present the data as if the data were coming from one single table.

```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
> Note: A view always shows up-to-date data! The database engine recreates the view, every time a user queries it.

- The following SQL creates a view that shows all customers from Brazil:
```sql
CREATE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName
FROM Customers
WHERE Country = 'Brazil';
```
- We can query the view above as follows:
```sql
SELECT * FROM [Brazil Customers];
```



# Create Employee and Department Table
```sql

CREATE TABLE Department (
    DeptID INT PRIMARY KEY,
    DeptName VARCHAR(50) NOT NULL,
    Location VARCHAR(100)
);


CREATE TABLE Employee (
    EmpID INT PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    DeptID INT,
    Salary DECIMAL(10,2), -- Assuming salary is stored as a decimal value
    FOREIGN KEY (DeptID) REFERENCES Department(DeptID)
);


-- Inserting data into the Department table
INSERT INTO Department (DeptID, DeptName, Location) VALUES
(1, 'Finance', 'New York'),
(2, 'Human Resources', 'Los Angeles'),
(3, 'Marketing', 'Chicago');

-- Inserting data into the Employee table
INSERT INTO Employee (EmpID, FirstName, LastName, DeptID, Salary) VALUES
(1, 'John', 'Doe', 1, 60000.00),
(2, 'Jane', 'Smith', 2, 55000.00),
(3, 'Michael', 'Johnson', 3, 62000.00),
(4, 'Emily', 'Brown', 1, 58000.00),
(5, 'David', 'Wilson', 3, 63000.00);


-- Inserting more data into the Department table
INSERT INTO Department (DeptID, DeptName, Location) VALUES
(4, 'Engineering', 'San Francisco'),
(5, 'Operations', 'Seattle');

-- Inserting more data into the Employee table
INSERT INTO Employee (EmpID, FirstName, LastName, DeptID, Salary) VALUES
(6, 'Sarah', 'Miller', 4, 65000.00),
(7, 'Chris', 'Davis', 2, 55000.00),
(8, 'Emma', 'Martinez', 5, 60000.00),
(9, 'James', 'Wilson', 1, 60000.00),
(10, 'Olivia', 'Taylor', 3, 62000.00),
(11, 'William', 'Anderson', 4, 65000.00),
(12, 'Ava', 'Thomas', 5, 58000.00),
(13, 'Liam', 'Hernandez', 3, 62000.00);
```
- To fetch all data from both the Department and Employee tables, you can use a SQL SELECT statement to join the tables together. Here's how you can do it:
```sql
SELECT *
FROM Department
JOIN Employee ON Department.DeptID = Employee.DeptID;

```
- To retrieve the highest salary from the Employee table, you can use the MAX() function.
```sql
SELECT MAX(Salary) AS HighestSalary
FROM Employee;

```
- To get the second-highest salary from the Employee table, you can use a subquery. 
```sql
SELECT MAX(Salary) AS SecondHighestSalary
FROM Employee
WHERE Salary < (SELECT MAX(Salary) FROM Employee);

```
- achieve this without using subqueries by utilizing the LIMIT and OFFSET clauses in combination with the ORDER BY clause. 

```sql
SELECT Salary AS ThirdHighestSalary
FROM Employee
ORDER BY Salary DESC
LIMIT 1 OFFSET 2;

```
- To retrieve the highest salary from each department, you can use the MAX() function along with the GROUP BY clause to group the data by department. 
```sql
SELECT Department.DeptID, Department.DeptName, MAX(Employee.Salary) AS HighestSalary
FROM Department
JOIN Employee ON Department.DeptID = Employee.DeptID
GROUP BY Department.DeptID, Department.DeptName;
```


```
-The ORDER BY keyword is used to sort the result-set in ascending or descending order.
-The HAVING clause was added to SQL because the WHERE keyword cannot be used with aggregate functions.


-What is Primary key and Unique ?
-what is difference between primary key and foreign key

-db queries to find out 3 highest salary

    SELECT name, salary
    FROM employee
    ORDER BY salary DESC
    LIMIT 3;

    SELECT e.name AS employee_name, e.salary, d.name AS department_name
    FROM employee e
    INNER JOIN department d ON e.department_id = d.department_id
    ORDER BY e.salary DESC
    LIMIT 3;


-Query to join table ( employee, department) show department name, salary
    SELECT employee.employee_id, employee.name AS employee_name, department.name AS department_name, employee.salary
    FROM employee
    INNER JOIN department ON employee.department_id = department.department_id;

-Tell a SQL query to find duplicates in a table that doesn't have a primary key.
what is normalization 



4> Write query to find max salary from every dept ?
    SELECT department.name AS department_name, MAX(employee.salary) AS max_salary
    FROM employee
    INNER JOIN department ON employee.department_id = department.department_id
    GROUP BY department.name;

difference between delete truncate and drop
what is stored procedure
Query from select highest salary
Explain groupby clause

-Query for 1st 10 records from the table ?
    
    SELECT * FROM YourTableName LIMIT 10;
    SELECT * FROM YourTableName ORDER BY SomeColumn LIMIT 10;

-Query for top 10 records sort by ascending order age above 30 ?

    SELECT *
    FROM YourTableName
    WHERE Age > 30
    ORDER BY Age ASC
    LIMIT 10;

-Query for unique name of employee ?

    SELECT DISTINCT Name FROM Employees;

-Query to write the all the employees who have age above 30 ?

    SELECT Name
    FROM Employees
    WHERE Age > 30;

-find  max 5 marks from student table ?
    
    SELECT marks
    FROM student
    ORDER BY marks DESC
    LIMIT 5;

-write a SQL Query to find fifth highest salary

    SELECT DISTINCT Salary
    FROM Employee
    ORDER BY Salary DESC
    LIMIT 1 OFFSET 4;
```