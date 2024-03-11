## Marker Interface ?
## Various ways to create object ?
1. By Using new Keyword
Employee emp = new Employee();

## String Constant Pool ?

## Can We Override static method ?
- static methods cannot be overridden.
- When a method is declared as static, it belongs to the class itself rather than to instances of the class. Therefore, it is associated with the class's type, not with any particular instance.
- Subclasses can declare static methods with the same signature as a static method in the parent class, but it's considered hiding rather than overriding.
- it won't be considered overriding because the method called will depend on the reference type, not the actual object type.

```java
class Parent {
    static void staticMethod() {
        System.out.println("Parent's static method");
    }
}

class Child extends Parent {
    static void staticMethod() {
        System.out.println("Child's static method");
    }
}

public class Main {
    public static void main(String[] args) {
        Parent.staticMethod(); // Output: Parent's static method
        Child.staticMethod();  // Output: Child's static method

        // However, hiding is not dynamic polymorphism:
        Parent obj = new Child();
        obj.staticMethod();    // Output: Parent's static method
    }
}

```

## What is a Immutable Class

## How To create Immutable Class
- Make fields private and final:
- Do not provide setter methods: 
- Ensure methods do not modify state:
- Make the class final or use defensive copying:

```java
//Make the class final
final class Student{

    // Make fields private and final:
    final private int id;
    final private String name;
    final private List<String> hobbies;

    // provide Getter methods

    public getHobbies(){

    }

    // provide Setter methods

    //parametersed Constructor
    public Student(int id,String name,List<String> hobbies){
        this.id = id;
        this.name = name;
        this.hobbies = hobbies;
    }

    // toString 

}
```

## How to iterate Map
```java

Map<Integer, String> map = new HashMap<>();
map.put(1, "One");
map.put(2, "Two");
map.put(3, "Three");

// Iterating using forEach and lambda expression
map.forEach((key, value) -> {
    System.out.println("Key: " + key + ", Value: " + value);
});

// Iterating using entrySet() and forEach() method
map.entrySet().forEach(entry -> {
    System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());
});

// Get the iterator for the entry set
Iterator<Map.Entry<Integer, String>> iterator = map.entrySet().iterator();

// Iterate through the map using the iterator
while (iterator.hasNext()) {
    Map.Entry<Integer, String> entry = iterator.next();
    System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());

// Iterate through the map using forEach loop
for (Map.Entry<Integer, String> entry : map.entrySet()) {
    System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());
}

// Get the iterator for the key set
Iterator<Integer> iterator = map.keySet().iterator();

// Iterate through the keys using the iterator
while (iterator.hasNext()) {
    Integer key = iterator.next();
    String value = map.get(key);
    System.out.println("Key: " + key + ", Value: " + value);
}
```

## ConcurrentModificationException
- occurs when you try to modify a collection (like a List, Set, or Map) while iterating over it with an iterator, and another thread modifies the same collection concurrently.

```java
List<String> list = new ArrayList<>();
list.add("one");
list.add("two");
list.add("three");

for (String s : list) {
    if (s.equals("two")) {
        list.remove(s); // This will throw ConcurrentModificationException
    }
}

```
> To avoid this exception, you can use an iterator explicitly and its remove() method, or use thread-safe collections such as ConcurrentHashMap, CopyOnWriteArrayList, etc., depending on your concurrency requirements. Alternatively, you can synchronize the code properly to avoid concurrent modifications.

