# MYSQL


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


