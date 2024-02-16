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