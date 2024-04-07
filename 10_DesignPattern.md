### How to Create Singleton Class
### How it will work multithreading environment

```
- How to create Singleton Class
https://www.youtube.com/watch?v=yC4H8YdBrqg
```

```java
// Lazy Initialization Using double check locking 
public class SingletonClass {
	
	private static volatile SingletonClass instance = null;
	
	private SingletonClass() {
		
	}
	
	// Double Checked Locking Pattern
	public static SingletonClass getInstance() {
		if(instance == null) {
			synchronized (SingletonClass.class) {
				if(instance == null) {
					instance = new SingletonClass();
				}
			}	
		}
		return instance;
	}
}
```

## Factory Design Pattern Project : Live Example

- create functional Interface in Service Package AccessoriesService { String getSpecificProduct(); }
- create Classes in Factory Package as AccessoriesFactory ,Camera , Laptop , Mobile , etc.