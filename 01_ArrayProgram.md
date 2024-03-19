# Array
```
# ArrayProgram

- Find Missing Number in Array
- Program to find the minimum (or maximum) element of an array
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