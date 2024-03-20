```
# Basic Program
- Program to Check Whether A Number is Prime or Not in Java.
- How to Check Given Number is Palindrome or Not
```

## Program to Check Whether A Number is Prime or Not in Java.
	Prime number is a number that is greater than 1 and divided by 1 or itself only.
	prime numbers can't be divided by other numbers than itself or 1. For example 2, 3, 5, 7, 11, 13, 17.... are the prime numbers.
	Note: 0 and 1 are not prime numbers. The 2 is the only even prime number because all the other even numbers can be divided by 2.

```java
public class PrimeNumber {
	
	public static void main(String[] args) {
			
		int num = 3;
		
		boolean result = isPrime(num);
		
		if(result) {
			System.out.println("Prime Number "+ num);
		}else {
			System.out.println("Not a Prime Number");
		}
	}

	private static boolean isPrime(int num) {
		
		boolean result = true;

		if (num <= 1) { 
			return false;
		}
		
		for(int i =2;i<=num-1;i++	) {
		
			if(num % i == 0) {
				result = false;
			}
		}
		return result;
	}
}
```

## How to Check Given Number is Palindrome or Not
```java
public class PalindromeNum {
	
	public static void main(String[] args) {
		
		int num = 121;
		checkPalindrome(num);
		
	}
	private static void checkPalindrome(int num) {
		
		int temp = num;
		
		int sum = 0;
		
		while(num > 0) {
			int rem = num % 10;
			sum = (sum * 10) + rem;
			num = num /10;
		}
		
		if(temp == sum) {
			System.out.println("Palindrome");
		}else {
			System.out.println("Not Palindrome");
		}	
	}
}
```