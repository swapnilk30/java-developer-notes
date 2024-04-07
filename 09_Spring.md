
### What is Spring Bean?
    The java class which is managed by IOC is called as Spring Bean.



### How to represent java class as Spring Bean?
- Using Xml configuration
```
<bean id="car" class="com.algowebpro.Car" />
```
- Using Annotations
```
@Component , @Service , @Repository
```

### Difference between heavy weight and light weight components

- EJB(enterprise java bean) are **depends on application server.** So it is called as heavy weight components.
- Spring are **not depends on application server.** They just use your JDK and jar file to run application.

### What are the different bean scopes in spring?

- singleton (default)

```java
@Component
@Scope("singleton")
public class MySingletonBean {
    // Bean definition
}

```
- prototype
- request
- session
- globalsession


### Spring Boot Autoconfiguration
```
### Pagination and Sorting
https://www.youtube.com/watch?v=fJ914p0A7UA
https://www.youtube.com/watch?v=CPueZeE1JH8
```

## Spring Boot Actuator
## Spring Boot Profiles
## Spring Boot Logging


```
- What are the key Advantages of spring boot over spring
- can you explain concept of DI in Spring and why it is beneficial
- What is role of @SpringBootApplication Annotation
- How Spring boot achive Auto-Configuration with example.(dataSource Example)
- What are the steps to Override a specific AutoConfiguration.(application.properties)
- What annotation used to create restful services in spring boot.(@RestController )
- How handle exception in spring boot rest aplications
- approach to secure end points
https://www.youtube.com/watch?v=0QhyHQh0avE
```

```
- Spring Boot Interview Mastery | Question & Answer Guide for Developers | Part-1 |
https://www.youtube.com/watch?v=-_tPeb3VE6w&t=0s

- How One Singleton Bean handles 1000X Requests concurrently in a Spring Boot App?
https://www.youtube.com/watch?v=wsq_nhEzWFw&t=200s
```
