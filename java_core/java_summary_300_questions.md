question list
### 1. What's new in Java 8
### 2. What is the difference between JDK, JRE, and JVM?
### 3. How many types of memory areas are allocated by JVM?
### 4. What is classloader?
### 5. What if I write static public void instead of public static void?
### 6. What is the default value of the local variables?
### 7. What are the various access specifiers in Java?
### 7. What is the static variable?
### 8. What is the purpose of static methods and variables?
### 8. What are the restrictions that are applied to the Java static methods?
### 9. What is an object?
### 10. What is the constructor?
### 11. Is constructor inherited?
### 12. Can you make a constructor final?
### 13. Can we overload the constructors?
### 13. Can we make constructors static?
### 13. Can we override the static methods?
### 13. What if the static modifier is removed from the signature of the main method?
### 13. What is the difference between static (class) method and instance method?
### 15. Can we make the abstract methods static in Java?
### 15. Can we declare the static variables and methods in an abstract class?



### 1. What's new in Java 8
Java 8 introduced several significant features and enhancements to the language. Here are some key highlights of what's new in Java 8:

1. **Lambda Expressions:** Lambda expressions enable you to treat functionality as a method argument or to create anonymous inner classes more concisely. They facilitate functional programming in Java.

2. **Stream API:** The Stream API provides a new abstraction for processing data in a functional style. It allows for declarative operations on sequences of elements, such as filtering, mapping, reducing, and more.

3. **Functional Interfaces:** Java 8 introduced the `@FunctionalInterface` annotation, which can be used to indicate that an interface is intended to be a functional interface, containing exactly one abstract method.

4. **Default Methods:** Interfaces in Java 8 can have default methods, which provide a way to add new methods to interfaces without breaking existing implementations.

5. **Optional:** The `Optional` class was introduced to address the issue of null values. It provides a container object which may or may not contain a non-null value, avoiding null pointer exceptions.

6. **Method References:** Method references provide a shorthand notation for lambda expressions representing methods or constructors that can be invoked.

7. **Date and Time API:** Java 8 introduced a new date and time API in the `java.time` package to overcome the shortcomings of the old `java.util.Date` and `java.util.Calendar` classes.

8. **CompletableFuture:** The `CompletableFuture` class was introduced to represent a future result of an asynchronous computation. It provides a way to perform asynchronous tasks and handle their results asynchronously.

9. **Parallel Array Sorting:** Java 8 introduced new methods in the `Arrays` class for parallel sorting of arrays using the fork/join framework, improving performance on multi-core systems.

10. **Nashorn JavaScript Engine:** Java 8 included a new lightweight JavaScript engine called Nashorn, which provides better performance and compatibility with modern JavaScript standards.

### 2. What is the difference between JDK, JRE, and JVM?