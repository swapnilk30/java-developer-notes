```
- What is Immutable object.
- How To create Immutable Class.

```

# What is Immutable object ?
- Once we Created an object, we can not change the values of its instance variables.
- No inheritance.

### How to Change values of instance variable ?
```java
List<String> hobbyList = new ArrayList<>();
hobbyList.add("Swimming");

// Here We Have Created new Object
Student s = new Student(1,"Swapnil",hobbyList);

// 1. Using objects passed in constructor
hobbyList.add("Cricket");
// 2. Using Setter methods
s.setName("Rahul");
// 3. Using getter methods
List<String> list = s.getHobbies();
list.add("new Hobby");
```

## How To create Immutable Class
- Make fields private and final:
- Do not provide setter methods: 
- Ensure methods do not modify state:
- Make the class final or use defensive copying:

```java
//Make the class final
final class Student {
	
	// Make fields private and final:
	final private int id;
	final private String name;
	final private List<String> hobbies;
	
	public int getId() {
		return id;
	}
	public String getName() {
		return name;
	}
	
	public List<String> getHobbies() {
		List<String> newList = new ArrayList<String>();
		for(String h:hobbies) {
			newList.add(h);
		}
		return newList;
	}
	
	// remove Setter Methods
	
	public Student(int id, String name, List<String> hobby) {
		super();
		this.id = id;
		this.name = name;
		// Fixing Constructor Problem
		this.hobbies = new ArrayList<String>();
		for(String h:hobby) {
			hobbies.add(h);	
		}	
	}
}
```
```java
public class StudentTest {
	
	public static void main(String[] args) {
		
		List<String> list = new ArrayList<String>();
		
		list.add("Swimming");
		
		Student s = new Student(1, "Swapnil",list );	
	}
}
```



- Jdbc
- Hibernate
- Spring
- SpringMVC
- SpringBoot
- MySQL




```
- Core Java FAQ: Frequently Asked Interview Questions and Answers for Java Developers
https://www.youtube.com/watch?v=07_Vvi_bi6Y

- TOP 25 Java Exception Handling Interview Questions & Answers
https://www.youtube.com/watch?v=uo0CLK3z9Rs&t=14s

- TOP 100+ Spring Boot & Microservices Interview Questions and Answers
https://www.youtube.com/watch?v=cZYJHIgmGaY&list=RDCMUCqCGL2oiIC4sLi1A1n6xHiA&index=4

- Real-Time Spring Boot Interview Questions and Answers [All In One Video]
https://www.youtube.com/watch?v=XilRv9wJhzc

- Java multi threading | Session - 01 | Ashok IT
https://www.youtube.com/watch?v=TXek1PaNmWE&t=88s

- Top 25 Java Multi Threading Interview Questions & Answers | Ashok IT
https://www.youtube.com/watch?v=wE0FPmq63P4


- Five Different Ways to Create Objects in Java 
https://www.youtube.com/watch?v=XAM9GwH1bNI

- Spring boot - Conditional annotation with examples
https://www.youtube.com/watch?v=ApUtROI5bAg&t=95s

- Spring MVC Introduction 
https://www.youtube.com/watch?v=R3XlwImkFe0

- Spring MVC Architecture Explanation
https://www.youtube.com/watch?v=7dr4fOEgM1c

- Spring MVC Tutorial Step by Step
https://www.youtube.com/playlist?list=PL0zysOflRCelAb51IrexpUSeB0dpr9p6g

- 
https://www.interviewbit.com/spring-boot-interview-questions/
```

```

```

```
- What are the key Advantages of spring boot over spring
- can you explain concept of DI in Spring and why it is beneficial
- What is role of @SpringBootApplication Annotation
- How Spring boot achive Auto-Configuration with example.(dataSource Example)
- What are the steps to Override a specific AutoConfiguration.(application.properties)
- What annotation used to create restful services in spring boot.(@RestController )
- How handle exception in spring boot rest aplications
- approach to secure end points
https://www.youtube.com/watch?v=0QhyHQh0avE
```

```
- @RequestMapping
- Difference Between @Restcontroller and @Controller
- @ResponseBody
- @SpringBootApplication(@SpringBootConfiguration @EnableAutoConfiguration @ComponentScan)
- @Autowired
- @Qualifier
- @Blob

- @RestControllerAdvice
- @ExceptionHandler
- @ResponseStatus
```

```
SWAGGER
LOGGING
```

```
- When to use HTTP POST instead of GET to retrieve data?
https://www.youtube.com/watch?v=fS8QY7BiDaQ

- Hibernate N+1 Problem Solution
https://www.youtube.com/watch?v=Txb0YlEVLds
```

