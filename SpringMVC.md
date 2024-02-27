
# Spring MVC

### What is Spring MVC ?
1. A Spring MVC is sub Framework which is used to build a **web application**.
2. It is build on the top of **Servlet API**.
3. It follows the **Model-View-Controller** design pattern.
4. It implements all the basic features of core spring framework like **Inversion of Control, Dependency Injection.**

### Why Spring MVC ?
1. Separate each role model,view,controller etc.
2. Powerfull configuration.
3. It is sub framework of Spring Framework. Use of Spring core features like IOC etc.
4. Rapid application development.
5. Spring MVC is flexible , easy to test and much features.
6. Spring MVC is highly flexible and can be integrated with various view technologies, such as JSP, Thymeleaf, FreeMarker, etc. 
7. It also supports validation, data binding, internationalization, and other features to simplify web application development.

### MVC Design Pattern.
    MVC design pattern - way of organize the code in our application

- **Model**: Represents the data and business logic of the application. It encapsulates the application's data and behavior, providing services to access and manipulate this data.

- **View**: Represents the presentation layer of the application. It is responsible for rendering the user interface and presenting data to the user in a format that is easy to understand and interact with.

- **Controller**: Acts as an intermediary between the model and the view. It handles user requests, processes input, and updates the model accordingly. It also selects the appropriate view to display the response to the user.

# Spring MVC Interview Questions

### What is the front controller class of Spring MVC?
- The **DispatcherServlet** class works as the front controller in Spring MVC.


---



### Creating a Spring MVC (Model-View-Controller) project involves several steps.

1. Setup Java Development Environment:
```
Make sure you have Java Development Kit (JDK) installed on your system.

Install an IDE like IntelliJ IDEA, Eclipse, or Spring Tool Suite (STS) for easier development.
```
2. Download and Configure Tomcat with Eclipse

3. Create a New Maven Project:

```
Maven is a popular build automation tool used in Java projects. Most Spring projects use Maven for dependency management.

In your IDE, create a new Maven project and choose the appropriate archetype for a web application.

For Spring MVC, you might use maven-archetype-webapp or maven-archetype-webapp-jee5.
```
4. Add Spring Dependencies:
- Add Spring MVC dependencies to your pom.xml file. These dependencies include spring-webmvc, spring-context, spring-web, etc.
- Ensure you specify the appropriate version of Spring framework compatible with your project.
```
<!-- https://mvnrepository.com/artifact/org.springframework/spring-webmvc -->
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-webmvc</artifactId>
    <version>5.2.4.RELEASE</version>
</dependency>


<!-- https://mvnrepository.com/artifact/org.springframework/spring-orm -->
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-orm</artifactId>
    <version>5.2.4.RELEASE</version>
</dependency>


<!-- https://mvnrepository.com/artifact/org.hibernate/hibernate-core -->
<dependency>
    <groupId>org.hibernate</groupId>
    <artifactId>hibernate-core</artifactId>
    <version>5.2.4.Final</version>
</dependency>

<!-- https://mvnrepository.com/artifact/mysql/mysql-connector-java -->
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>5.1.3</version>
</dependency>

```
5. Configure Dispatcher Servlet:
- In the web.xml file (located in the WEB-INF directory), configure the Spring Dispatcher Servlet.
- This servlet is the entry point for all requests in a Spring MVC application.
- Define a servlet mapping for the Dispatcher Servlet and specify the URL patterns it should handle.
```
<web-app>
	<display-name>Archetype Created Web Application</display-name>
	<!-- Configure dispatcher servlet -->
	<servlet>
		<servlet-name>spring</servlet-name>
		<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
	</servlet>

	<servlet-mapping>
		<servlet-name>spring</servlet-name>
		<url-pattern>/</url-pattern> <!-- URL pattern to map all requests -->
	</servlet-mapping>
</web-app>
```
6. Create Spring Configuration File:
```
create xml file in "WEB-INF" folder and file named as "spring-servlet.xml"
```
**spring-servlet.xml**
```
<!-- Spring MVC Configuration -->
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:mvc="http://www.springframework.org/schema/mvc"
    xmlns:context="http://www.springframework.org/schema/context"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/mvc
        http://www.springframework.org/schema/mvc/spring-mvc.xsd
        http://www.springframework.org/schema/context
        http://www.springframework.org/schema/context/spring-context.xsd">

    <!-- Component scanning for controller classes -->
    <context:component-scan base-package="com.example.controllers" />

    <!-- View resolver configuration -->
    <bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
        <property name="prefix" value="/WEB-INF/views/" />
        <property name="suffix" value=".jsp" />
    </bean>

    <!-- Other configurations such as interceptors, validators, etc. -->

</beans>

```

7. Create Controller Classes:
- Create your controller classes and annotate them with **@Controller** or other specialized annotations provided by Spring MVC.