- Use Iterator's remove() method: Instead of directly modifying the collection while iterating over it, use the iterator's remove() method. This approach is the safest when removing elements from a collection during iteration.
```java
List<String> list = new ArrayList<>();
list.add("one");
list.add("two");
list.add("three");

Iterator<String> iterator = list.iterator();
while (iterator.hasNext()) {
    String s = iterator.next();
    if (s.equals("two")) {
        iterator.remove(); // Safe removal
    }
}

```
- Use Synchronized Collections: Wrap your collection with Collections.synchronizedList(), Collections.synchronizedSet(), or Collections.synchronizedMap(). This will make the collection thread-safe, preventing concurrent modifications.
```java
List<String> list = Collections.synchronizedList(new ArrayList<>());

```
- Use Concurrent Collections: Use thread-safe collections provided in the java.util.concurrent package, such as CopyOnWriteArrayList, ConcurrentHashMap, etc. These collections are designed for concurrent access.
```java
List<String> list = new CopyOnWriteArrayList<>();

```
- Synchronize the Access: If you prefer to use traditional collections, you can synchronize access to the collection explicitly. However, this might reduce concurrency and performance.
```java
List<String> list = new ArrayList<>();

synchronized (list) {
    // Access or modify the list here
}

```
## DELETE and TRUNCATE commands

## syntax of a LEFT OUTER JOIN

```sql

SELECT column1, column2, ...
FROM table1
LEFT OUTER JOIN table2 ON table1.column_name = table2.column_name;

```
## some popular Java application servers:
- IBM WebSphere Application Server: WebSphere is a commercial Java EE application server developed by IBM. It provides a scalable and reliable platform for deploying mission-critical enterprise applications.
- Oracle WebLogic Server: WebLogic Server is another commercial Java EE application server developed by Oracle. It offers high-performance clustering, security, and management capabilities for enterprise applications.
- JBoss EAP (Enterprise Application Platform): JBoss EAP is a commercially supported distribution of WildFly developed by Red Hat. It provides additional features and support options for enterprise customers.
- Apache Tomcat: Although commonly referred to as a web server, Tomcat also functions as a lightweight Java application server. It supports servlets, JavaServer Pages (JSP), JavaServer Faces (JSF), and other Java EE technologies.

## Debugging a Java application deployed on an application server like WebLogic or WebSphere using Eclipse IDE involves a few steps. Here's a general guide:
```
Debugging a Java application deployed on an application server like WebLogic or WebSphere using Eclipse IDE involves a few steps. Here's a general guide:

Configure the Application Server:

Set up your application server within Eclipse. This usually involves adding the server runtime environment to Eclipse's preferences.
Configure the server settings such as hostname, port, and deployment directories.
Deploy Your Application:

Deploy your application to the application server. This could involve packaging your application as a WAR (Web Archive) or EAR (Enterprise Archive) file and deploying it using the server's administration console or command-line tools.
Set Up Debugging Configuration:

In Eclipse, create a new debug configuration by going to "Run" > "Debug Configurations".
Select "Remote Java Application" and click "New Configuration".
Enter a name for your configuration and select the project containing your code.
Specify the host and port for remote debugging. This should match the host and port of your application server's debug settings.
Start the Application Server in Debug Mode:

Start your application server in debug mode. This usually involves adding JVM parameters to enable remote debugging. For example, for WebLogic, you might add -Xdebug -Xrunjdwp:transport=dt_socket,address=8000,server=y,suspend=n to the server's startup script.
Start Debugging:

Click "Debug" in your Eclipse debug configuration.
Eclipse will connect to the remote JVM running on your application server.
Set breakpoints in your code where you want to pause execution.
As your application runs, it will pause at breakpoints, allowing you to inspect variables, step through code, and diagnose issues.
Monitor Debugging Output:

Eclipse will display debugging output in the Debug perspective. You can see the stack trace, variable values, and other debugging information here.
Stop Debugging:

When you've finished debugging, terminate the debug session either by clicking the "Terminate" button in the Debug perspective or by stopping the server.
Keep in mind that specific configurations might vary depending on the application server you're using. Always refer to the documentation for your application server and Eclipse for detailed instructions.
```
## prime number program - 
```java
public class MyClass {
    public static boolean isPrime(int number) {
        if (number <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(number); i++) {
            if (number % i == 0) {
                return false;
            }
        }
        return true;
    }

    public static void main(String[] args) {
        int num = 17;
        System.out.println(num + " is prime? " + isPrime(num));
    }
}

```
## Java 8 Features