```


-how memory management or Garbage collection works in java?

Garbage collection
    Java provides automatic memory management through a program called Garbage collector.
    "Remove objects that are not used anymore."
    live object = reacheable (referenced by someone else)
    dead object = unreachable (not referenced from anywhere)
    Garbage collection is carried out by a daemon thread called "Garbage collector"
    we can not force gc to happen (System.gc())

Create an Object without ‘new’ Keyword



Differences between Abstraction and Encapsulation
Differences between Interface and Abstract Class


realtime example of final class provided by java?
A real-time example of a final class in Java is the java.lang.String class,
which is a final class and cannot be extended by any other class.
This is because the String class is complete in nature and cannot be modified

What is public static void main(String[] args) ?
public - this method is accessible from outside the class.
static - No object is required to call the main method.
void - this method does not return any value.
main - Special method name to start the java program execution.
String[] args - the arguments passed while running the program.

Can we change the order of public , static , and void keywords ?
Yes can change the order of public and static keywords , but void should come just before the method name.

Method Overloading
                public class Calculator{

                    // By changing the number of parameters
                    
                    public int add(int a, int b){
                        return a+b;
                    }

                    public int add(int a , int b , int c){
                        return a+b+c;
                    }

                    // By changing the data types of parameters

                    public double add(double a,double b){
                        return a+b;
                    }

                }

                public class CalculatorTest{

                    public static void main(String[] args){

                        Calculator calculator = new Calculator();

                        int result1 = calculator.add(10,20);

                        System.out.println("Addition of Two numbers : " + result);

                        int result2 = calculator.add(10,20,30);

                        System.out.println("Addition of Three numbers : "+ result2);

                        double result3 = calculator.add(10.0,20.0);

                        System.out.println("Addition of Two Double Numbers : "+ result3);

                    }

                }

            
Abstract Class And Interface
                Abstraction-
                It is the process of hiding the certain details and showing the important information
                to the end user called as “Abstraction”. Or
                Abstraction is a process of hiding the implementation details and showing only functionality
                to the user.

                How to achieve Abstraction in Java?
                There are two ways to achieve or implement abstraction in java program. They are as follows:
                Abstract class (0 to 100%)
                Interface (100%)
            
what will happen if we write final keyword with abstarct class?
If you declare a class abstract, to use it, you must extend it and if you declare a class final you cannot extend it,
since both contradict with each other you cannot declare a class both abstract and final
if you do so a compile time error will be generated.

Can We Start Thread Twice ?
No. You can not start thread twice
This will result in a IllegalThreadStateException


                public class StartTwice{
                    public static void main(String[] args){
                        Thread t = new Thread();
                        t.start();
                        t.start();
                    }

                }
            
What methods thread use to communicate with each other ?
Thread use wait(), notify(), and notifyAll() to communicate with each other.

Why Strings are Immutable or final in Java ?
1. Immutable String or Object that can not be modified once it is created. But We can only change the reference to the object.
2. The String is immutable in java because of the security,synchronization and concurrency ,caching and class loading.

Why java provided with String Constant Pool as we can store the objects in heap memory ?
String Constant Pool provides the facility of reusability of the existing string object.
When a new string object is created using the string literals ,then JVM first checks in the pool if this string already exists or not.
if it exists ,then it will reference the existing string rather than creating a new object.
this will help in the speeding up of the application and also helps in saving the memory as no two objects will have the same content.

Why abstract class has constructor even though we cannot create object?
We cannot create an object of abstract class but we can create an object of subclass of abstract class.
When we create an object of subclass of an abstract class, it calls the constructor of subclass.
This subclass constructor has super in the first line that calls constructor of an abstract class.
Thus, the constructors of an abstract class are used from constructor of its subclass.
If the abstract class doesn’t have a constructor, a class that extends that abstract class will not get compiled.

How to create immutable class.






----------------------
### Serialization task :
-perform serialization and deserialiazation on Employee
Employee{
    int id;
    String name;
    transient double salary;
}
----------------------
How to serialize objects and save to file
https://www.youtube.com/watch?v=b-KLxooxih4&t=1116s
```

```
- create pdf using pdfbox java library | create pdf in java | read write pdf in java |
https://www.youtube.com/watch?v=qCBgymqbJtA
```

```
Why we can't use this inside static context?
https://www.youtube.com/watch?v=z5AJ4NK4HpY&list=PLVlQHNRLflP-exWR9yw_Xp29Ctek_GQTG
How to create immutable class
https://www.youtube.com/watch?v=TXV0_JhP8pY

```

```
What is Upcasting in Java
https://www.youtube.com/watch?v=9ry63PeSl1E
What is Downcasting in Java
https://www.youtube.com/watch?v=tiWY-rB86EA
```