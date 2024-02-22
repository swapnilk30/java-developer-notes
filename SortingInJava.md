### Comparable Interface (compareTo())

    Sort Employees Based on Salary

```java
public class Employee implements Comparable<Employee>{

	private int id;
	private String name;
	private double salary;
		
	public Employee() {
		// TODO Auto-generated constructor stub
	}

	public int getId() {
		return id;
	}

	public void setId(int id) {
		this.id = id;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public double getSalary() {
		return salary;
	}

	public void setSalary(double salary) {
		this.salary = salary;
	}

	public Employee(int id, String name, double salary) {
		super();
		this.id = id;
		this.name = name;
		this.salary = salary;
	}

	@Override
	public String toString() {
		return "Employee [id=" + id + ", name=" + name + ", salary=" + salary + "]";
	}

    // logic to sort the data Ascending
	@Override
	public int compareTo(Employee employee) {
		 
		if(salary == employee.getSalary()) {
			return 0;
		}else if (salary > employee.getSalary()) {
			return 1;
		}else
			return -1;
	}

    //Sorting By Reverse Order
    /*	
    @Override
	public int compareTo(Employee employee) {
		// logic to sort the data Ascending 
		if(salary == employee.getSalary()) {
			return 0;
		}else if (salary > employee.getSalary()) {
			return -1; // changed to -1
		}else
			return 1; // changed to 1
	}
    */
}
```
```java
public class EmployeeTest {
	
	public static void main(String[] args) {
		
		List<Employee> employeeList = new ArrayList<>();
		
		// Adding sample data
        employeeList.add(new Employee(1, "John", 50000.0));
        employeeList.add(new Employee(2, "Alice", 60000.0));
        employeeList.add(new Employee(3, "Bob", 55000.0));
        employeeList.add(new Employee(4, "Carol", 55000.0));
        employeeList.add(new Employee(5, "David", 62000.0));
        employeeList.add(new Employee(6, "Eve", 50000.0));
		
        Collections.sort(employeeList);
		
        for(Employee e:employeeList) {
        	System.out.println(e);
        }
	}
}
```




### Comparator Interface