### Functional Interface : A functional interface is an interface that contains only one abstract method.
- it can contain any number of default or static methods.
- The primary purpose of functional interfaces is to enable the use of lambda expressions, which are anonymous functions that can be passed around as arguments to methods or stored in variables. Lambda expressions provide a concise way to express instances of functional interfaces.
- Java provides some built-in functional interfaces in the java.util.function package, such as:
1. Predicate<T>: Represents a predicate (boolean-valued function) of one argument. It has a single method test(T t) that returns a boolean.
2. Function<T, R>: Represents a function that accepts one argument of type T and produces a result of type R. It has a single method apply(T t).
3. Consumer<T>: Represents an operation that accepts a single input argument of type T and returns no result. It has a single method accept(T t).
4. Supplier<T>: Represents a supplier of results, producing a result of type T. It has a single method get().

## filter employee data having name starts with s
- To filter employee data where the names start with 'S', you can use the Predicate functional interface along with lambda expressions. Here's how you can achieve that in Java:
```java
import java.util.ArrayList;
import java.util.List;
import java.util.function.Predicate;

class Employee {
    private String name;
    private int age;
    // other fields and methods

    public Employee(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    // other getter and setter methods
}

public class Main {
    public static void main(String[] args) {
        List<Employee> employees = new ArrayList<>();
        employees.add(new Employee("John", 30));
        employees.add(new Employee("Sarah", 25));
        employees.add(new Employee("Michael", 35));
        employees.add(new Employee("Samantha", 28));

        // Define a Predicate to filter employees whose name starts with 'S'
        Predicate<Employee> startsWithS = employee -> employee.getName().startsWith("S");

        // Filter the employee data
        List<Employee> filteredEmployees = filterEmployees(employees, startsWithS);

        // Print the filtered employees
        System.out.println("Employees whose name starts with 'S':");
        for (Employee emp : filteredEmployees) {
            System.out.println(emp.getName());
        }
    }

    // Method to filter employees based on the given Predicate
    public static List<Employee> filterEmployees(List<Employee> employees, Predicate<Employee> predicate) {
        List<Employee> filteredList = new ArrayList<>();
        for (Employee employee : employees) {
            if (predicate.test(employee)) {
                filteredList.add(employee);
            }
        }
        return filteredList;
    }
}

```
## Stream API, intermediate and terminal operations play crucial roles in processing streams of data.
```
Intermediate Operations:

Intermediate operations are operations that are executed on a stream before a terminal operation is applied.
They transform the elements of the stream into another stream or perform some other intermediate processing.
Examples of intermediate operations include map(), filter(), sorted(), distinct(), limit(), and flatMap().
These operations are typically lazy, meaning they don't process the entire stream until a terminal operation is invoked.
Terminal Operations:

Terminal operations are operations that produce a result or a side effect.
They trigger the processing of the stream and produce a final result or perform some action.
Examples of terminal operations include forEach(), collect(), reduce(), count(), min(), max(), anyMatch(), allMatch(), and noneMatch().
Once a terminal operation is executed, the stream is consumed, and it cannot be reused.
Here's a simple example to illustrate these concepts:
```
```java
List<String> names = Arrays.asList("John", "Alice", "Bob", "Charlie");

// Intermediate operation: filter names starting with 'A'
Stream<String> filteredStream = names.stream().filter(name -> name.startsWith("A"));

// Intermediate operation: convert names to uppercase
Stream<String> uppercaseStream = filteredStream.map(String::toUpperCase);

// Terminal operation: print each name in uppercase
uppercaseStream.forEach(System.out::println);

```
## example of how you can find the second highest salary using Java 8 streams:
```java
import java.util.Arrays;
import java.util.Comparator;
import java.util.List;

public class SecondHighestSalary {
    public static void main(String[] args) {
        List<Integer> salaries = Arrays.asList(10000, 5000, 8000, 15000, 12000);

        Integer secondHighestSalary = salaries.stream()
                .distinct() // Remove duplicates if any
                .sorted(Comparator.reverseOrder()) // Sort in descending order
                .skip(1) // Skip the first highest salary
                .findFirst() // Get the first element, which is the second highest salary
                .orElseThrow(() -> new RuntimeException("No second highest salary found"));

        System.out.println("Second highest salary: " + secondHighestSalary);
    }
}

```
```java
import java.util.Arrays;
import java.util.Comparator;
import java.util.List;

class Employee {
    private String name;
    private int salary;

    public Employee(String name, int salary) {
        this.name = name;
        this.salary = salary;
    }

    public String getName() {
        return name;
    }

    public int getSalary() {
        return salary;
    }
}

public class SecondHighestSalary {
    public static void main(String[] args) {
        List<Employee> employees = Arrays.asList(
                new Employee("Alice", 10000),
                new Employee("Bob", 5000),
                new Employee("Charlie", 8000),
                new Employee("David", 15000),
                new Employee("Emily", 12000)
        );

        Integer secondHighestSalary = employees.stream()
                .map(Employee::getSalary) // Extract salaries
                .distinct() // Remove duplicates if any
                .sorted(Comparator.reverseOrder()) // Sort in descending order
                .skip(1) // Skip the first highest salary
                .findFirst() // Get the first element, which is the second highest salary
                .orElseThrow(() -> new RuntimeException("No second highest salary found"));

        System.out.println("Second highest salary: " + secondHighestSalary);
    }
}

```
## Comparable vs comparator
## OOps Concept

