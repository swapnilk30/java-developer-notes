```
# StringProgram

- Java program to check whether a string is a Palindrome.
- Compress a string aaabbbcc into a3b3c2 in java.
- Write Java Program -input "a2b3c1" and Output should be "aabbbc"
- In a string, count the repeated characters and show in map using Java 8.
- Write a program to convert camel case string to snake case string.
- Java Program To Find First Non Repeated Character In String

```

### Java program to check whether a string is a Palindrome.

```java
package com.string;

public class CheckPalindromeString {
	
	public static void main(String[] args) {
		String str = "MADAM";
		
		//reverse string 
		String rev = "";
		for(int i = str.length()-1;i>=0;i--) {
			rev = rev + str.charAt(i);
		}
		System.out.println(rev);
		
		if(str.equals(rev)) {
			System.out.println("String is Palindrome !!");
		}else {
			System.out.println("String is Not Palindrome !!");
		}
	}
}
```

### Compress a string aaabbbcc into a3b3c2 in java.
    (Given a string "aaabbbcc", compress it "a3b3c2".Given that output strings length is always smaller than input string, you have to do it inpalce.)

```java
public class CompressString {
	
	public static void main(String[] args) {
		String str ="aaabbbcc"; // output = "a3b3c2"
		
		Map<Character, Integer> map = new HashMap<Character, Integer>();
		
		for(int i = 0; i< str.length(); i++) {
			
			if(map.containsKey(str.charAt(i))) {
				map.put(str.charAt(i),map.get(str.charAt(i))+1);
			}else {
				map.put(str.charAt(i), 1);
			}
		}
		
		map.forEach((key,value) -> System.out.print(key + "" + value));
	}

}   
```

### Write Java Program -input "a2b3c1" and Output should be "aabbbc"

```java
public class ExpandString {
	
	public static void main(String[] args) {
		String str = "a3b3c2"; // output "aaabbbcc"
		
		
		for(int i = 0 ; i< str.length(); i++) {
			if(Character.isAlphabetic(str.charAt(i))) {
				System.out.print(str.charAt(i));
			}else {
				int x = Character.getNumericValue(str.charAt(i));
				//System.out.println(x);
				
				for(int j = 1; j<x; j++) {
					System.out.print(str.charAt(i-1));
				}
			}
		}	
	}
}
```

### In a string, count the repeated characters and show in map using Java 8.
    For Example, "india" -> output is "i->2, n->1,d->1,a->1"

```java
public class CountChars {
	
	public static void main(String[] args) {
		
		String str = "india";
		
		Map<Character, Long> charCounts = str.chars().mapToObj(c -> (char) c).collect(Collectors.groupingBy(Function.identity(),Collectors.counting()));
		
		charCounts.forEach((k,v) -> System.out.print(k +" -> "+ v + " "));
		
	}
}
```

### Write a program to convert camel case string to snake case string.
    whatIsYourName -> WHAT_IS_YOUR_NAME
	
```java

public class CamelToSnakeCase {
	
	public static void main(String[] args) {
		
		String str = "whatIsYourName";
		
		String snakeCase = convert(str);
		
		System.out.println(snakeCase);
	}

	private static String convert(String str) {
		
		String result = str.charAt(0)+"";
		
		int len = str.length();
		
		int i;
		
		for(i=1;i<len;i++) {
			if(Character.isUpperCase(str.charAt(i))) {
				result = result + "_" + str.charAt(i);
			}else {
				result = result + str.charAt(i);
			}	
		}
		return result.toUpperCase();
	}
}
```

### Java Program To Find First Non Repeated Character In String

	String str = "AABCDBE";
	1. Without Using Collections
	2. Using Collections

```java

public class NonRepeatingChar {
	
	public static void main(String[] args) {
		
		String str = "AABCDBE";
		
		Map<Character, Integer> map = new HashMap<Character, Integer>();
		
		for(int i = 0; i<str.length() ; i++) {
			
			char c = str.charAt(i);
			
			if(map.containsKey(c)) {
				map.put(c, map.get(c)+1);
			}else {
				map.put(c, 1);
			}
		}
		
		for(Entry<Character,Integer> e:map.entrySet()) {
			
			if(e.getValue() == 1) {
				System.out.println(e);
				break;
			}
		}	
	}
}
```