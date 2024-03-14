#
```
Predefined Functional Interfaces  :

    Predicate 
    Function
    Consumer
    Supplier


Write a program to read the CSV data using Java 8 Stream API and group it by ID and covert into JSON
https://www.youtube.com/watch?v=42UWgTdQwwI

```

# What is Lambda Expression (λ):

### The Main Objective of Lambda Expression is to bring benefits of functional programming into Java.
    • Lambda Expression is just an anonymous (nameless) function. That means the function which
    doesn’t have the name, return type and access modifiers.
    • Lambda Expression also known as anonymous functions or closures.







### find out all the numbers starting with 1 in a list by using Stream API ?

    List<Integer> list = Arrays.asList(20,15,80,11,48,25,98,32,17);

    list.stream().map(s -> s.toString()).filter(s -> s.startsWith("1")).forEach(System.out::println);

### Write a java program to find sum of even numbers and sum of odd numbers in a given list using java 8 streams.
    List<Integer> list = Arrays.asList(3,5,6,8,9);

```java
public class SumOfEvenOdd {
	
	public static void main(String[] args) {
		List<Integer> list = Arrays.asList(3,5,6,8,9);
		
		//filter even numbers and add to list
		List<Integer> listOfEvenNum = list.stream().filter(n -> n % 2 ==0 ).collect(Collectors.toList());
		System.out.println(listOfEvenNum);
		
		int sumOfEvenNumbers = list.stream().filter(n->n%2==0).mapToInt(Integer::intValue).sum();

		System.out.println(sumOfEvenNumbers);
		
		//filter Odd numbers and add to list
		List<Integer> listOfOddNum = list.stream().filter(n->n%2 == 1).collect(Collectors.toList());
		
		System.out.println(listOfOddNum);
		
		int sumOfOddNumbers = list.stream().filter(n->n%2==1).mapToInt(Integer::intValue).sum();
	
		System.out.println(sumOfOddNumbers);
	}
}
```
### How to convert primitive data type arrays to Wrapper arrays in Java.

```java
public class PrimitiveArrayToStream {
	
	public static void main(String[] args) {
		
		//primitive data type array
		int[] arr = {10,20,30,40,60,30,40,50,60,};
		
		IntStream stream = Arrays.stream(arr);
		
		Stream<Integer> boxed = stream.boxed();
		
		//convert to Wrapper Array
		
		Integer[] array = boxed.toArray(Integer[]::new);
		
		System.out.println(Arrays.toString(arr));
		
		//Integer[] array2 = Arrays.stream(arr).boxed().toArray(Integer[] :: new);	
	}
}
```

# What is the Optional class in Java 8?
- The Optional class in Java 8 is a container object that may or may not contain a value.
- **It is used to avoid null pointer exceptions.**
- If a value is present, isPresent() will return true.
- get() will return the value otherwise throws **NoSuchElementException**.

```java
/*you might encounter a Null Pointer Exception when you try to invoke a method or access a field on a variable that is null.
 Null Pointer Exceptions can be common sources of bugs in programs,
 especially if proper null checks are not performed before accessing object references.
*/
public class OptionalExample {
	
	public static void main(String[] args) {
		
		String str = null;
		int length = str.length(); // This line will throw a NullPointerException
	}
}

// To Handle Above NullPointerException we have to Check null using if else 

public class OptionalExample {
	
	public static void main(String[] args) {
		
		String str = null;
		//int length = str.length(); // This line will throw a NullPointerException
	
		if(str == null) {
			System.out.println("this is null object");
		}else {
			System.out.println(str.length());
		}
	}
}
```
#### Handle Using Optional Class
```java
public class OptionalExample {
	
	public static void main(String[] args) {
		
		String str = null;
		//int length = str.length(); // This line will throw a NullPointerException
		
		Optional<String> optional = Optional.ofNullable(str);
		
		System.out.println(optional.isPresent());// false
		
		//System.out.println(optional.get());// Exception in thread "main" java.util.NoSuchElementException: No value present
		
		System.out.println(optional.orElse("No value present"));
	}
}
```

