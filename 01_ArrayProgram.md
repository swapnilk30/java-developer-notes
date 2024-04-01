# Array
```
# ArrayProgram

- Find Missing Number in Array
	int [] arr = {1,2,3,5};

- Program to find the minimum (or maximum) element of an array
	int a[]={1,423,6,46,34,23,13,53,4};
	
- How to rotate an array in Java

- How to rotate an array by x places in Java

- How to reverse the array elements in Java

- Java Program to remove duplicate element from an Array

- Remove Duplicates from Sorted Array
https://www.youtube.com/watch?v=xnj-GjdboGE

- Merge Sorted Array 
https://www.youtube.com/watch?v=xF3TU-QlhJQ&t=427s

- Subarray Sum Equals K using hashmap

- Write a Program to find the second largest number in array in Java
https://bushansirgur.in/write-a-program-to-find-the-second-largest-number-in-array-in-java/

- Find the Sum of All Even Numbers from the given array using Java8 Features.

```



## Find Missing Number in Array
	int [] arr = {1,2,3,5};
```java
public class MissingNumberInArray {
	
	public static void main(String[] args) {
		
		// Array should not have duplicates
		// Array No need be Sorted order
		
		int [] arr = {1,2,3,5};
		
		// 1+2+3+5=11
		
		int sum1 = 0;
		for(int i = 0 ; i< arr.length; i++) {
			sum1 = sum1 + arr[i];
		}
		System.out.println("Sum of Elements in Array ="+sum1);
		
		// 1+2+3+4+5 = 15
		int sum2=0;
		for(int i =1;i<=5;i++) {
			sum2 = sum2 +i;
		}
		System.out.println("Sum Of Range Of Elements in Array ="+sum2);
		
		System.out.println("Missing Number is = "+(sum2-sum1));
	}
}
```

## Program to find the minimum (or maximum) element of an array
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
## How to rotate an array by x places in Java
	int [] arr = {1,2,5,-1,10};

## Merge Sorted Array
```java

public class MergeSortedArray {
	
	public static void main(String[] args) {
		
		int[] arr1 = {1,2,3,5,7};
		int[] arr2 = {3,5,7,9};
		
		int [] result = mergeSorted(arr1,arr2);
		
		System.out.println(Arrays.toString(result));
		
 	}

	private static int[] mergeSorted(int[] arr1, int[] arr2) {
		
		int len1 = arr1.length;
		int len2 = arr2.length;
		
		int [] result = new int[len1+len2];
		
		int i=0,j=0,k=0;
		
		while(i< len1 && j< len2) {
			
			if(arr1[i]<arr2[j]) {
				result[k] = arr1[i];
				i++;
				k++;
			}else {
				result[k] = arr2[j];
				j++;
				k++;
			}
		}
		
		while(i<len1) {
			result[k++]=arr1[i++];
		}
		
		while(j<len2) {
			result[k++]=arr2[j++];
		}
		
		
		return result;
	}

}
```

## Find the Sum of All Even Numbers from the given array using Java8 Features.
    int [] arr = {1,2,3,4,5,6,7,8,9,10};

```java
    int sum = Arrays.stream(arr).filter(n->n%2 == 0).sum();
    System.out.println(sum);
```


---


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


## Merge Two Arrays Into Single Array In Java
https://www.youtube.com/watch?v=7PJA0rwt1VQ

## How to sort an array in fastest way using java program
https://www.youtube.com/watch?v=r7-aGiHlo_Q&t=509s

## Array Duplicates Printing Using Java Program
https://www.youtube.com/watch?v=DcihmSV5ZPo

## Merged two arrays into a single array with sorting and remove duplicates java8
https://www.youtube.com/watch?v=pJbFPkHYIos

## Java Program To Find Missing Number In Array
https://www.youtube.com/watch?v=BpqhcN7Qcpk&t=47s

## Split an array into chunks with a specified size.
Example - array = [1,2,3,4,5] chunkSize = 1 [1] [2] [3] [4] [5] chunkSize = 2 [1, 2] [3, 4] [5] chunkSize = 3 [1, 2, 3] [4, 5] chunkSize = 4 [1, 2, 3, 4] [5] chunkSize = 5 [1, 2, 3, 4, 5] chunkSize = 6 [1, 2, 3, 4, 5]

```
This is a problem around OO design Ask the candidate to start a new code snippet in onlingdb. Once the questions are done, make sure the code snippet is put in the feedback comments. You have to design a solution (classes, interfaces, etc etc) for DeckofCards. Each card has a suit (heart, spade, club, diamond) and a rank (ace, king, queen jack, 10, 9, 8, 7, 6, 5, 4, 3, 2). Problem 1 Write a function to Compare two cards and return bigger one. Suit doesnt matter. Problem 2 You are given a shuffled deck of cards. You have to sort them (by suit and then by rank) 

Flatten nested arrays in java. 1. Numbers or nested arrays can be upto n levels. 2. Recursive approach - Good to know Code Template - https://onlinegdb.com/O1TZTwvHT Ensure the candidate fork is given the detailed feedback Ensure the candidate output is copy pasted into the detailed feedback Example Input -> [[[1],2],[3,4]] Output -> [1,2,3,4]

Can one use an Employee class as a key in a HashMap?

Employee Table -- Id -- Name -- Salary -- Department id Find one employee from each department who is getting the highest salary within his department. Discuss further on server side pagination, boundary cases like 2 emp getting the same salary in the same department which is highest etc.

Consider a class A with a synchronized method class A { public void synchronized m1() {Thread.sleep(5000);} } We create two objects of this class - o1 and o2. We call o1.m1() on one thread and o2.m1() on another thread, at the same time. What will be the behaviour? Follow up with - how will you force these calls to execute one after the other

```
```