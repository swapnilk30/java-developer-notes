### Employee.java

```java
package com.demo;

public class Employee {
	
	private String empName;
	private String deptName;
	
	public String getEmpName() {
		return empName;
	}
	public void setEmpName(String empName) {
		this.empName = empName;
	}
	public String getDeptName() {
		return deptName;
	}
	public void setDeptName(String deptName) {
		this.deptName = deptName;
	}
	public Employee(String empName, String deptName) {
		super();
		this.empName = empName;
		this.deptName = deptName;
	}
	
	
	public Employee() {
		// TODO Auto-generated constructor stub
	}
	@Override
	public String toString() {
		return "Employee [empName=" + empName + ", deptName=" + deptName + "]";
	}
		
}
```

### EmployeeTest.java

```java
package com.demo;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

public class TraditionalWay {

	public static void main(String[] args) {

		List<Employee> listOfEmployee = Arrays.asList(
			new Employee("emp1 hr1", "HR"),
			new Employee("emp2 hr2", "HR"),
			new Employee("emp3 hr3", "HR"),
			new Employee("emp4 hr4", "HR"),
			new Employee("emp5 admin1", "ADMIN"),
			new Employee("emp6 admin2", "ADMIN"),
			new Employee("emp7 pd1", "PD"),
			new Employee("emp8 pd2", "PD"),
			new Employee("emp9 pd3", "PD"));
		
		Map<String, List<Employee>> map = new HashMap<String, List<Employee>>();

		for(Employee e:listOfEmployee) {
			String deptName = e.getDeptName();//HR
			
			if(!map.containsKey(deptName)) {
				map.put(deptName, new ArrayList<Employee>());// HR,list<Employee>
			}
			map.get(deptName).add(e);
		}
		
		for(Map.Entry e:map.entrySet()) {
			System.out.println(e);
		}
	}
}
```
### TestEmployee.java
```java
package com.demo;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.HashSet;
import java.util.Iterator;
import java.util.List;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Set;
import java.util.function.Function;
import java.util.stream.Collectors;

public class Test {

	public static void main(String[] args) {

		List<Employee> listOfEmployee = Arrays.asList(new Employee("emp1 hr1", "HR"), new Employee("emp2 hr2", "HR"),
				new Employee("emp3 hr3", "HR"), new Employee("emp4 hr4", "HR"), new Employee("emp5 admin1", "ADMIN"),
				new Employee("emp6 admin2", "ADMIN"), new Employee("emp7 pd1", "PD"), new Employee("emp8 pd2", "PD"),
				new Employee("emp9 pd3", "PD"));

		//Using Java 8
		Map<String, List<Employee>> departmentWiseList = listOfEmployee.stream()
				.collect(Collectors.groupingBy(Employee::getDeptName));
		
		for(Entry e : departmentWiseList.entrySet()) {
			System.out.println(e);
		}

	}
}
```

### what is primitive data types ?
- They are used to store single value in variables.
- These primitive types are used to declare variables that hold simple values like numbers, characters, or boolean values.
```java
int x = 10;
```

# Array

### What is Array ?
- 

# Collection

### Difference between Array and Collection.

| Array | Collection |
|---|---|
|1.|1.|
|1.|1.|
|1.|1.|
|1.|1.|
|1.|1.|


## Comparable vs Comparator with Example.

## Concurrent Collections


## What is the Collection framework in Java?
- It defines several classes and interface which can be used as objects as single entity.

## What are the main differences between array and collection?

## What is the difference between Collection and Collections?
- Collection is an **interface** which can be used to represent a group of individual objects as a single entity.
- Collections is an utility **class** present in **java.util** package to define several utility methods (like sorting )for Collection objects.

## There are 9 key interfaces of collection framework.
1. Collection
2. List
3. Set
4. SortedSet
5. NavigableSet
6. Queue
7. Map
8. SortedMap
9. NavigableMap

# List
- ArrayList, LinkedList, Vector, Stack
# Set
- HashSet, LinkedHashSet, TreeSet
# Map
- HashMap, LinkedHashMap, TreeMap, HashTable


## ArrayList
- **Underlying Data Structure:** Internally backed by an array that dynamically resizes itself when needed. Elements are stored in contiguous memory locations.
## LinkedList
- **Underlying Data Structure:** Implemented as a **doubly linked list**. Each element is stored in a node that contains a reference to the previous and next elements.


## What is the difference between ArrayList and Vector?
## What is the difference between ArrayList and LinkedList?

## What is the difference between Iterator and ListIterator?
## What is the difference between Iterator and Enumeration?

## What is the difference between List and Set?

## What is the difference between HashSet and TreeSet?
## What is the difference between Set and Map?

## What is the difference between HashSet and HashMap?
## What is the difference between HashMap and TreeMap?

## What is the difference between HashMap and Hashtable?

## What is the difference between Comparable and Comparator?
