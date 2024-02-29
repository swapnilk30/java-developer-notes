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

# Creating MAVEN Project for hibernate and Adding dependencies
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