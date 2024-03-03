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

## Object class
## final 
## this and super
## Exception Handling
## Serialization
## Array
## String
 
## MultiThreading
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

## Collection Framework












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