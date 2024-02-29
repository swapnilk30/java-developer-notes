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

		List<Employee> listOfEmployee = Arrays.asList(new Employee("emp1 hr1", "HR"), new Employee("emp2 hr2", "HR"),
				new Employee("emp3 hr3", "HR"), new Employee("emp4 hr4", "HR"), new Employee("emp5 admin1", "ADMIN"),
				new Employee("emp6 admin2", "ADMIN"), new Employee("emp7 pd1", "PD"), new Employee("emp8 pd2", "PD"),
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




### What is the difference between Collection and Collections.
- Collection is an **interface** which can be used to represent a group of individual objects as a single entity.
- Collections is an utility **class** present in **java.util** package to define several utility methods (like sorting )for Collection objects.

## What is the difference between Iterator and ListIterator in java.
## Comparable vs Comparator with Example.