```java
// Example : Used in project 

@Repository
public interface UserRepository extends JpaRepository<User, String>{

	Optional<User> findByEmail(String username);

}


{
	User user = userRepository.findById(userId).orElseThrow(()-> new ResourceNotFoundException("User not found by Given Id !!"));
}
```


# Default Methods
- Until 1.7 version onwards inside interface we can take only public abstract methods and public
static final variables (every method present inside interface is always public and abstract whether
we are declaring or not).
- Every variable declared inside interface is always public static final whether we are declaring or
not.
- But from 1.8 version onwards in addition to these, we can declare default concrete methods also
inside interface, which are also known as defender methods.
- We can declare default method with the keyword “default” as follows
```java

interface MyInterface{

	// Abstract method
    void myMethod();

	// Default method
    default void defaultMethod() {
        System.out.println("This is a default method.");
    }
}
```
- **Interface default methods are by-default available to all implementation classes.**
- Based on requirement implementation class can use these default methods directly or can override.
```java
class MyClass implements MyInterface {
    public void myMethod() {
        System.out.println("Implemented abstract method.");
    }
}

public class Main {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        obj.myMethod(); // Output: Implemented abstract method.
        obj.defaultMethod(); // Output: This is a default method.
    }
}
```
> The main advantage of default methods is without effecting implementation classes we can add
new functionality to the interface (backward compatibility).

### Default method vs multiple inheritance
- Two interfaces can contain default method with same signature then there may be a chance of
ambiguity problem (diamond problem) to the implementation class.
- To overcome this problem **compulsory** we should **override default method in the implementation class** otherwise we get **compile time error.**
- In the implementation class we can provide complete new implementation or we can call any interface method as follows.
- interfacename.super.m1();

```java
// 
interface Left {
	
	default void m1() {
		System.out.println("Left Default Method");
	}
}
// 
interface Right {
	
	default void m1() {
		System.out.println("Right Default Method");
	}
}
// 
class Test implements Left,Right{
	
	public void m1() {
		System.out.println("Test Class Method"); 
		//  Left.super.m1(); Or Right.super.m1()
	}

	public Static void main(String[] args){
		Test test = new Test();
		test.m1();
	}

}
```

> Note: We can’t override object class methods as default methods inside interface otherwise we get
compile time error.
> Reason: Object class methods are by-default available to every Java class hence it’s not required to
bring through default methods.

# Static Methods



# Stream
## What is an Intermediate operation
- The Operations which return another stream as a result are called intermediate operations.
- filter(), map(), distinct(), sorted(), limit(), skip()

https://www.youtube.com/watch?v=PMhrMDHFFW4&t=5s

```java
public class Employee {

	private int id;
	private String name;
	private int age;
	private String dept;
	private double salary;

	// Getter and Setter
	// Default Constructor
	// Parameterised Constructor
	// toString
}
```
- Group By Age (Map < Integer ,List < Employee > > )

```java
Map<Integer,List<Employee>> groupByAge = listOfEmployee.stream().collect(Collectors.groupingBy(emp -> emp.getAge()));
```

- Group By Age (Map < Integer ,Set < Employee > > )
```java
// Here return Map<Ineteger, Set <Employee > > Unique Value by name ,need to overide equals() and Hashcode() in employee by name 
```
- response will be Sorted 
```java
// To Sort here we will use TreeMap is Third Parameter of GroupingBy
collect(Collectors.groupingBy(emp->emp.getAge(),TreeMap::new,Collectors.toSet()));
```

- Sort By Name
```java
List<Employee> sortByName = listOfEmployee.stream().sorted((e1,e2)->e1.getName().compareTo(e2.getName())).collect(Collectors.toList());
```

- Sort By Age
```java
List<Employee> sortByAge = listOfEmployee.stream().sorted(Comparator.comparing(Employee::getAge)).collect(Collectors.toList());
```

https://www.youtube.com/watch?v=1pweZskNq7w
https://www.youtube.com/watch?v=OISIBsuObAw

- find list of employee whose age is between 30 and 40

https://www.youtube.com/watch?v=Ul_7T2WJIuQ&list=RDCMUCORuRdpN2QTCKnsuEaeK-kQ&index=5

- how to sort a Map by its value.

https://www.youtube.com/watch?v=eBDN04LlEOg&t=507s