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


