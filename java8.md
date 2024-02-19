
### What is Lambda Expression (λ):

### The Main Objective of Lambda Expression is to bring benefits of functional programming into Java.
    • Lambda Expression is just an anonymous (nameless) function. That means the function which
    doesn’t have the name, return type and access modifiers.
    • Lambda Expression also known as anonymous functions or closures.


# Java 8

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

### What is the Optional class in Java 8?

    The Optional class in Java 8 is a container object that may or may not contain a value.
    It is used to avoid null pointer exceptions.

    If a value is present, isPresent() will return true.
    get() will return the value otherwise throws NoSuchElementException.

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
```java
// Example : Used in project 

@Repository
public interface UserRepository extends JpaRepository<User, String>{

	Optional<User> findByEmail(String username);

}
```