## count the occurrences of a character in a string using Java 8 streams.
```java
import java.util.stream.IntStream;

public class Main {
    public static void main(String[] args) {
        String str = "hello";
        char targetChar = 'l';

        long count = str.chars()
                       .filter(ch -> ch == targetChar)
                       .count();

        System.out.println("Number of occurrences of '" + targetChar + "' in the string: " + count);
    }
}

```
## 
##
##
##
##




## Armstrong Number program
https://www.youtube.com/watch?v=GxtEs1sRjv4

## Java 8 Arrays Programming
https://www.youtube.com/watch?v=RynqGUbgw9k&t=434s











### Project Details 
|||
|---|---|
|Project|Maven|
|Language|Java|
|Spring Boot|2.7.6|
|Java|17|
|Packaging|Jar|

### Dependencies 
- Spring Web 
- Spring Data JPA 
- MySQL Driver
- Lombok
- Spring Boot DevTools
- Spring Security

## Transaction Management in Spring boot
- @Transactional | @EnableTransactionManagement
- Types of Transaction Propagation

https://www.youtube.com/watch?v=CokAkwI5U3s
https://www.youtube.com/watch?v=b7Pev6i8fso
https://www.youtube.com/watch?v=GqpQ3J40Op8

## How to Implement Pagination in Spring Boot
https://www.youtube.com/watch?v=IwNPHoXZCWA

## Spring Boot with H2 Database

### Maven Dependencies

- To use H2 in the Spring boot application, we need to add the H2 runtime jar into dependencies. The best way to add is through Maven. The version is maintained by Spring Boot’s BOM file, so we can skip it.

```
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>

<dependency>
  <groupId>com.h2database</groupId>
  <artifactId>h2</artifactId>
  <scope>runtime</scope>
</dependency>
```
### H2 DataSource Configuration
- Spring provides effortless configuration options to connect to any database using properties. Below are the configuration properties, we shall have in application.properties file for the most straightforward H2 configuration.

- Please note by default, spring boot configures H2 database connection with the username 'sa' and an empty password. If you wish to change the username and password, override them in the above properties options.

```
# application.properties

spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=

spring.jpa.database-platform=org.hibernate.dialect.H2Dialect

spring.h2.console.enabled=true
spring.h2.console.path=/h2-console
spring.h2.console.settings.trace=false
```
## Spring Boot with MySQL Database