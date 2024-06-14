
```
Frequently Asked Core Java Interview Questions For Freshers
https://www.youtube.com/watch?v=AfpuuGUBTIQ&t=672s
```


# COLLECTION FRAMEWORK


### HashMap

```
- How Custom Java Object will be used as key in HashMap.
https://www.youtube.com/watch?v=626jyt0yN4M

- How to Iterate Map in Java Example
- 5 Best Ways to Iterate Over HashMap in Java
    1. Iterate through a HashMap EntrySet using Iterator
    2. Iterate through HashMap KeySet using Iterator
    3. Iterate HashMap using For-Each Loop
    4. Iterating through a HashMap using Lambda Expressions
    5. Loop through a HashMap using Stream Api
```

### equals()
- it checks the equality of two objects.
- it compares the key, whether they are equal or not.
- it is a method of the Object Class. It can be Overridden.
- If you Override the equals() , then it is mandatory to override the hashCode().

### hashcode()
- This is the method of Object Class.
- It returns the hashcode value of the object in integer form.
- The value received from the method is used as bucket number(index).
- The bucket number (index) is the address of the element inside the map.
- HashCode of null Key is 0.

```
obj1.equals(obj2) is true
then 
obj1.hashCode() == obj2.hashCode() must be true.
if not they can be behave very weirdly.
```

### What is the contract between equals() and hashCode().
- if two objects are equal according to the equal() then the hashcode for both the objects must be same.
- it is not necessary that if we have same hashcode for two objects which means those two objects are equal.(This is collision. Better hash function can prevent this.)
- when ever it is invoked on the same object more than once during an execution of java application,the hashcode method must consistently return the same integer.

### Internal Working of HashMap.
1. When we initialize a HashMap , the bucket or Array is initialized.
2. When we call put(key,value) method to insert the content.
3. It will first check whether the key is null or not, if the key is null it calls putForNullKey() which returns index 0, which is always reserved for null key, hashcode for null is zero.
4. if key is not null then it calculates the hashcode of key.
5. After calculation the hashcode of the key , it calls indexfor() by passing the hashcode of the key and length of the table array.
- this method returns the index of the array for that particular key value pair.
- index  = hashCode(key) & (n-1).
6. **After getting the index** , it checks all key present in the linked list at that index using **equals()** if the key is already present in the linked list it **replaces the old value with new value**.
7. if the key is not present in the linked list it appends the specified key value pair at the end of the linked list
8. when the calculated index value is same for two or more keys the collision is resolved by linked list the entry class has an attribute next this attribute always points to the next object in the chain.


### LinkedHashMap
### ConcurrentHashMap
### HashTable
### TreeMap

### What is Immutable object ?
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

### How To create Immutable Class
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


```
- Difference between Volatile & Synchronized - Java
https://www.youtube.com/watch?v=R9MqDY2SxbA
```
# 

```
What is Upcasting in Java
https://www.youtube.com/watch?v=9ry63PeSl1E

What is Downcasting in Java
https://www.youtube.com/watch?v=tiWY-rB86EA

```

```
### Which collections you used in your project?
```

```
Why we can't use this inside static context?
https://www.youtube.com/watch?v=z5AJ4NK4HpY&list=PLVlQHNRLflP-exWR9yw_Xp29Ctek_GQTG

How to create immutable class
https://www.youtube.com/watch?v=TXV0_JhP8pY

```
```
create pdf using pdfbox java library | create pdf in java | read write pdf in java |
https://www.youtube.com/watch?v=qCBgymqbJtA
```

```
- When to use HTTP POST instead of GET to retrieve data?
https://www.youtube.com/watch?v=fS8QY7BiDaQ

```

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

```
```
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
Differences between Abstraction and Encapsulation
Differences between Interface and Abstract Class
```
```


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
Understand Volatile Keyword in Java
https://www.youtube.com/watch?v=7cRo6UVm1PQ
```
