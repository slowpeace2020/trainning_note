# Day6
## Design pattern
### Creational Pattern
#### Singleton Pattern
    - only one object gets created

    - use case: 
        - hardware interface access
        - Logger
        - Configuration File
        - Thread Pool
        - Cache

Here's the completed code snippet implementing lazy loading with double-check locking for a singleton class using the volatile keyword:

```java
public class Singleton2 {
    // volatile to prevent instruction reorder
    private static volatile Singleton2 instance;

    private Singleton2() {
        // Private constructor to prevent instantiation
    }

    public static Singleton2 getInstance() {
        // Double-check locking for lazy initialization
        if (instance == null) {
            synchronized (Singleton2.class) {
                if (instance == null) {
                    instance = new Singleton2();
                    // 1 create instance reference
                    // 2 new singleton();
                    // 3 instance reference points to instance object,
                    // 1 -> 2 -> 3
                    // 1 -> 3 -> 2
                }
            }
        }
        return instance;
    }
}
```

In this implementation:
- The volatile keyword ensures that changes to the instance variable are visible to all threads, preventing instruction reordering that could lead to an unsafe publication of the singleton instance.
- Double-check locking is used to minimize the performance impact of synchronization by first checking if the instance is null outside the synchronized block, and then acquiring the lock only if necessary to create the singleton instance.
- Inside the synchronized block, another null check is performed to prevent multiple threads from creating multiple instances of the singleton when they access the getInstance() method concurrently.
- Finally, the instance variable is returned to provide access to the singleton instance.
- 
### Factory Pattern

The Factory Pattern is a creational design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created. It defines an interface for creating an object, but allows subclasses to alter the type of objects that will be instantiated.

### Prototype Pattern

The Prototype Pattern is a creational design pattern that is used to create a new object by cloning an existing object, known as the prototype. It allows for the creation of new objects by copying an existing object, thus avoiding the need for subclassing.

### Structural Pattern

Structural patterns are concerned with object composition or, in other words, how objects are made up or structured.

#### Decorator Pattern

The Decorator Pattern is a structural design pattern that allows behavior to be added to individual objects, either statically or dynamically, without affecting the behavior of other objects from the same class. It is used to add new functionality to an existing object without altering its structure.

#### Static Proxy Pattern

The Static Proxy Pattern is a structural design pattern that involves creating a proxy object that acts as a placeholder for another object. This proxy controls access to the original object, allowing you to add behavior before or after the request is passed to the original object.

#### Dynamic Proxy Pattern

The Dynamic Proxy Pattern is a structural design pattern that allows an object to delegate method calls to another object at runtime. It provides a way to create a proxy class at runtime, which implements a list of interfaces and delegates method calls to an underlying target object.

##### Java Reflection

Java Reflection is a feature that allows Java code to inspect and manipulate classes, interfaces, fields, and methods at runtime. It provides a way to inspect classes, interfaces, fields, and methods at runtime without knowing their names at compile time. This allows for dynamic loading of classes, instantiation of objects, and invocation of methods at runtime.

### Behavioral Pattern

Behavioral patterns are concerned with the interaction and communication between objects.

#### Observer Pattern

The Observer Pattern is a behavioral design pattern where an object, known as the subject, maintains a list of its dependents, called observers, and notifies them of any state changes, usually by calling one of their methods. It is used to define a one-to-many dependency between objects, so that when one object changes state, all its dependents are notified and updated automatically.

#### Interpreter Pattern

The Interpreter Pattern is a behavioral design pattern that defines a grammar for a language and provides an interpreter to interpret sentences in the language. It is used to define a language grammar and provide a way to evaluate sentences in the language.

#### Iterator Pattern

The Iterator Pattern is a behavioral design pattern that provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation. It is used to access the elements of a collection object sequentially without exposing its internal structure.

These design patterns provide solutions to commonly occurring problems in software design, helping developers to create flexible, maintainable, and reusable software components.




