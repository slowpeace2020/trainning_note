### Homework 8

### Question List

- [What is IOC](#what-is-ioc)
- [What is DI](#what-is-di)
- [What is AOP](#what-is-aop)
- [What is Aspect, joinpoint, pointcut, advice, target](#what-is-aspect-joinpoint-pointcut-advice-target)
- [Bean scope](#bean-scope)
    - What is prototype, singleton, request?
- [ApplicationContext vs BeanFactory](#applicationcontext-vs-beanfactory)
- [Different types of DI and their pros and cons](#different-types-of-di-and-their-pros-and-cons)

### Homework 9

### Question List

- [Why Spring Boot? Pros and cons](#why-spring-boot-pros-and-cons)
- [How to start a Spring Boot project from scratch](#how-to-start-a-spring-boot-project-from-scratch)
- [`@Controller` vs `@RestController`](#controller-vs-restcontroller)
- [`@PathVariable` vs `@RequestParam`](#pathvariable-vs-requestparam)
- [`@RequestBody` vs `@ResponseBody`](#requestbody-vs-responsebody)
- [How to use `GetMapping`, `PutMapping`, `PostMapping`, `DeleteMapping`, `RequestMapping`](#how-to-use-getmapping-putmapping-postmapping-deletemapping-requestmapping)
- [What is Spring Actuator](#what-is-spring-actuator)
- [How to achieve async in Spring Boot application](#how-to-achieve-async-in-spring-boot-application)

### Homework 10

### Question List

- [How does Spring handle exceptions](#how-does-spring-handle-exceptions)
- [How does Spring validate data](#how-does-spring-validate-data)
- [How does Spring do the log](#how-does-spring-do-the-log)
- [Cache hit vs cache miss](#cache-hit-vs-cache-miss)
- [Do some research on Redis and have a basic understanding](#do-some-research-on-redis-and-have-a-basic-understanding)
- [SQL vs NoSQL database](#sql-vs-nosql-database)
- [What is database normalization](#what-is-database-normalization)
- [Vertical scaling vs horizontal scaling](#vertical-scaling-vs-horizontal-scaling)
- [What is ACID](#what-is-acid)
- [What is CAP](#what-is-cap)
;
### Homework 8

### Question List

- ### What is IOC
IOC stands for "Inversion of Control." It is a software design principle and a pattern used in object-oriented programming. In traditional programming, the flow of control is determined by the program's code, where objects directly call and interact with each other. However, with IOC, the control over the flow of a program is inverted or shifted from the program to a container or framework.

In practical terms, IOC means that rather than an application explicitly calling components or services it depends on, the responsibility for creating and managing these components is delegated to a framework or container. This inversion of control allows for better separation of concerns and promotes loose coupling between components, making the codebase more modular, flexible, and easier to maintain.

One common implementation of IOC is dependency injection (DI), where a container injects dependencies (such as objects, services, or configurations) into the components that need them, rather than the components creating or managing their dependencies themselves. This allows for easier testing, as dependencies can be mocked or replaced with stubs during testing, and facilitates easier reusability and swapping of components without modifying the code.

- ### What is DI
DI stands for "Dependency Injection." It is a software design pattern and a form of Inversion of Control (IoC) where the dependencies of a component are provided from the outside rather than created within the component itself.

In DI, dependencies (such as objects, services, or configurations) are "injected" into a component when it is constructed or during its lifecycle, rather than being created or managed by the component internally. This allows for better separation of concerns and promotes loose coupling between components, making the codebase more modular, flexible, and easier to maintain.

There are several ways to implement DI:

1. Constructor Injection: Dependencies are provided to a component through its constructor. This is one of the most common and recommended approaches to implement DI.

2. Setter Injection: Dependencies are provided to a component through setter methods. While less common than constructor injection, setter injection can be useful in certain scenarios, such as when the dependencies are optional.

3. Interface Injection: Dependencies are provided to a component through an interface method. This approach is less common and less flexible compared to constructor and setter injection.

DI is often used in conjunction with a dependency injection container or framework, which automates the process of managing and injecting dependencies into components. Popular DI frameworks in various programming languages include Spring Framework for Java, Angular for TypeScript/JavaScript, and Dagger for Android development in Java or Kotlin.

- ### What is AOP
AOP stands for Aspect-Oriented Programming. It is a programming paradigm that aims to increase modularity and reduce code duplication by separating cross-cutting concerns from the main business logic.

In AOP, a concern is a particular feature or behavior that cuts across multiple modules or layers of an application, such as logging, security, transaction management, or error handling. These concerns are referred to as cross-cutting concerns because they affect multiple parts of the application.

AOP introduces the concept of aspects, which encapsulate cross-cutting concerns. Aspects are modular units of cross-cutting behavior that can be applied to different parts of the application without modifying the core business logic.

AOP provides mechanisms to dynamically weave aspects into the code at runtime. This is typically done using a technique called "interception," where the AOP framework intercepts method calls or events and applies the appropriate aspects before or after the target method execution.

Key concepts in AOP include:

1. Advice: The code that implements a cross-cutting concern. Advices are executed at specific join points in the application, such as method invocation or exception handling.

2. Join Point: A specific point in the execution of the application where an aspect can be applied. Examples include method execution, field access, or object instantiation.

3. Pointcut: A set of join points where an aspect should be applied. Pointcuts define the conditions under which an advice should be executed.

4. Weaving: The process of integrating aspects into the codebase. Weaving can be done at compile-time, load-time, or runtime.

AOP frameworks provide tools and APIs to define aspects, pointcuts, and advices, and to apply them to the application code. Popular AOP frameworks include AspectJ for Java, PostSharp for .NET, and Spring AOP for Spring Framework applications.


- ### What is Aspect, joinpoint, pointcut, advice, target
  - #### Aspect
An aspect is a modular unit of cross-cutting behavior in Aspect-Oriented Programming (AOP). It encapsulates a particular cross-cutting concern, such as logging, security, or transaction management, which cuts across multiple modules or layers of an application. Aspects define how the cross-cutting concern should be implemented and applied to the target code.

  - #### Join Point
A join point is a specific point in the execution of a program where an aspect can be applied. It represents a well-defined point in the execution flow, such as method invocation, method execution, object creation, or exception handling. Join points are defined by the programming language or framework and serve as the targets for applying aspects.

  - #### Pointcut
A pointcut is a set of join points where an aspect should be applied. It defines the conditions or criteria for selecting join points in the program's execution flow. Pointcuts specify which methods, classes, or objects should be intercepted by the aspect. They allow developers to specify when and where the cross-cutting behavior defined by the aspect should be executed.

  - #### Advice
An advice is the actual implementation of a cross-cutting concern in AOP. It represents the code that runs at a specific join point in the program's execution flow. Advices define what should be done when the aspect is applied to a join point. There are different types of advice, such as "before," "after," "around," "after-returning," and "after-throwing," each specifying when the advice should be executed relative to the target method execution.

  - #### Target
The target, also known as the target object or target method, refers to the component of the application that is being advised by an aspect. It represents the original code or functionality that the aspect is applied to modify or enhance. The target is the recipient of the cross-cutting behavior defined by the aspect. In AOP, aspects are applied to targets based on defined pointcuts to intercept their execution and apply the desired behavior.

- ### Bean scope
    - What is prototype, singleton, request?

  - **Prototype**: In Spring Framework, a bean with prototype scope means that a new instance of the bean is created every time it is requested. This means that each time you ask the container for an instance of the bean, you get a new instance, independent of any previously created instances. This is useful for stateful beans where you want to maintain separate instances with their own state.

  - **Singleton**: Singleton scope is the default scope in Spring. A bean with singleton scope means that only one instance of the bean is created per Spring IoC container. Whenever you ask the container for an instance of the bean, it returns the same instance if it already exists or creates a new one if it doesn't. This is suitable for stateless beans or beans that need to be shared across the application.

  - **Request**: Request scope is specific to web applications. A bean with request scope means that a new instance of the bean is created for every HTTP request. This ensures that each HTTP request is handled by a separate instance of the bean, allowing for isolation and thread safety in web applications. Request-scoped beans are typically used for objects that hold request-specific data, such as HTTP session attributes or form data.

- ### ApplicationContext vs BeanFactory
  - **ApplicationContext**:
    - **Description**: ApplicationContext is an advanced container that extends the functionality of the BeanFactory. It provides all the features of the BeanFactory and adds additional functionalities such as event propagation, internationalization, resource loading, and application lifecycle management.
    - **Features**:
      - Automatic BeanPostProcessor registration.
      - Automatic BeanFactoryPostProcessor registration.
      - Built-in support for message resource handling (for i18n).
      - Built-in event propagation mechanisms.
      - Easier integration with Spring's AOP features.
      - Integration with Spring's expression language (SpEL).
    - **Performance**: ApplicationContext initializes all beans eagerly by default, which can lead to longer startup times compared to BeanFactory. However, ApplicationContext provides better performance at runtime due to its caching mechanism for singleton beans.

  - **BeanFactory**:
    - **Description**: BeanFactory is the core container interface in Spring Framework. It provides the fundamental features of managing beans, such as instantiation, wiring, and lifecycle management.
    - **Features**:
      - Lazy loading of beans: BeanFactory initializes beans on demand, leading to faster startup times compared to ApplicationContext.
      - Basic bean instantiation and wiring capabilities.
      - Lightweight container implementation.
      - Suitable for memory-constrained environments.
    - **Performance**: BeanFactory initializes beans lazily, meaning beans are created only when they are requested. This can lead to faster startup times compared to ApplicationContext, especially in applications with a large number of beans where eager initialization might cause performance issues.

- ### Different types of DI and their pros and cons
```markdown
- **Types of Dependency Injection (DI)**:

    1. **Constructor Injection**:
        - **Description**: Dependencies are provided to the dependent class through its constructor.
        - **Pros**:
            - Ensures that all required dependencies are available when the object is created.
            - Provides immutable objects, improving thread safety.
            - Makes dependencies explicit, enhancing code readability and maintainability.
        - **Cons**:
            - Can lead to large constructor signatures, making the code harder to read.
            - Increases the coupling between classes.

    2. **Setter Injection**:
        - **Description**: Dependencies are injected into the dependent class through setter methods.
        - **Pros**:
            - Provides flexibility by allowing dependencies to be changed or replaced at runtime.
            - Avoids the need for large constructor signatures.
        - **Cons**:
            - Makes it harder to ensure that all required dependencies are set before the object is used.
            - Can lead to mutable objects, potentially causing thread safety issues.
            - Introduces additional boilerplate code for setter methods.

    3. **Field Injection**:
        - **Description**: Dependencies are injected directly into the dependent class's fields.
        - **Pros**:
            - Concise syntax, reducing the amount of boilerplate code.
            - Easier to use with frameworks like Spring, which handle dependency injection automatically.
        - **Cons**:
            - Violates encapsulation principles by exposing internal details of the class.
            - Harder to test in isolation, as dependencies cannot be easily mocked or substituted.
            - Difficult to identify dependencies at a glance, leading to potential maintenance issues.

    4. **Interface Injection** (Deprecated):
        - **Description**: Dependencies are injected through an interface implemented by the dependent class.
        - **Pros**:
            - Promotes loose coupling between classes by allowing multiple implementations of the interface.
        - **Cons**:
            - Requires the dependent class to implement an interface solely for the purpose of dependency injection, leading to unnecessary boilerplate code.
            - Increases the complexity of the codebase and may introduce unnecessary abstraction layers.

- **Comparison**:
    - **Constructor Injection** is preferred for mandatory dependencies that must be available when the object is created.
    - **Setter Injection** offers flexibility and is suitable for optional dependencies or scenarios where dependencies may change at runtime.
    - **Field Injection** is convenient but can lead to issues with testability and maintainability.
    - **Interface Injection** is deprecated in favor of other injection methods due to its disadvantages.
```
This markdown snippet outlines different types of Dependency Injection (DI) and discusses their pros and cons, along with a comparison of each method.

### Homework 9

### Question List

- ### Why Spring Boot? Pros and cons
- **Pros of Spring Boot**:

  1. **Rapid Development**: Spring Boot simplifies the configuration and setup of Spring-based applications, allowing developers to quickly bootstrap and develop robust applications.

  2. **Convention over Configuration**: Spring Boot provides sensible defaults and conventions, reducing the need for manual configuration and boilerplate code, thus enhancing productivity.

  3. **Embedded Server**: It comes with an embedded servlet container (e.g., Tomcat, Jetty), eliminating the need for external server setup and deployment, which simplifies deployment and testing.

  4. **Auto-Configuration**: Spring Boot's auto-configuration feature automatically configures beans based on dependencies present in the classpath, reducing manual configuration efforts.

  5. **Standalone**: Spring Boot applications can be packaged as standalone JAR files, which contain embedded servers, making deployment and distribution straightforward.

  6. **Integration**: It offers seamless integration with other Spring projects and third-party libraries, enabling developers to leverage a wide range of tools and frameworks.

  7. **Microservices Support**: Spring Boot provides features like Spring Cloud for building and deploying microservices architectures, including service discovery, configuration management, and distributed tracing.

- **Cons of Spring Boot**:

  1. **Complexity**: While Spring Boot simplifies many aspects of application development, it can still be complex, especially for beginners, due to the extensive ecosystem and configuration options.

  2. **Magic Behind Auto-Configuration**: While auto-configuration is convenient, it can sometimes lead to unexpected behavior or conflicts, making troubleshooting challenging.

  3. **Performance Overhead**: Spring Boot's auto-configuration and dependency injection mechanisms may introduce some performance overhead compared to manually optimized configurations.

  4. **Learning Curve**: Mastering Spring Boot requires understanding of underlying Spring concepts, which can have a steep learning curve for developers unfamiliar with the framework.

  5. **Limited Control**: While Spring Boot's conventions and defaults are beneficial for rapid development, they may limit the level of control and customization desired in certain scenarios.


- ### How to start a Spring Boot project from scratch
- To start a Spring Boot project from scratch, you can follow these steps:

1. **Set Up Development Environment**:
  - Ensure that you have Java Development Kit (JDK) installed on your system.
  - Choose an Integrated Development Environment (IDE) such as IntelliJ IDEA, Eclipse, or Spring Tool Suite (STS).

2. **Create a New Project**:
  - Open your IDE and create a new Maven or Gradle project.
  - Choose Spring Initializr or Maven Archetype as the project template.

3. **Configure Project Metadata**:
  - Provide the Group and Artifact names for your project.
  - Choose the desired version of Spring Boot.
  - Add dependencies based on your project requirements (e.g., web, data, security).

4. **Generate Project**:
  - Let the IDE or Spring Initializr generate the project structure and necessary files based on your configurations.

5. **Project Structure**:
  - Once the project is created, you'll see the default project structure with source code directories (`src/main/java` for Java classes, `src/main/resources` for resources, etc.).

6. **Add Application Code**:
  - Start by creating your main application class annotated with `@SpringBootApplication`.
  - Define controllers, services, repositories, and other necessary components for your application.

7. **Configure Application Properties**:
  - Customize application properties such as server port, database connection details, etc., in the `application.properties` or `application.yml` file.

8. **Write Unit Tests**:
  - Create unit tests using JUnit or TestNG to ensure the correctness of your application's functionality.

9. **Build and Run**:
  - Build your project using Maven or Gradle commands (`mvn clean install` or `./gradlew build`).
  - Run your Spring Boot application either from the IDE or using the generated JAR file (`java -jar <your-project>.jar`).

10. **Test and Debug**:
  - Test your application by accessing endpoints, verifying data operations, etc.
  - Debug any issues that arise during testing and make necessary adjustments to your code.

11. **Documentation and Deployment**:
  - Document your project's architecture, APIs, and configurations.
  - Deploy your Spring Boot application to your desired environment (e.g., local, cloud) following deployment best practices.

Following these steps will help you set up and start a Spring Boot project from scratch, allowing you to develop robust and scalable applications using the Spring framework.
- ### `@Controller` vs `@RestController`
`@Controller` and `@RestController` are both annotations used in Spring MVC framework for defining controller classes. However, they have different purposes and behaviors:

- `@Controller`: This annotation is used to define a class as a controller in a Spring MVC application. It typically handles HTTP requests and generates HTTP responses. Methods inside a `@Controller` class return a view name or a `ModelAndView` object, which resolves to a view.

- `@RestController`: This annotation is a specialized version of `@Controller` and is typically used in RESTful web services. It combines `@Controller` and `@ResponseBody` annotations. Methods inside a `@RestController` class return domain objects directly, which are automatically converted to JSON or XML response by Spring.

Here's a breakdown of their differences:

1. **Response Type**:
  - `@Controller`: Methods return a view name or a `ModelAndView` object.
  - `@RestController`: Methods return domain objects, which are converted to JSON or XML response.

2. **Usage**:
  - `@Controller`: Used for handling traditional web applications where views are rendered on the server-side.
  - `@RestController`: Used for building RESTful APIs where data is exchanged in JSON or XML format.

3. **Typical Return Types**:
  - `@Controller`: `String` (view name), `ModelAndView`, `String` (JSON/XML).
  - `@RestController`: `Object`, `List`, `Map`, `ResponseEntity`, etc.

4. **Response Body Annotation**:
  - `@Controller`: Requires `@ResponseBody` annotation on methods or at class level to return data in JSON/XML format.
  - `@RestController`: Automatically applies `@ResponseBody` to all methods, meaning every method returns data in JSON/XML format by default.

In summary, use `@Controller` for traditional web applications where views are rendered on the server-side, and use `@RestController` for building RESTful APIs where data is exchanged in JSON or XML format without the need for server-side rendering of views.
- ### `@PathVariable` vs `@RequestParam`
- `@PathVariable` and `@RequestParam` are both annotations used in Spring MVC framework to extract data from the request URL or query parameters, but they are used for different purposes:

- `@PathVariable`: This annotation is used to extract values from the URI template and bind them to method parameters. It is typically used to capture values from parts of the URL, such as path segments.

- `@RequestParam`: This annotation is used to extract query parameters from the request URL and bind them to method parameters. It is typically used to capture values from the query string of a URL.

Here's a breakdown of their differences:

1. **Usage**:
  - `@PathVariable`: Used to extract values from parts of the URL (path segments).
  - `@RequestParam`: Used to extract values from query parameters in the URL.

2. **Syntax**:
  - `@PathVariable`: Applied to a method parameter and used to specify the name of the path variable being extracted.
  - `@RequestParam`: Applied to a method parameter and used to specify the name of the query parameter being extracted. It also has additional attributes like `required`, `defaultValue`, etc.

3. **URL Format**:
  - `@PathVariable`: Typically used in RESTful APIs with URLs containing path segments, such as `/users/{userId}`.
  - `@RequestParam`: Used with URLs containing query parameters, such as `/search?query=example`.

4. **Example**:
  - `@PathVariable`: `@GetMapping("/users/{userId}") public User getUserById(@PathVariable Long userId) {...}`
  - `@RequestParam`: `@GetMapping("/search") public List<Book> searchBooks(@RequestParam String query) {...}`

In summary, use `@PathVariable` when you need to extract values from path segments in the URL, and use `@RequestParam` when you need to extract values from query parameters in the URL.
- ### `@RequestBody` vs `@ResponseBody`
`@RequestBody` and `@ResponseBody` are annotations used in Spring MVC to handle HTTP request and response bodies. They are used for different purposes:

- `@RequestBody`: This annotation is used to bind the HTTP request body to a method parameter or method-level parameter in a controller. It indicates that a method parameter should be bound to the body of the HTTP request. When Spring receives an HTTP request, it will attempt to convert the request body into the specified method parameter type.

- `@ResponseBody`: This annotation is used to indicate that the return value of a controller method should be bound to the body of the HTTP response. It tells Spring MVC that the object returned from the method should be serialized directly into the response body.

Here's a breakdown of their differences:

1. **Usage**:
  - `@RequestBody`: Used to bind the HTTP request body to a method parameter.
  - `@ResponseBody`: Used to bind the return value of a method to the HTTP response body.

2. **Direction**:
  - `@RequestBody`: Deserializes the request body to a Java object.
  - `@ResponseBody`: Serializes the method return value to the response body.

3. **Purpose**:
  - `@RequestBody`: Used when you want to extract data from the request body, typically used in POST or PUT requests.
  - `@ResponseBody`: Used when you want to return data in the response body, typically used to return JSON or XML data.

4. **Example**:
  - `@RequestBody`: `@PostMapping("/create") public ResponseEntity<User> createUser(@RequestBody User user) {...}`
  - `@ResponseBody`: `@GetMapping("/user/{userId}") public ResponseEntity<User> getUserById(@PathVariable Long userId) {...}`

In summary, `@RequestBody` is used to extract data from the request body, while `@ResponseBody` is used to return data in the response body. They are often used together to create RESTful APIs in Spring MVC.
- ### How to use `GetMapping`, `PutMapping`, `PostMapping`, `DeleteMapping`, `RequestMapping`
These are annotations provided by Spring Framework for mapping HTTP requests to handler methods in your controller classes. Here's a brief overview of each:

- `@GetMapping`: This annotation is a shortcut for `@RequestMapping(method = RequestMethod.GET)`. It is used to map HTTP GET requests onto specific handler methods. It's commonly used for read-only operations.

- `@PutMapping`: This annotation is a shortcut for `@RequestMapping(method = RequestMethod.PUT)`. It is used to map HTTP PUT requests onto specific handler methods. It's commonly used for updating resources.

- `@PostMapping`: This annotation is a shortcut for `@RequestMapping(method = RequestMethod.POST)`. It is used to map HTTP POST requests onto specific handler methods. It's commonly used for creating new resources.

- `@DeleteMapping`: This annotation is a shortcut for `@RequestMapping(method = RequestMethod.DELETE)`. It is used to map HTTP DELETE requests onto specific handler methods. It's commonly used for deleting resources.

- `@RequestMapping`: This annotation is more general and can be used to map any HTTP request method (GET, POST, PUT, DELETE, etc.) onto specific handler methods. You specify the HTTP method using the `method` attribute. It's commonly used when you need to support multiple HTTP methods for the same endpoint.

Here's an example of how to use these annotations:

```java
@RestController
@RequestMapping("/api/users")
public class UserController {

    @GetMapping("/{id}")
    public ResponseEntity<User> getUserById(@PathVariable Long id) {
        // Get user logic
    }

    @PostMapping
    public ResponseEntity<User> createUser(@RequestBody User user) {
        // Create user logic
    }

    @PutMapping("/{id}")
    public ResponseEntity<User> updateUser(@PathVariable Long id, @RequestBody User user) {
        // Update user logic
    }

    @DeleteMapping("/{id}")
    public ResponseEntity<Void> deleteUser(@PathVariable Long id) {
        // Delete user logic
    }
}
```

In this example, different HTTP methods are mapped to corresponding handler methods in the `UserController` class using the respective mapping annotations.

- ### What is Spring Actuator
Spring Boot Actuator is a subproject of Spring Boot that provides built-in production-ready features to help you monitor and manage your application. It includes various endpoints and features that allow you to monitor and interact with your Spring Boot application at runtime. Some of the key features provided by Spring Boot Actuator include:

1. **Health Check**: Actuator provides a health indicator endpoint (`/actuator/health`) that reports the application's health status. It can be used by monitoring systems to determine if the application is running correctly.

2. **Metrics**: Actuator gathers various metrics about your application, such as memory usage, CPU usage, garbage collection statistics, HTTP request metrics, database connection pool metrics, etc. These metrics can be exposed via endpoints (`/actuator/metrics`) and integrated with monitoring systems like Prometheus or Graphite.

3. **Endpoints**: Actuator exposes several management endpoints (`/actuator`) that allow you to interact with the application at runtime. For example, you can retrieve environment information, view configuration properties, dump thread stacks, shutdown the application gracefully, etc.

4. **Auditing and Logging**: Actuator provides endpoints for auditing and logging (`/actuator/auditevents` and `/actuator/logfile`), allowing you to monitor security-related events and view application logs.

5. **Environment Information**: Actuator provides an endpoint (`/actuator/env`) to retrieve information about the application's environment, including properties, system variables, and other details.

6. **Custom Endpoints**: Actuator allows you to create custom management endpoints to expose application-specific information or perform custom actions.

Overall, Spring Boot Actuator enhances the manageability and observability of Spring Boot applications, making it easier to monitor, manage, and troubleshoot them in production environments.

- ### How to achieve async in Spring Boot application
In a Spring Boot application, you can achieve asynchronous processing using Spring's `@Async` annotation along with `@EnableAsync` annotation on your configuration class. Here's how to do it:

1. **Enable Async Support**: First, you need to enable asynchronous processing in your Spring Boot application. You can do this by annotating your configuration class with `@EnableAsync`. This annotation tells Spring to enable support for asynchronous method execution.

    ```java
    import org.springframework.context.annotation.Configuration;
    import org.springframework.scheduling.annotation.EnableAsync;

    @Configuration
    @EnableAsync
    public class AppConfig {
        // Other configurations
    }
    ```

2. **Create Async Methods**: Next, you need to define methods that you want to execute asynchronously. Annotate these methods with `@Async`.

    ```java
    import org.springframework.scheduling.annotation.Async;
    import org.springframework.stereotype.Service;

    @Service
    public class MyService {

        @Async
        public void asyncMethod() {
            // Asynchronous logic here
        }
    }
    ```

3. **Invoke Async Methods**: You can now invoke the asynchronous methods from any other component in your application.

    ```java
    import org.springframework.beans.factory.annotation.Autowired;
    import org.springframework.stereotype.Component;

    @Component
    public class MyComponent {

        @Autowired
        private MyService myService;

        public void invokeAsyncMethod() {
            // This method call will be executed asynchronously
            myService.asyncMethod();
        }
    }
    ```

With these configurations, any method annotated with `@Async` will be executed asynchronously in a separate thread pool managed by Spring. This allows you to perform long-running or non-blocking tasks without blocking the main thread of your application. Make sure to handle exceptions properly within asynchronous methods, as they won't be propagated to the calling thread by default.

### Homework 10

### Question List

- ### How does Spring handle exceptions
Spring provides several mechanisms for handling exceptions in Spring applications:

1. **`@ExceptionHandler`**: You can use `@ExceptionHandler` annotation to handle exceptions within a specific controller or controller advice. This allows you to define methods that will be invoked when a specific exception occurs within the annotated class.

   ```java
   @ControllerAdvice
   public class GlobalExceptionHandler {

       @ExceptionHandler(Exception.class)
       public ResponseEntity<ErrorResponse> handleException(Exception ex) {
           // Custom error response
           ErrorResponse errorResponse = new ErrorResponse("Internal Server Error", ex.getMessage());
           return new ResponseEntity<>(errorResponse, HttpStatus.INTERNAL_SERVER_ERROR);
       }
   }
   ```

2. **`@ControllerAdvice`**: You can define global exception handling logic by annotating a class with `@ControllerAdvice`. This allows you to define methods that will be invoked to handle exceptions thrown from any controller in your application.

3. **`HandlerExceptionResolver`**: Spring provides `HandlerExceptionResolver` interface that allows you to define custom exception handling logic. You can implement this interface to create custom exception resolvers that handle exceptions in a flexible manner.

4. **`@ResponseStatus`**: You can annotate an exception class with `@ResponseStatus` to specify the HTTP status code that should be returned when the exception occurs.

   ```java
   @ResponseStatus(HttpStatus.NOT_FOUND)
   public class ResourceNotFoundException extends RuntimeException {
       // Exception logic
   }
   ```

5. **`@ControllerAdvice` with `ResponseEntityExceptionHandler`**: Spring Boot provides a convenient way to handle exceptions using `ResponseEntityExceptionHandler` class in combination with `@ControllerAdvice`. This class provides default exception handling logic for common Spring MVC exceptions.

6. **Global Error Page**: You can configure Spring to display a global error page when unhandled exceptions occur. This can be done by defining an error page in the `web.xml` file or using the `@ControllerAdvice` annotation.

By using these mechanisms, you can handle exceptions gracefully in your Spring applications, providing meaningful error responses to clients and improving the overall robustness of your application.

- ### How does Spring validate data
Spring provides several ways to validate data in a Spring application:

1. **JSR-380 (Bean Validation 2.0)**: Spring supports the standard JSR-380 for bean validation. You can annotate your model classes with validation annotations such as `@NotNull`, `@Size`, `@Email`, etc., to specify constraints on the data.

   ```java
   public class User {

       @NotNull
       @Size(min = 2, max = 30)
       private String username;

       @NotNull
       @Email
       private String email;

       // Getters and setters
   }
   ```

   Then, you can use `@Valid` annotation along with `BindingResult` to validate the data in your controller methods.

   ```java
   @PostMapping("/users")
   public ResponseEntity<User> createUser(@Valid @RequestBody User user, BindingResult result) {
       if (result.hasErrors()) {
           // Handle validation errors
       }
       // Process the user data
   }
   ```

2. **Programmatic Validation**: You can implement `Validator` interface to create custom validators for your model classes. This gives you more flexibility to define complex validation logic beyond what can be expressed with annotations.

   ```java
   public class UserValidator implements Validator {

       @Override
       public boolean supports(Class<?> clazz) {
           return User.class.equals(clazz);
       }

       @Override
       public void validate(Object target, Errors errors) {
           User user = (User) target;
           if (user.getUsername().length() < 5) {
               errors.rejectValue("username", "Size.userForm.username");
           }
           // More validation logic
       }
   }
   ```

   You can then use `Validator` interface to perform validation programmatically.

3. **Global Error Handling**: Spring provides mechanisms like `@ControllerAdvice` and `HandlerExceptionResolver` to handle validation errors globally and customize the error responses.

By using these validation mechanisms, you can ensure that the data in your Spring application is validated according to your requirements and provide meaningful error messages to users when validation fails.

- ### How does Spring do the log
Spring uses the popular logging framework SLF4J (Simple Logging Facade for Java) for logging. SLF4J provides a simple facade for various logging frameworks like Log4j, Logback, JDK logging, etc., allowing developers to switch between different logging implementations without changing the application code.

Here's how Spring performs logging:

1. **Logger Declaration**: In Spring components such as controllers, services, repositories, etc., developers declare a logger using the SLF4J API. This is typically done as a class-level field:

    ```java
    import org.slf4j.Logger;
    import org.slf4j.LoggerFactory;

    public class MyClass {
        private static final Logger logger = LoggerFactory.getLogger(MyClass.class);

        // Class methods
    }
    ```

2. **Logging Statements**: Developers use the logger instance to log messages at various levels (debug, info, warn, error) depending on the severity of the message:

    ```java
    logger.debug("This is a debug message");
    logger.info("This is an info message");
    logger.warn("This is a warning message");
    logger.error("This is an error message");
    ```

3. **Configuration**: The logging behavior, including the logging level, log format, log destination (console, file, database), etc., is configured through an external configuration file such as `logback.xml`, `log4j.properties`, or `application.properties`. This configuration file is typically located in the `src/main/resources` directory of the Spring application.

   For example, in `logback.xml`:

    ```xml
    <configuration>
        <appender name="consoleAppender" class="ch.qos.logback.core.ConsoleAppender">
            <encoder>
                <pattern>%d{HH:mm:ss.SSS} [%thread] %-5level %logger{36} - %msg%n</pattern>
            </encoder>
        </appender>

        <root level="INFO">
            <appender-ref ref="consoleAppender" />
        </root>
    </configuration>
    ```

   This configuration sets the logging level to INFO and configures the console appender with a specific log message format.

4. **Logging Facade Binding**: At runtime, SLF4J binds to the actual logging implementation (e.g., Logback, Log4j) that is specified in the application's classpath. The logging framework then handles the actual logging based on the configured behavior.

By using SLF4J and an underlying logging implementation, Spring provides a flexible and configurable logging mechanism that allows developers to easily integrate logging into their applications and customize the logging behavior according to their requirements.

- ### Cache hit vs cache miss
- Cache hit and cache miss are terms used in caching systems to describe whether a requested piece of data is found in the cache (hit) or not (miss). Here's an explanation of each:

- **Cache Hit**:
  - Definition: A cache hit occurs when the requested data is found in the cache.
  - Scenario: When a piece of data is requested, the caching system checks if it's already stored in the cache. If it is, the data is retrieved from the cache, and the request is considered a cache hit.
  - Significance: Cache hits are desirable because they indicate that the data is readily available in the cache, leading to faster access times and reduced latency compared to retrieving the data from the original data source.

- **Cache Miss**:
  - Definition: A cache miss occurs when the requested data is not found in the cache.
  - Scenario: If the requested data is not present in the cache, it needs to be retrieved from the original data source (e.g., a database, file system). This retrieval process is slower compared to accessing data from the cache and results in a cache miss.
  - Significance: Cache misses are less desirable because they result in longer access times and increased latency. However, they are inevitable and can occur due to various reasons, such as cache eviction, cache expiration, or accessing data that has not been cached before.

In summary, cache hits indicate successful data retrieval from the cache, leading to improved performance, while cache misses indicate that the requested data needs to be fetched from the original data source, resulting in potentially slower access times. Efficient caching strategies aim to maximize cache hits while minimizing cache misses to optimize overall system performance.
- ### Do some research on Redis and have a basic understanding
Redis is an open-source, in-memory data structure store that is used as a database, cache, and message broker. It is known for its speed, versatility, and support for various data structures. Here are some key points to understand about Redis:

- **In-Memory Data Store**: Redis stores data primarily in memory, which allows for extremely fast read and write operations. This makes it well-suited for use cases where low-latency access to data is critical.

- **Key-Value Store**: Redis is a key-value store, meaning that data is accessed using keys. Each key is associated with a value, which can be a wide range of data types, including strings, lists, sets, hashes, and more.

- **Support for Data Structures**: Redis supports various data structures, such as strings, lists, sets, sorted sets, hashes, bitmaps, and hyperloglogs. This versatility allows developers to choose the most appropriate data structure for their specific use cases.

- **Persistence Options**: Although Redis primarily stores data in memory, it also offers persistence options to ensure data durability. Redis supports different persistence mechanisms, including snapshots (RDB) and append-only log (AOF), which can be configured based on the application's requirements.

- **High Availability and Replication**: Redis supports high availability through master-slave replication. It allows for the configuration of multiple Redis instances in a master-slave setup, where data is replicated from the master to one or more slave nodes, providing fault tolerance and data redundancy.

- **Pub/Sub Messaging**: Redis includes support for publish/subscribe messaging, allowing clients to subscribe to channels and receive messages published to those channels. This feature enables building real-time messaging systems, chat applications, and more.

- **Lua Scripting**: Redis provides Lua scripting capabilities, allowing developers to execute custom scripts directly within the Redis server. This feature enables complex operations and atomic transactions, enhancing Redis's flexibility and extensibility.

- **Cluster Mode**: Redis Cluster is a distributed implementation of Redis that provides automatic partitioning and replication across multiple Redis nodes. It offers scalability and fault tolerance by distributing data across the cluster and handling node failures gracefully.

Overall, Redis is a powerful and versatile in-memory data store that is widely used in various applications, including caching, session management, real-time analytics, message queuing, and more. Its simplicity, performance, and rich feature set make it a popular choice for developers seeking fast and scalable data storage solutions.
- ### SQL vs NoSQL database
SQL (Structured Query Language) and NoSQL (Not Only SQL) are two broad categories of database management systems (DBMS) that differ in their data models, querying languages, scalability, and use cases. Here's a comparison of SQL and NoSQL databases:

- **Data Model**:
  - SQL databases use a relational data model, where data is organized into tables with rows and columns. Tables have predefined schemas, and relationships between tables are established using foreign keys.
  - NoSQL databases support various data models, including document, key-value, columnar, and graph. These models are more flexible and can accommodate semi-structured and unstructured data.

- **Query Language**:
  - SQL databases use SQL (Structured Query Language) for querying and manipulating data. SQL is a standardized language with well-defined syntax and semantics.
  - NoSQL databases typically have their own query languages or APIs tailored to the specific data model. These languages may not be as standardized as SQL but are designed to efficiently query and manipulate data in the chosen data model.

- **Scalability**:
  - SQL databases are traditionally vertically scalable, meaning they scale up by adding more resources (CPU, memory, storage) to a single server. This approach has limits in terms of scalability.
  - NoSQL databases are designed for horizontal scalability, allowing them to scale out by adding more servers to a distributed cluster. This approach enables NoSQL databases to handle large volumes of data and high concurrency more effectively.

- **Schema Flexibility**:
  - SQL databases have rigid schemas, where the structure of the data must be defined upfront. Altering the schema can be complex and may require downtime.
  - NoSQL databases offer schema flexibility, allowing developers to store data without a predefined schema or to modify the schema dynamically as needed. This flexibility is well-suited for agile development and evolving data requirements.

- **ACID vs BASE**:
  - SQL databases typically adhere to the ACID (Atomicity, Consistency, Isolation, Durability) properties, ensuring data integrity and transactional consistency.
  - NoSQL databases often follow the BASE (Basically Available, Soft state, Eventually consistent) model, prioritizing availability and partition tolerance over strong consistency. This makes NoSQL databases more suitable for distributed systems and high availability scenarios.

- **Use Cases**:
  - SQL databases are commonly used for transactional applications, relational data modeling, and applications with complex queries and joins.
  - NoSQL databases are preferred for applications with large-scale data storage, real-time analytics, high write throughput, and distributed systems where horizontal scalability is essential.

In summary, the choice between SQL and NoSQL databases depends on factors such as data structure, scalability requirements, query complexity, and the specific needs of the application. Each type of database has its strengths and weaknesses, and the optimal choice often depends on the use case and the trade-offs that need to be made.

- ### What is database normalization
Database normalization is the process of organizing the attributes and tables of a relational database to minimize redundancy and dependency. The main goal of normalization is to structure data in a way that ensures data integrity, eliminates data anomalies, and reduces the risk of data corruption.

Normalization is typically achieved through a series of steps, known as normal forms, each representing a higher level of normalization. The most common normal forms are:

1. **First Normal Form (1NF)**:
  - Eliminate repeating groups: Ensure that each column contains atomic values, and there are no repeating groups of columns.
  - Ensure each row is unique: Identify a primary key for each table to uniquely identify each row.

2. **Second Normal Form (2NF)**:
  - Meet the requirements of 1NF.
  - Remove partial dependencies: Ensure that each non-key attribute is fully functionally dependent on the entire primary key.

3. **Third Normal Form (3NF)**:
  - Meet the requirements of 2NF.
  - Remove transitive dependencies: Ensure that no non-key attribute is dependent on another non-key attribute.

There are additional normal forms beyond 3NF, such as Boyce-Codd Normal Form (BCNF) and Fourth Normal Form (4NF), each addressing specific types of dependencies and anomalies.

Database normalization helps in improving database design by:
- Reducing data redundancy: Storing data only once eliminates redundant information and conserves storage space.
- Improving data consistency: With data stored in a structured manner, updates and modifications are less likely to result in inconsistencies.
- Simplifying database maintenance: A well-normalized database is easier to maintain and modify, as changes can be localized and applied without affecting other parts of the database.

However, it's essential to strike a balance between normalization and performance, as excessive normalization can lead to increased complexity and slower query performance in some cases. Therefore, normalization should be applied judiciously based on the specific requirements and characteristics of the application and data model.

- ### Vertical scaling vs horizontal scaling
- Vertical scaling and horizontal scaling are two approaches to increasing the capacity and performance of a system, particularly in the context of managing resources such as servers, databases, or network bandwidth.

- **Vertical Scaling (Scale-Up)**:
  - **Definition**: Vertical scaling involves increasing the capacity of a single resource, such as upgrading the CPU, RAM, or storage capacity of a server.
  - **Pros**:
    - Simplified management: Adding resources to a single machine is typically easier to manage than distributing resources across multiple machines.
    - Lower initial cost: Scaling up may require purchasing higher-end hardware, but it can be more cost-effective in the short term compared to horizontal scaling.
  - **Cons**:
    - Limited scalability: There is a physical limit to how much you can scale up a single machine, and eventually, you may reach the maximum capacity of the hardware.
    - Single point of failure: If the single machine fails, it can lead to downtime for the entire system.

- **Horizontal Scaling (Scale-Out)**:
  - **Definition**: Horizontal scaling involves adding more machines or instances to distribute the workload across multiple resources.
  - **Pros**:
    - Improved scalability: Horizontal scaling allows you to add more resources as needed, making it more suitable for handling large-scale applications and increasing capacity over time.
    - Fault tolerance: With multiple instances, if one machine fails, the workload can be redistributed to other instances, reducing the impact of failures.
  - **Cons**:
    - Increased complexity: Managing a distributed system with multiple instances can be more complex and require additional tools for load balancing, data synchronization, and fault tolerance.
    - Higher initial cost: Setting up and maintaining multiple instances may require more initial investment in infrastructure and ongoing operational costs.

In summary, vertical scaling involves adding resources to a single machine, while horizontal scaling involves adding more machines to distribute the workload. The choice between vertical and horizontal scaling depends on factors such as the scalability requirements, budget constraints, and the nature of the application or workload. Often, a combination of both vertical and horizontal scaling strategies may be employed to achieve optimal performance and scalability.
- ### What is ACID
- ACID is an acronym that stands for Atomicity, Consistency, Isolation, and Durability. It is a set of properties that ensure the reliability and integrity of transactions in a database management system (DBMS). Here's a brief explanation of each component:

- **Atomicity**: Atomicity ensures that a transaction is treated as a single, indivisible unit of work. This means that either all the operations within the transaction are successfully completed, or none of them are. If any part of the transaction fails, the entire transaction is rolled back to its original state, ensuring data integrity.

- **Consistency**: Consistency ensures that the database remains in a consistent state before and after the execution of a transaction. In other words, any changes made by a transaction must adhere to all the constraints, rules, and validations defined in the database schema. This prevents the database from entering an inconsistent state, where data integrity may be compromised.

- **Isolation**: Isolation ensures that the execution of one transaction is isolated from the execution of other transactions concurrently accessing the same data. Each transaction operates as if it were the only transaction running on the system. Isolation prevents interference between transactions, such as dirty reads, non-repeatable reads, and phantom reads, which can lead to data inconsistency.

- **Durability**: Durability guarantees that once a transaction is committed, its changes are permanently saved and cannot be undone, even in the event of a system failure (such as a power outage or hardware failure). The changes made by committed transactions are stored in a durable medium (such as disk storage) and remain intact even after the system restarts. This ensures that data is not lost and maintains the database's reliability.

Together, these four properties ensure that transactions in a database system are reliable, maintain data integrity, and provide the necessary guarantees for data consistency and durability, even in the face of system failures or concurrent access by multiple users. ACID compliance is a fundamental requirement for many applications and is typically provided by relational database management systems (RDBMS) and other transactional data stores.
- ### What is CAP
CAP, often referred to as the CAP theorem, is a fundamental principle in distributed systems that highlights the trade-offs between consistency, availability, and partition tolerance. It states that in any distributed system, it is impossible to simultaneously guarantee all three of the following properties:

1. **Consistency**: Every read receives the most recent write or an error. In other words, all nodes in the system have the same data at the same time, ensuring that clients always see a consistent view of the data.

2. **Availability**: Every request receives a response, without guaranteeing that the data returned is the latest. In other words, the system remains operational and responsive even in the presence of failures.

3. **Partition Tolerance**: The system continues to operate despite network partitions (i.e., communication failures) that prevent some nodes from communicating with each other. In other words, the system can withstand network failures and still maintain its functionality.

According to the CAP theorem, a distributed system can ensure only two out of the three properties simultaneously. This means that in the event of a network partition (P), the system must choose between maintaining consistency (C) or availability (A). The choice between consistency and availability is often influenced by the specific requirements of the application and the system's design goals.

It's essential to note that the CAP theorem does not imply that one needs to sacrifice one of the properties entirely but rather suggests that under certain conditions, trade-offs must be made. Different distributed databases and systems adopt various strategies to achieve the desired balance between consistency, availability, and partition tolerance based on the specific needs and use cases of the application.



