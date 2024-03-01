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
``