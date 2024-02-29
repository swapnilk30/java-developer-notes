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
		<property name="connection.driver_class">com.mysql.jdbc.Driver</property>
		<property name="connection.url">jdbc:mysql://localhost:3306/hibernatedb</property>
		<property name="connection.username">root</property>
		<property name="connection.password">Skmania@1234</property>
		<property name="dialect">org.hibernate.dialect.MySQLDialect</property>
		<property name="hbm2ddl.auto">update</property>
		<property name="show_sql">true</property>
	</session-factory>
</hibernate-configuration>
```