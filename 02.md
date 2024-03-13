# CORE JAVA

## Type Of Application :
- Standalone application -> desktop application,which need to be installed on desktop.
- Web Application -> application which are made to run on internet via server connection with dynamic web pages support
- Enterprice Application -> distributed in nature
- Mobile Application -> created for mobile devices.


## Variables

- Global Variables
- Local Variables

## Methods
    Method is a block of statement that are used to perform some task(action).

- static method
- non-static method

### why do we need method ?
- they provide behavior to object of a class.
- methods provide reusability feature.

## Operators 
    operators are symbols that perform operations on variables and values.

- Arithmetic operators
- Logical operators
- Relational operators
- Assignment operators
- Bitwise operators
- Unary operators
- Ternary operators
- Shift operators
- New operator
- Dot operator
- InstanceOf operators


## Access Modifiers
## static
## Constructor

## Encapsulation

- Binding of data into a single entity(class) is called as encapsulation.
- In Other words it is a programming technique that binds the class members (Variable + methods) together and prevent them from direct access.
- Every java class is an example of encapsulation.

## Inheritance

- Inheritance is creating a new class from the existing class functionality.
- it means reusability.
- it shows `IS-A` relationship.

## Polymorphism
## Abstraction

### Why do we need Marker Interface ?
- Marker Interface is an interface with no abstract method.(empty interface)
- It is also known as a tagging interface and is used to indicate or inform the JVM that a class implementing this interface will have some special behavior.
- Example : Serializable, Cloneable, and Remote Interfaces

## Object class
## final 
## this and super
## Exception Handling
## Serialization
## Array

---

## String
### String class methods
- char charAt(int index)
- static String format(String format, Object... args)
- String substring(int beginIndex)
- String concat(String str)
- String[] split(String regex)
- static String valueOf(int value)
- String trim()


### Difference between StringBuffer and StringBuilder?
### Why Strings are Immutable or final in Java ?

### Why java provided with String Constant Pool as we can store the objects in heap memory ?
- String Constant Pool provides the facility of reusability of the existing string object.
- When a new string object is created using the string literals ,then JVM first checks in the pool if this string already exists or not.
if it exists ,then it will reference the existing string rather than creating a new object.
- this will help in the speeding up of the application and also helps in saving the memory as no two objects will have the same content.

### realtime example of final class provided by java?
- A real-time example of a final class in Java is the java.lang.String class,
which is a final class and cannot be extended by any other class.
- This is because the String class is complete in nature and cannot be modified

### How to create immutable class.
---


## MultiThreading

### Realtime Example of Multithreading ?

### What is Thread ?
    What are the different Thread states
- New State (Born)
- Runnable State (Ready)
- Running State (Execution)
- Waiting State (Blocked)
- Dead State (Exit)

### Different ways of creating a thread in Java

1. One is by **extending java.lang.Thread class**
2. Another is by **implementing java.lang.Runnable interface**

### Can We Start Thread Twice ?

- No. You can not start thread twice
- This will result in a **IllegalThreadStateException**

```java
public class TestThread extends Thread{

    @Override
    public void run(){
        System.out.print("Thread start");
    }
    
    public static void main(String[] args){

        TestThread t = new TestThread();
        
        t.start();
        t.start(); // java.lang.IllegalThreadStateException
    }
}
```

### Why to override run() method while creating the thread using the Runnable interface ?
    because Runnable is interface and it has abstract method called run. 
    Hence when we implement the Runnable interface we have to override run() method. 

### Synchronization



### Create an Object without ‘new’ Keyword
    Using Class.newInstance()

## Input and Output Stream (java.io package)
- Stream : In Java , streams are the sequence of data that are read from the source and written to the destination.
1. Input and 
2. Output
- We can perform **File Handling** in java by java I/O API.
- IOException , FileNotFoundException-> fully checked exception

- Type of streams :
1. Byte Stream
- Input Stream - read()
> This abstract class is the superclass of all classes representing an input stream of bytes. It's designed to read data from various sources.Some common subclasses include FileInputStream, ByteArrayInputStream, and BufferedInputStream.
- Output Stream - write()
> This abstract class is the superclass of all classes representing an output stream of bytes. It's designed to write data to various destinations. Some common subclasses include FileOutputStream, ByteArrayOutputStream, and BufferedOutputStream.
2. Character Stream
- Reader
- Writer
3. Object

## Serialization and DeSerialization
- Serialization is a mechanism of converting the state of an object into a byte stream.
- Deserialization is the reverse process where the byte stream is used to recreate the actual
Java object in memory.
> Note: The byte stream created is platform independent. So, the object serialized on one
platform can be deserialized on a different platform.

### Why we need Serialization in java?
- To transfer objects through a network.
- To keep Java objects in memory.
- To save Java objects in files.

### How to implement serialization in java?
1. For **serializing** the **object**, we call the **writeObject()** method of **ObjectOutputStream**, and
for **deserialization** we call the **readObject()** method of **ObjectInputStream** class.
2. We must implement the **Serializable interface** for serializing the object.

### What is Serial Version UID?
- every serializable class/object gets associated
with a unique identification number **provided by the JVM** of the host machine.This Unique ID is called Serial Version UID.
- This UID is used as an identification by the JVM of the receiving end to confirm that the same object is being DeSerialized at the receiving end.

### What is Transient Keyword?
- Transient Keyword is a reserved keyword in Java.
- It is used as a variable modifier at the time of the Serialization process.
- **Declaring a variable with Transient keyword avoids the variable from being Serialized.**
- During deserialization, the transient variable will be assigned a default value, typically null for reference types or 0 for primitive types.