## [SpringFramework](https://github.com/swapnilk30/SpringFramework)


### What are the different bean scopes in spring?
- singleton
- prototype
- request
- session
- globalsession


### 
- @Configuration
- @Bean
- @Component
- @Scope






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

## Frequently Used Annotations From Spring Framework.

spring core module related annotations
- @Component
- @Service 
- @Repository

@Configuration
@Bean

@Autowired
@Qualifier



# Spring Framework
- the primary feature of the spring framework is **Dependency Injection.**
- 

## Difference between heavy weight and light weight components

- EJB(enterprise java bean) are **depends on application server.** So it is called as heavy weight components.
- Spring are **not depends on application server.** They just use your JDK and jar file to run application.
