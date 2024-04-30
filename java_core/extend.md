## Proxy Pattern
The Proxy Pattern is a structural design pattern that provides a surrogate or placeholder for another object to control access to it. The Proxy Pattern allows you to create a wrapper around an object, intercepting and controlling access to its methods and properties. There are two main types of Proxy Patterns: Static Proxy and Dynamic Proxy.

### Static Proxy Pattern:
In the Static Proxy Pattern, the proxy class is created manually and exists alongside the real subject class. The proxy class implements the same interface as the subject class, intercepts method calls to the subject, and adds additional behavior before or after forwarding the call to the real subject.

#### Use Cases:
- **Security**: Control access to sensitive methods or resources by adding authentication, authorization, or logging logic in the proxy.
- **Caching**: Implement caching of expensive method calls in the proxy to improve performance.
- **Remote Access**: Implement communication with a remote server by sending requests through a proxy, handling network-related concerns such as serialization and deserialization.

#### Pros:
- **Controlled Access**: Allows for controlled access to the subject object, enabling additional functionality to be added before or after method calls.
- **Separation of Concerns**: Separates concerns related to access control, caching, or remote communication from the core functionality of the subject class.
- **Security**: Provides a layer of security by intercepting method calls and enforcing access control policies.

#### Cons:
- **Boilerplate Code**: Requires manually creating a proxy class for each subject class, leading to potential code duplication and maintenance overhead.
- **Tight Coupling**: The proxy class is tightly coupled to the subject class, making it difficult to change or replace the subject without modifying the proxy.

### Dynamic Proxy Pattern:
In the Dynamic Proxy Pattern, the proxy class is generated dynamically at runtime using reflection. The Java language provides support for dynamic proxies through the `java.lang.reflect.Proxy` class and the `InvocationHandler` interface. Dynamic proxies allow you to intercept method calls to the subject class at runtime without the need to create a separate proxy class.

#### Use Cases:
- **Logging**: Implement logging of method calls by intercepting them with a dynamic proxy and logging information before or after invoking the real method.
- **Performance Monitoring**: Measure method execution time or resource usage by intercepting method calls with a dynamic proxy and collecting performance metrics.
- **Dynamic Behavior**: Implement dynamic behavior modification by intercepting and modifying method calls at runtime based on certain conditions.

#### Pros:
- **Dynamic Generation**: Allows for the dynamic generation of proxy classes at runtime, eliminating the need for manually creating proxy classes for each subject class.
- **Reduced Boilerplate Code**: Reduces boilerplate code by eliminating the need to create separate proxy classes, resulting in cleaner and more concise code.
- **Flexible Composition**: Enables flexible composition of interceptors and handlers, allowing for complex behavior modification at runtime.

#### Cons:
- **Performance Overhead**: Dynamic proxies may introduce some performance overhead compared to static proxies due to reflection and method invocation handling.
- **Limited Control**: Provides less control over method interception compared to static proxies, as dynamic proxies are generated based on interfaces rather than concrete classes.
- **Interface-based**: Limited to intercepting method calls on interfaces, as dynamic proxies rely on interface-based invocation. They cannot intercept calls to methods defined in concrete classes.

Overall, both Static Proxy and Dynamic Proxy Patterns provide a way to control access to objects and add additional functionality before or after method calls. The choice between static and dynamic proxies depends on the specific requirements of the application, such as performance considerations, flexibility, and ease of implementation.


## What is the default value of the local variables?
In Java, local variables are not automatically initialized with default values like instance variables are. Attempting to use a local variable before initializing it will result in a compilation error.

Local variables must be explicitly initialized before they are used. If a local variable is not explicitly initialized before it is accessed, the Java compiler will raise a compile-time error, indicating that the variable might not have been initialized.

Here's an example:

```java
public class Example {
    public static void main(String[] args) {
        int x;
        System.out.println(x); // Error: variable x might not have been initialized
    }
}
```

In this example, the variable `x` is declared but not initialized. Trying to access it before initialization results in a compilation error.

So, the default value of local variables in Java is essentially undefined, and you must explicitly assign a value to them before using them in your code.

## What is the default value of the local variables?

In Java, local variables are not automatically initialized with default values like instance variables are. Attempting to use a local variable before initializing it will result in a compilation error.

Local variables must be explicitly initialized before they are used. If a local variable is not explicitly initialized before it is accessed, the Java compiler will raise a compile-time error, indicating that the variable might not have been initialized.

Here's an example:

```java
public class Example {
    public static void main(String[] args) {
        int x;
        System.out.println(x); // Error: variable x might not have been initialized
    }
}
```

In this example, the variable `x` is declared but not initialized. Trying to access it before initialization results in a compilation error.

So, the default value of local variables in Java is essentially undefined, and you must explicitly assign a value to them before using them in your code.

