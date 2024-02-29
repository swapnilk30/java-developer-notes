

### Program to find the minimum (or maximum) element of an array
    int a[]={1,423,6,46,34,23,13,53,4}; 
```java
public class MaxAndMinElementArray {
	
	public static void main(String[] args) {
		
		int a[]={1,423,6,46,34,23,13,53,4};
		
		int max = a[0];
		
		for(int i = 1;i<a.length;i++) {
			if(a[i] > max) {
				max = a[i];	
			}
		}
		
		System.out.println(Arrays.toString(a));
		
		System.out.println("Maximum Element is : " + max);
		
		int min = a[0];
		
		for(int i=1 ;i < a.length ; i++) {
			if(a[i] < min) {
				min = a[i];
			}
		}
		System.out.println("Minimum Element is : " + min);	
	}
}
```


# Examples:
```java

String str1 = "hello";

String str2 = new String("hello");

String[] stringArray = { "apple", "banana", "orange", "kiwi", "strawberry" };

int[] intArray = { 1, 2, 3, 4, 5 };

List<Integer> listOfIntger = Arrays.asList();

List<String> listOfString = Arrays.asList();

List<Employee> employees = Arrays.asList();

```