```
Common examples of Hibernate dialects include:

org.hibernate.dialect.MySQLDialect for MySQL
org.hibernate.dialect.OracleDialect for Oracle
org.hibernate.dialect.SQLServerDialect for Microsoft SQL Server
org.hibernate.dialect.PostgreSQLDialect for PostgreSQL
```
```
- Hibernate Caching
https://www.youtube.com/watch?v=zxgvN-Qs4DU&t=1s
```
### Hibernate Caching
- Hibernate caching is a mechanism provided by the Hibernate ORM (Object-Relational Mapping) framework to improve application performance by reducing the number of database queries.

- Hibernate provides several levels of caching:
    - First-level cache
    - Second-level cache
    - Query cache

    
```
- Hibernate N+1 Problem Solution
https://www.youtube.com/watch?v=Txb0YlEVLds
```


## Why we need maven
- No need to add jar files manually.
- We can directly add the dependency.

## What is Hibernate?
- Hibernate is an open-source and lightweight ORM tool that is used to store, manipulate, and retrieve data from the database.

## What is ORM?
- ORM is an acronym for Object/Relational mapping. It is a programming strategy to map object with the data stored in the database. It simplifies data creation, data manipulation, and data access.
## Explain hibernate architecture?
## What are the core interfaces of Hibernate?
```
The core interfaces of Hibernate framework are:

Configuration
SessionFactory
Session
Query
Criteria
Transaction
```
## Mention some of the advantages of using ORM over JDBC.
```
ORM has the following advantages over JDBC:

Application development is fast.
Management of transaction.
Generates key automatically.
Details of SQL queries are hidden.
```
## Define criteria in terms of Hibernate.
```
The objects of criteria are used for the creation and execution of the object-oriented criteria queries.
```
## List some of the databases supported by Hibernate.
```
Some of the databases supported by Hibernate are:

DB2
MySQL
Oracle
Sybase SQL Server
Informix Dynamic Server
HSQL
PostgreSQL
FrontBase
```
## List the key components of Hibernate.
```
Key components of Hibernate are:

Configuration
Session
SessionFactory
Criteria
Query
Transaction
```
## Mention two components of Hibernate configuration object.
```
Database Connection

Class Mapping Setup
```
## How is SQL query created in Hibernate?
```
The SQL query is created with the help of the following syntax:

Session.createSQLQuery
```
## What does HQL stand for?
```
Hibernate Query Language
```
## How is HQL query created?
```
The HQL query is created with the help of the following syntax:

Session.createQuery
```
## How can we add criteria to a SQL query?
```
A criterion is added to a SQL query by using the Session.createCriteria.
```
## Define persistent classes.
```
Classes whose objects are stored in a database table are called as persistent classes.
```
## What is persistence?
## What are some of the advantages of Hibernate?
## What is HQL?
## What are some databases that are supported by Hibernate?
## What are three key association mappings in Hibernate?
## What is a one-to-one association?
## How would you create a one-to-one mapping solution in Hibernate?
## What is a one-to-many association?
## How would you create a one-to-many mapping solution in Hibernate?
## What is a many-to-many association?
## What are some major Hibernate interfaces?
## What is a Hibernate Session, and how do you create one?
## How can you make an immutable class in Hibernate?
## What are the three states of a Hibernate object?

```
https://www.codecademy.com/resources/blog/hibernate-interview-questions/
https://www.javatpoint.com/hibernate-interview-questions
```

## which mapping is used in your project?perform on notepad?

# JDBC
### JDBC provides three statements.
1. Statement : java.sql.Statement
2. PreparedStatement : java.sql.PreparedStatement
- `(?)` placeholders to replace it with the actual values.
3. CallableStatement : java.sql.CallableStatement

# Hibernate Framework

### ORM
### JPA 
- it is a Specification that defines how to persist data in java application.

### Hibernate features :
- ORM 
- DatabaseIndependence
- Automatic table generation
- Caching
- query langauge - HQL is similar to sql
- Transactions
- lazy loading

# Creating MAVEN Project for hibernate and Adding dependencies (Eclipse)
- To create a Maven project for Hibernate and add the necessary dependencies, you can follow these steps:
1. Create Maven Project:
2. Add Hibernate Dependencies: 
- Open the **pom.xml** file in your project and add the Hibernate dependencies within the `<dependencies>` tag.

```xml
    <!-- Hibernate Core -->
    <dependency>
        <groupId>org.hibernate</groupId>
        <artifactId>hibernate-core</artifactId>
        <version>5.5.7.Final</version> <!-- Use the latest version -->
    </dependency>


    <!-- JDBC Driver (choose the one for your database, e.g., MySQL, PostgreSQL) -->
    <!-- Example for MySQL -->
    <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>8.0.27</version> <!-- Use the latest version -->
    </dependency>
```
3. Hibernate Configuration:
- This configuration file will be used to store database connection information and schema level settings.
- Create a hibernate.cfg.xml file in the **src/main/resources** directory with your database connection details and **entity mappings**.
- **hibernate.cfg.xml**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE hibernate-configuration PUBLIC
"-//Hibernate/Hibernate Configuration DTD 3.0//EN"
"http://hibernate.sourceforge.net/hibernate-configuration-3.0.dtd">

<hibernate-configuration>
	<session-factory>

        <!-- Database connection settings -->
		<property name="connection.driver_class">com.mysql.jdbc.Driver</property>
		<property name="connection.url">jdbc:mysql://localhost:3306/hibernatedb</property>
		<property name="connection.username">root</property>
		<property name="connection.password">root</property>

         <!-- Hibernate dialect -->
		<property name="dialect">org.hibernate.dialect.MySQL8Dialect</property>
        
		<property name="hbm2ddl.auto">update</property>
		<property name="show_sql">true</property>

	</session-factory>
</hibernate-configuration>
```

```
Basics Commonly used Hibernate Annotations
@Entity -used to mark class as Entity.
@Table - used to change table details.
@Id - use to mark column as id (primary key)
@GeneratedValue - hibernate automatically generate values for that using an internal sequence. Therefore we dont have to set it manually.
@Column - used to specify column mappings.to change the column name in the associated table in database.
@OneToOne
@OneToMany
@JoinColumn
@Transient - this tells hibernate not to save this field in database

            @Entity
            @Table(name = "products")
            public class Product{

                @Id
                private String productId;

                @Column(name ="title")
                private String title;
                
                @Column(length = 1000)
                private String description;
                
                private double price;
                
                @Transient
                private double discount;
                
                private boolean live;
            }

        
```


```
• Step-1 : Create maven project.
• Step-2 : Add the dependency in pom.xml file
• -hibernate-core
• -mysql-connector-java
• Step-3 : Add the pojo class – Employee class
• Step-4 : Add the hibernate annotations to pojo class
• Step-5 : Add the hibernate.cfg.xml file
```
