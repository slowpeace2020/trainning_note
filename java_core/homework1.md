## Homework 1

- [List vs Set](#list-vs-set)
- [LinkedList vs ArrayList](#linkedlist-vs-arraylist)
- [What is Map Interface](#what-is-map-interface)
- [How does HashMap work](#how-does-hashmap-work)
- [What is hash collision](#what-is-hash-collision)
- [What is Collections used for](#what-is-collections-used-for)
- [What is immutable class](#what-is-immutable-class)
- [HashTable vs HashMap vs ConcurrentHashmap](#hashtable-vs-hashmap-vs-concurrenthashmap)
- [String vs StringBuilder vs StringBuffer](#string-vs-stringbuilder-vs-stringbuffer)
- [Comparator vs Comparable, when to use which one](#comparator-vs-comparable-when-to-use-which-one)
- [Overriding vs overloading](#overriding-vs-overloading)
- [JRE vs JDK vs JVM](#jre-vs-jdk-vs-jvm)
- [Java 8 basic data types](#java-8-basic-data-types)
- [Primitive type, reference type](#primitive-type-reference-type)

## Homework 2

- [What is final keyword](#what-is-final-keyword)
- [Create a Student immutable class, with fields student id, first name, last name, List<Course> courses](#create-a-student-immutable-class-with-fields-student-id-first-name-last-name-list-course-courses)
- [What is volatile, transient, synchronized](#what-is-volatile-transient-synchronized)
- [throw vs throws](#throw-vs-throws)
- [final vs finally vs finalize](#final-vs-finally-vs-finalize)
- [this vs super](#this-vs-super)
- [abstract class vs interface](#abstract-class-vs-interface)
- [Jvm architecture](#jvm-architecture)
- [Java modifier scope: public, private, protected, default scope](#java-modifier-scope-public-private-protected-default-scope)
- [What is static scope](#what-is-static-scope)
- [how does classloader work](#how-does-classloader-work)

## Homework 3

- [Describe the difference between unchecked and checked exceptions in Java](#describe-the-difference-between-unchecked-and-checked-exceptions-in-java)
- [What is the difference between finally, final, and finalize in Java](#what-is-the-difference-between-finally-final-and-finalize-in-java)
- [Define try-with resource. How can you say that it differs from an ordinary try](#define-try-with-resource-how-can-you-say-that-it-differs-from-an-ordinary-try)
- [Define Runtime Exception. Describe it with the help of an example](#define-runtime-exception-describe-it-with-the-help-of-an-example)
- [What is the difference between NoClassDefFoundError and ClassNotFoundException in Java](#what-is-the-difference-between-noclassdeffounderror-and-classnotfoundexception-in-java)
- [Why should we clean up activities such as I/O resources in the finally block](#why-should-we-clean-up-activities-such-as-io-resources-in-the-finally-block)
- [Describe OutofMemoryError in exception handling](#describe-outofmemoryerror-in-exception-handling)
- [What is Generics in Java? What are the advantages of using Generics](#what-is-generics-in-java-what-are-the-advantages-of-using-generics)
- [How Generics works in Java? What is type erasure](#how-generics-works-in-java-what-is-type-erasure)
- [What is the difference between List<? extends T> and List <? super T>](#what-is-the-difference-between-list-extends-t-and-list--super-t)
- [what is Optional class (write a demo code to use ofNullable, orElse, orElseThrow method)](#what-is-optional-class-write-a-demo-code-to-use-ofnullable-orelse-orelsethrow-method)
- [what is functional interface](#what-is-functional-interface)
- [what is default method](#what-is-default-method)
- [what is the difference between Predicate, Supplier, Consumer, Function?](#what-is-the-difference-between-predicate-supplier-consumer-function)
- [write a piece of code to use the Predicate, Supplier, Consumer, Function interface](#write-a-piece-of-code-to-use-the-predicate-supplier-consumer-function-interface)
- [what is method reference](#what-is-method-reference)




## Homework  1 List (write necessary code to answer the following questions)
### List vs Set
Set is unordered and contains different elements, whereas the list is ordered and can contain the same elements in it


### LinkedList vs ArrayList
1. ArrayList
   - Resizable-array implementation of the `List` interface.
   - Provides fast random access and is very efficient for storing and accessing data.
   - Not synchronized.

2. LinkedList
   - Doubly-linked list implementation of the `List` and `Deque` interfaces.
   - Offers better performance than `ArrayList` when elements are added or removed from the middle of the list.
   - Can also be used as a queue or a stack.

### What is Map Interface
No Duplicate Keys: Each key in a Map must be unique. If a duplicate key is used in an attempt to put a value, the old value associated with that key will be overwritten with the new value.
Each Key Maps to Exactly One Value: A key can map to any value, including null (unless the Map implementation restricts null values).
Ordering: The Map interface itself does not guarantee any specific order of its elements. However, some implementations, like LinkedHashMap, maintain elements in the order they were inserted, and TreeMap sorts the keys according to their natural ordering or using a specified comparator.
How does HashMap work
HashMap uses an array-based structure internally to store its entries, which are essentially key-value pairs. Each entry in the array is a bucket that can hold zero or more entries, typically in the form of a linked list or, in more recent Java versions, as a balanced tree when buckets become too large.

When you add a key-value pair to a HashMap, it uses the key’s hashCode() method to compute an initial hash value. This hash is then transformed to reduce the impact of poor quality hash functions and to better distribute the keys across the available buckets. This transformation typically involves rehashing the initial hash to ensure a more uniform distribution of entries.

Once the hash is computed, HashMap determines the index in its array by using the hash and the length of the array.

### What is hash collision
A hash collision occurs when two distinct keys produce the same hash code or hash to the same index in a hash table, despite being different in actual value.

### What is Collections used for
Collections are used to store groups of objects. Unlike arrays, most collection classes automatically manage the size of the data structure, which means they can grow or shrink dynamically as items are added or removed.

Collections provide methods to manipulate data efficiently. Common operations include adding, removing, and updating elements. Advanced operations like sorting, shuffling, and reversing lists are also supported directly by methods in the Collections class.

Collections provide mechanisms to search for elements and filter data based on certain criteria. For example, a HashSet can be used for fast existence checks, a TreeMap can store sorted data, and a HashMap offers quick retrieval of data based on a key.

Collections can be iterated using iterator patterns provided by the framework. This makes it easy to loop through the elements of a collection, such as a list, set, or map, and perform operations on each element in a controlled way.

Collections simplify the implementation of various data access patterns, such as FIFO (First In, First Out), LIFO (Last In, First Out), and key-value pair mapping. For instance, LinkedList can be used as a queue or a stack, and HashMap provides an associative array functionality.


### What is immutable class
A type of immutable class whose instances cannot be modified after they are created. This means that once an instance of an immutable class is instantiated, its fields or state cannot change in any way. Immutable objects are useful for building reliable and secure applications, as they can simplify concurrency and offer strong guarantees against data alteration.

Final Class: The class itself is often declared final to prevent subclassing, which could potentially add mutable behavior.
Final Fields: All fields of the class are usually declared final so they can be assigned only once.
No Setter Methods: Immutable classes do not provide "setter" methods that modify fields or objects referred to by fields.
Initialization via Constructors: All fields of an immutable object are typically initialized in the constructor. Once set, these fields cannot be changed.
Deep Copies for Complex Fields: If an immutable object has fields that refer to mutable objects, such as arrays or collections, these fields should ideally point to copies of these objects, not to the original instances. This practice ensures that the mutable objects cannot be changed from outside the immutable object.
Returning Copies Instead of Original References: Any method that returns information about the object's state should return a new copy of the object, rather than a direct reference to a mutable field.


### HashTable vs HashMap vs ConcurrentHashmap
In Java, `HashTable`, `HashMap`, and `ConcurrentHashMap` are all implementations of the `Map` interface but have different characteristics and are suited to different use cases.

1. HashTable

- Thread Safety: `HashTable` is synchronized, which means it is thread-safe. Every method call is wrapped in a synchronized block, thus only one thread can access the table at a time. This can introduce a significant performance cost due to contention between threads.
- Null Keys and Values: `HashTable` does not allow null keys or null values. Attempting to use a null key or value will throw a `NullPointerException`.
- Iteration Order: It does not guarantee any specific order of the entries in the map.
- Performance: While `HashTable` is thread-safe, the coarse-grained locking strategy significantly hinders performance when high levels of concurrency are involved.
- Historical Note: `HashTable` is considered a legacy class. Much of its functionality has been superseded by `ConcurrentHashMap` in environments requiring concurrency and by `HashMap` in single-threaded applications.

2. HashMap

- Thread Safety: `HashMap` is not synchronized, which means it is not thread-safe if multiple threads modify the map concurrently without proper synchronization. It is suitable for single-threaded applications or read-only scenarios.
- Null Keys and Values: `HashMap` allows one null key and multiple null values, which provides greater flexibility than `HashTable`.
- Iteration Order: Like `HashTable`, `HashMap` does not guarantee any order of its entries. However, `LinkedHashMap` (a subclass of `HashMap`) maintains elements in the order they were inserted.
- Performance: `HashMap` provides constant-time performance for the basic operations (`get` and `put`), assuming the hash function disperses elements properly across the buckets.

3. ConcurrentHashMap

- Thread Safety: `ConcurrentHashMap` is an implementation of the `Map` interface that supports full concurrency of retrievals and high expected concurrency for updates. It is designed to optimize retrieval operations at the expense of a moderate performance hit on updates.
- Null Keys and Value*: Like `HashTable`, `ConcurrentHashMap` does not allow null keys or null values.
- Iteration Order: `ConcurrentHashMap` does not guarantee any specific iteration order of its entries.
- Performance: It uses a segment-based locking mechanism which is more fine-grained than `HashTable`. This allows a higher level of concurrency without blocking the entire map for updates. It performs much better in environments where read operations are much more common than writes.

Use Cases

- HashTable: Best used in legacy applications where thread safety is a concern, but where updates are infrequent or moderate, and high concurrency is not required.
- HashMap: Ideal for non-threaded applications or ones where synchronization is handled externally or not required. It offers the fastest access times of the three.
- ConcurrentHashMap: Suitable for highly concurrent applications, particularly where reads greatly outnumber writes. It is a part of the standard `java.util.concurrent` package, designed to support concurrent Java programming.

### String vs StringBuilder vs StringBuffer
1. String
- Immutability: `String` objects are immutable. Once a `String` object is created, its content cannot be changed. Any method that seems to modify a `String` actually creates a new `String` object with the modified content and returns it. This behavior simplifies coding but can lead to inefficiencies when extensive modifications are required.
- Usage: Due to its immutability, `String` is thread-safe and can be shared between threads without synchronization. This makes it ideal for values that are read frequently but seldom changed, like file names, configuration settings, or natural keys in maps.

2. StringBuilder

- Mutability: Unlike `String`, `StringBuilder` is mutable. It allows in-place modification of its content, which means you can add, remove, or change characters within the same `StringBuilder` object. This leads to better performance when performing frequent modifications because it avoids creating new objects for each modification.
- Thread Safety: `StringBuilder` is not synchronized, which means it is not thread-safe. This design decision enhances performance in single-threaded scenarios.
- Usage: `StringBuilder` is suitable for use in a single-threaded environment where you need to construct or modify strings frequently, such as in loops or when generating dynamic content.

3. StringBuffer

- Mutability: Like `StringBuilder`, `StringBuffer` is also mutable. It allows in-place modifications to the string it represents.
- Thread Safety: `StringBuffer` is synchronized, which makes it thread-safe. All of its public methods are synchronized, which means that only one thread can modify it at a time, preventing concurrent modifications that could lead to data corruption.
- Usage: `StringBuffer` should be used in scenarios where string data is shared across multiple threads, or when thread safety is a concern. However, due to its synchronization overhead, it is slower than `StringBuilder` and is generally only preferred in multi-threaded environments.

### Comparator vs Comparable, when to use which one
Comparable is an interface that should be implemented by a class if it has a natural ordering. The class must define a single method, compareTo(Object o), which compares this object with the specified object for order.
When a class implements Comparable, it modifies the class itself. Thus, every instance of the class has this one comparison method, and it can be used automatically by sorting methods, such as Collections.sort() or Arrays.sort(), without requiring additional parameters.

Comparator is a functional interface that defines an external comparison strategy. It requires implementing a single method, compare(Object o1, Object o2), which compares its two arguments for order.
Use Comparator when you need a specific sort order that is different from the natural ordering of a class, or when you want to sort instances of a class that does not implement

Use Comparable when:
You want to enforce a single natural ordering on the objects of your class.
The comparison logic can be embedded within the class itself.
You control the source code of the class that needs ordering.
Use Comparator when:
You need multiple different ways to sort types, perhaps in different parts of your application.
You need to sort instances of classes that you do not control, and these classes do not implement Comparable.
You want to decouple the sorting logic from the class definition to adhere to the single responsibility principle.
You are dealing with lambda expressions or method references, which can make Comparator implementations concise and flexible.

### Overriding vs overloading
overloading occurs when two or more methods in the same class have the same name but different parameters (different type, number, or both). Overloading is a way of providing greater flexibility in programming by allowing multiple methods to perform similar but slightly different tasks.
Parameter Differences: The overloaded methods must differ in the type and/or number of their parameters.
Return Type: The return type can be the same or different across overloaded methods; it does not participate in distinguishing overloaded methods.
Scope: Occurs within a single class, though it can happen in two classes if inheritance is involved.

overriding happens when a subclass provides a specific implementation for a method that is already provided by one of its parent classes or implemented interfaces. Overriding allows a subclass to offer a specific behavior for a method that is already defined in its superclass.
Same Signature: The method in the subclass that overrides the method from the superclass must have the same name, return type, and parameters.
Access Level: The access level can't be more restrictive than the method in the superclass.
Runtime Polymorphism: Method overriding is a foundation for runtime polymorphism, meaning that the method to be executed is determined at runtime based on the object’s actual class type.

### JRE vs JDK vs JVM
In Java development and execution environment, three key components are involved: the Java Virtual Machine (JVM), the Java Runtime Environment (JRE), and the Java Development Kit (JDK). Each serves a different role in the overall ecosystem of Java programming. Here's an explanation of each component and how they relate to each other:

1. Java Virtual Machine (JVM)
- Definition: The JVM is an abstract computing machine that enables a computer to run a Java program. It is platform-dependent in its implementation but provides a platform-independent execution environment for Java applications.
- Functionality: The JVM performs several tasks, including loading code, verifying code, executing code, and providing runtime environment. It acts as the engine that drives Java applications, executing the bytecode compiled from Java source files.
- Key Role: The primary role of the JVM is to ensure that Java applications can run on any device or operating system without needing to be rewritten or recompiled by developers, thereby upholding Java's write once, run anywhere (WORA) capability.

2. Java Runtime Environment (JRE)
- Definition: The JRE consists of the JVM and the core libraries necessary to run Java applications. It does not include development tools such as compilers or debuggers.
- Components: The JRE includes:
   - The Java Virtual Machine (JVM).
   - Core libraries and other components needed for the JVM to execute Java applications.
- Purpose: The JRE provides a minimal environment to run Java applications on a computer. It is intended for users who just want to run Java programs but do not need to develop them. This makes the JRE sufficient for most end-users of Java applications.

3. Java Development Kit (JDK)
- Definition: The JDK includes the JRE and the tools needed for developing, debugging, and monitoring Java applications.
- Components: The JDK comprises:
   - The Java Runtime Environment (JRE) – all the components needed to run Java applications.
   - Compiler (`javac`) – to convert Java source code into bytecode.
   - JavaDoc – tool to create HTML documentation from Java source code.
   - Debugger – to debug Java applications.
   - Various other development tools.
- Purpose: The JDK is essential for Java developers as it provides all the necessary tools to develop Java applications. It is used to write, compile, and debug Java code before it is run by the JRE.

How They Interact
- JVM is the base, running the programs.
- JRE is the container that provides a runtime environment, including the JVM.
- JDK is the full suite, providing both runtime environment and tools needed for development.

- If you just want to run Java applications, you need the JRE.
- If you want to develop Java applications, you need the JDK, which also includes the JRE to run the applications you develop.
- The JVM is a part of both the JRE and JDK, acting as the engine that executes the bytecode.



### Java 8 basic data types
1. Byte
- Size: 8 bits (1 byte)
- Range: -128 to 127
- Use: Very small integer values, saves space over using `int`.

2. Short
- Size: 16 bits (2 bytes)
- Range: -32,768 to 32,767
- Use: Shorter integers, saving space over `int`.

3. Int
- Size: 32 bits (4 bytes)
- Use: Default data type for integral values unless there is a concern about space.

4. Long
- Size: 64 bits (8 bytes)
- Use: Larger integer values than `int` can handle.

5. Float
- Type: Floating Point
- Size: 32 bits (4 bytes)
- Use: Single precision floating point. Used when a fractional component is required. It saves space over `double`.

6. Double
- Type: Floating Point
- Size: 64 bits (8 bytes)
- Use: Double precision floating point. It is the default data type for decimal values.

7. Char
- Type: Character
- Size: 16 bits (2 bytes)
- Use: To store any character.

8. Boolean
- Type: Boolean
- Size: Not precisely specified, but effectively 1 bit of information (true or false)
- Range: `true` or `false`
- Use: For simple flags that track true/false conditions.

Primitive type, reference type
Primitive types in Java are predefined by the language and named by a reserved keyword. They represent the most basic data types available and hold their values directly in memory.When you declare a primitive type, Java allocates memory for the value directly in the stack, which makes accessing and manipulating these types fast and efficient.

Reference types in Java are any data types that derive from a class rather than being predefined by the language. When you declare a variable of a reference type, the variable holds a reference (or address) to the actual object in memory, not the object itself.
Memory for objects of reference types is allocated on the heap, and the variable stores a reference to this memory location. This allows for more complex interactions than with primitive types.


## Homework 2 Question List (write necessary code to answer the following questions)
### What is final keyword

### Create a Student immutable class, with fields student id, first name, last name, List<Course> courses,  (be careful with Course class)
To create an immutable `Student` class with the specified fields, we need to follow these steps:

1. Make the class `final` to prevent inheritance.
2. Declare all fields as `private` and `final`.
3. Do not provide setter methods for the fields.
4. Initialize all fields through the constructor.
5. Ensure that mutable objects like `List<Course>` are not directly mutable outside the class.

Here's the implementation of the `Student` class:

```java
import java.util.Collections;
import java.util.List;

public final class Student {
    private final int studentId;
    private final String firstName;
    private final String lastName;
    private final List<Course> courses;

    public Student(int studentId, String firstName, String lastName, List<Course> courses) {
        this.studentId = studentId;
        this.firstName = firstName;
        this.lastName = lastName;
        // Create a defensive copy of the courses list to ensure immutability
        this.courses = Collections.unmodifiableList(courses != null ? courses : Collections.emptyList());
    }

    public int getStudentId() {
        return studentId;
    }

    public String getFirstName() {
        return firstName;
    }

    public String getLastName() {
        return lastName;
    }

    public List<Course> getCourses() {
        // Return an unmodifiable view of the courses list to prevent modification
        return courses;
    }
}
```

And here's a simple `Course` class:

```java
public class Course {
    private final String courseName;

    public Course(String courseName) {
        this.courseName = courseName;
    }

    public String getCourseName() {
        return courseName;
    }
}
```

In the `Student` class, the `courses` field is made immutable by creating an unmodifiable view of the provided list using `Collections.unmodifiableList()`. This ensures that the list cannot be modified after the `Student` object is constructed. Additionally, the `getCourses()` method returns an unmodifiable view of the courses list to prevent external modification.

### What is volatile, transient, synchronized
In Java, `volatile`, `transient`, and `synchronized` are keywords used for specific purposes:

1. **volatile**:
    - `volatile` is used to indicate that a variable's value may be modified by multiple threads concurrently.
    - When a variable is declared as `volatile`, it ensures that changes made by one thread to the variable's value are immediately visible to other threads.
    - It prevents the compiler and CPU from reordering instructions, thereby ensuring that the variable's value is always read from and written to the main memory, rather than from CPU caches.
    - `volatile` is typically used for flags or status variables that are accessed by multiple threads without synchronization.

2. **transient**:
    - `transient` is used to indicate that a variable should not be serialized when an object of the class containing the variable is serialized.
    - When an object is serialized, only the non-transient fields are written to the output stream, while transient fields are skipped.
    - This is useful for variables that hold temporary or sensitive data that should not be persisted when the object is serialized and deserialized.
    - For example, `transient` can be used for fields that hold cache data or references to resources that should not be persisted.

3. **synchronized**:
    - `synchronized` is used to create a mutually exclusive block of code, also known as a critical section, that can be accessed by only one thread at a time.
    - When a method or block of code is declared as `synchronized`, it ensures that only one thread can execute it at a time, preventing race conditions and ensuring thread safety.
    - It can be applied to methods, instance-level blocks, or static blocks, and it uses an intrinsic lock (also known as a monitor) to synchronize access to the code block.
    - `synchronized` is commonly used in multi-threaded environments to coordinate access to shared resources or to protect critical sections of code from concurrent execution.

In summary, `volatile` ensures visibility of variable changes across threads, `transient` excludes variables from serialization, and `synchronized` provides thread-safe access to critical sections of code. Each keyword serves a distinct purpose in Java programming, contributing to the overall robustness and correctness of multi-threaded and serialized applications.

### throw vs throws
**throw**:
- `throw` is a keyword in Java used to explicitly throw an exception within a method or block of code.
- It is followed by an instance of an exception class or an object that extends `Throwable`.
- When `throw` is executed, it immediately terminates the current execution path and transfers control to the nearest enclosing `try-catch` block or method that can handle the thrown exception.
- It is typically used to signal that an exceptional condition has occurred within a method and the method cannot handle it itself.

**throws**:
- `throws` is a keyword in Java used in method signatures to declare that a method may throw certain types of exceptions.
- It is followed by a comma-separated list of exception classes that the method may throw.
- When a method is declared with a `throws` clause, it means that the method does not handle the exception itself, but instead propagates it to the caller.
- The caller of the method is responsible for handling the thrown exception using a `try-catch` block or by declaring its own `throws` clause.

**Differences**:
- `throw` is used to manually throw an exception within a method or block of code, while `throws` is used in method signatures to declare that a method may throw certain types of exceptions.
- `throw` is followed by an instance of an exception class or object, while `throws` is followed by a list of exception classes.
- `throw` is used within the method implementation, while `throws` is used in the method declaration.
- `throw` immediately transfers control to a `try-catch` block or method that can handle the exception, while `throws` propagates the exception to the caller of the method.
- 
### final vs finally vs finalize
**final**:
- `final` is a keyword in Java used to denote something as constant or unchangeable. It can be applied to classes, methods, and variables.
- When applied to a class, it means the class cannot be subclassed or extended.
- When applied to a method, it means the method cannot be overridden by subclasses.
- When applied to a variable, it means the variable is a constant and cannot be reassigned after initialization.

**finally**:
- `finally` is a keyword in Java used in conjunction with try-catch blocks to ensure that certain code executes regardless of whether an exception is thrown or not.
- The `finally` block contains code that will be executed whether or not an exception is thrown in the try block.
- It is commonly used for releasing resources, closing connections, or performing cleanup tasks to ensure proper resource management.

**finalize**:
- `finalize` is a method in Java's `Object` class that is called by the garbage collector before an object is reclaimed.
- It is used for performing cleanup actions or releasing resources associated with an object before it is garbage collected.
- The `finalize` method is not guaranteed to be called by the garbage collector and should not be relied upon for critical resource cleanup.

**Differences**:
- `final` is used to denote something as constant or unchangeable, while `finally` is used in exception handling to ensure certain code is executed.
- `final` can be applied to classes, methods, and variables, whereas `finally` is used only in try-catch blocks.
- `finalize` is a method called by the garbage collector for object cleanup, whereas `final` and `finally` are keywords used in different contexts within the Java language.

### this vs super
In Java, `this` and `super` are both keywords used to refer to objects, but they have different meanings and contexts:

1. **this**:
   - `this` is a reference to the current object within an instance method or constructor.
   - It is used to access instance variables and methods of the current object.
   - It can be used to differentiate between instance variables and parameters with the same name within a method or constructor.
   - It can also be used to invoke constructors within other constructors of the same class, using `this()`.

2. **super**:
   - `super` is a reference to the superclass of the current object.
   - It is used to access superclass methods, variables, and constructors from a subclass.
   - It is often used to call superclass constructors explicitly, using `super()` in the subclass constructor.
   - When used in a method, it calls the superclass method with the same signature, even if the subclass has overridden the method.

In summary, `this` refers to the current object, while `super` refers to the superclass of the current object. `this` is used primarily for accessing members of the current object and invoking constructors, while `super` is used for accessing members of the superclass and invoking superclass constructors.

### abstract class vs interface
**Abstract Class**:
1. An abstract class can contain both abstract and non-abstract methods.
2. An abstract class can have constructors, but it cannot be instantiated (i.e., objects cannot be created from it).
3. Subclasses must implement all abstract methods of the abstract class, unless the subclass is also declared abstract.
4. An abstract class can contain member variables, static methods, static members, and constructors.
5. A class can only extend one abstract class.

**Interface**:
1. An interface can only contain abstract methods and constants (static final variables).
2. Methods in an interface are implicitly `public` and `abstract`, and these modifiers can be omitted.
3. Classes implementing an interface must implement all methods defined in the interface.
4. An interface cannot contain member variables, static methods, or constructors.
5. A class can implement multiple interfaces, allowing for multiple inheritance-like behavior.
6. Interfaces can extend other interfaces using the `extends` keyword.

**Similarities**:
1. Both abstract classes and interfaces are abstract and cannot be instantiated; they require subclasses or implementing classes to provide concrete implementations.
2. Both abstract classes and interfaces are used to achieve polymorphism and encapsulation.
3. Both abstract classes and interfaces can define abstract methods, allowing subclasses or implementing classes to provide specific implementations.

**Choosing between them**:
- Use an abstract class when you need to provide some default implementation or shared code.
- Use an interface when you need to define a set of specifications that different classes should implement.
- If a class needs to inherit from another class while also implementing functionality from multiple sources, you can achieve this by extending an abstract class and implementing interfaces.


### Jvm architecture
The Java Virtual Machine (JVM) architecture consists of several components that work together to execute Java programs. Here's an overview of the JVM architecture:

1. **Class Loader Subsystem**:
   - Responsible for loading class files into memory.
   - Consists of three subsystems:
      - **Bootstrap Class Loader**: Loads core Java classes from the bootstrap classpath.
      - **Extension Class Loader**: Loads classes from the extension classpath.
      - **Application Class Loader**: Loads classes from the application classpath.

2. **Runtime Data Area**:
   - Memory area used by the JVM to execute Java programs.
   - Consists of several components:
      - **Method Area**: Stores class metadata, static fields, and constant pool.
      - **Heap**: Memory area used for storing objects and instance variables.
      - **Java Stack**: Stores method frames, including local variables and partial results.
      - **Native Method Stack**: Stores native method invocation and local variables.
      - **Program Counter Register**: Keeps track of the currently executing instruction.
      - **Native Method Interface (JNI)**: Allows Java code to call and be called by native applications written in languages like C and C++.

3. **Execution Engine**:
   - Responsible for executing Java bytecode.
   - Consists of two components:
      - **Interpreter**: Interprets bytecode instructions and executes them one by one.
      - **Just-In-Time (JIT) Compiler**: Compiles frequently executed bytecode into native machine code for improved performance.

4. **Garbage Collector**:
   - Manages memory by reclaiming unused objects and freeing up memory space.
   - Performs automatic memory management to prevent memory leaks and optimize memory usage.
   - Utilizes different garbage collection algorithms like Mark-Sweep, Mark-Compact, and Generational Garbage Collection.

5. **Native Method Interface (JNI)**:
   - Provides a way for Java code to interact with native code written in languages like C and C++.
   - Allows Java applications to call native methods and vice versa.

6. **Execution Monitoring and Profiling**:
   - Provides tools for monitoring and profiling JVM performance.
   - Includes features like Java Monitoring and Management Console (JConsole), Java Flight Recorder (JFR), and Java Mission Control (JMC) for performance analysis and troubleshooting.

Overall, the JVM architecture provides a platform-independent execution environment for Java programs, allowing them to run on any device or operating system that supports the JVM. It abstracts away hardware-specific details and provides features like memory management, security, and portability.

### Java modifier scope: public, private, protected, default scope
The Java modifiers `public`, `private`, `protected`, and default (no modifier) are used to control the visibility and accessibility of classes, methods, and variables within a Java program. Here's a summary of their scopes:

1. **public**:
   - Classes, methods, and variables with the `public` modifier are accessible from any other class.
   - They can be accessed from any other package.
   - For example:
     ```java
     public class MyClass {
         public void myMethod() {
             // Code here
         }
     }
     ```

2. **private**:
   - Classes, methods, and variables with the `private` modifier are accessible only within the same class.
   - They cannot be accessed from outside the class, not even from subclasses.
   - For example:
     ```java
     public class MyClass {
         private int myVar;
         
         private void myMethod() {
             // Code here
         }
     }
     ```

3. **protected**:
   - Classes, methods, and variables with the `protected` modifier are accessible within the same package and by subclasses (even if the subclass is in a different package).
   - They cannot be accessed from outside the package by non-subclasses.
   - For example:
     ```java
     package mypackage;
     
     public class MyClass {
         protected int myVar;
         
         protected void myMethod() {
             // Code here
         }
     }
     ```

4. **default (no modifier)**:
   - Classes, methods, and variables with no modifier (default access) are accessible only within the same package.
   - They cannot be accessed from outside the package.
   - For example:
     ```java
     package mypackage;
     
     class MyClass {
         int myVar;
         
         void myMethod() {
             // Code here
         }
     }
     ```

These modifiers allow you to control the visibility and accessibility of your classes, methods, and variables, providing encapsulation and ensuring proper data hiding and abstraction in your Java programs.

### What is static scope
The term "static scope" typically refers to the scope or visibility of static members within a Java class. In Java, the `static` keyword is used to declare members (variables and methods) that belong to the class itself, rather than to instances of the class. Here's an explanation of static scope:

1. **Static Variables**:
   - Static variables, also known as class variables, are shared among all instances of the class.
   - They are declared using the `static` keyword and are initialized only once, when the class is loaded into memory.
   - Static variables have class-level scope, meaning they can be accessed directly using the class name, without needing to create an instance of the class.
   - They are accessible from any method, constructor, or block within the class or any other class in the same package.

2. **Static Methods**:
   - Static methods are associated with the class itself, rather than with instances of the class.
   - They are declared using the `static` keyword and can be invoked using the class name, without needing to create an instance of the class.
   - Static methods have class-level scope and can access static variables directly.
   - They cannot access instance variables or call non-static methods directly, unless they are within the same class.

3. **Static Initialization Blocks**:
   - Static initialization blocks are used to initialize static variables or perform other static initialization tasks.
   - They are declared using the `static` keyword and are executed only once, when the class is loaded into memory.
   - Static initialization blocks have class-level scope and can access static variables directly.

In summary, static scope in Java refers to the visibility and accessibility of static members (variables, methods, and initialization blocks) within a class. Static members are associated with the class itself and can be accessed using the class name, without requiring an instance of the class. They have class-level scope and are shared among all instances of the class.


### how does classloader work
The Java ClassLoader is a crucial component of the Java Runtime Environment (JRE) responsible for loading Java classes into memory during runtime. It follows a hierarchical structure and is responsible for locating and loading class files from various sources, such as the file system, network, or other custom sources. Here's how the ClassLoader works:

1. **Loading**:
   - When a Java program is executed, the JVM is responsible for loading classes into memory as they are referenced by the program.
   - The ClassLoader is invoked whenever a class is first referenced in the program, either explicitly (e.g., through the `new` keyword or method invocation) or implicitly (e.g., when a class is referenced as a superclass or interface).
   - The ClassLoader searches for the class file in the classpath, which includes directories, JAR files, and other locations specified by the runtime environment.

2. **Delegation Model**:
   - The ClassLoader follows a delegation model, where each ClassLoader delegates the class-loading request to its parent ClassLoader before attempting to load the class itself.
   - This parent delegation continues recursively until the Bootstrap ClassLoader, which is responsible for loading core Java classes from the bootstrap classpath, is reached.
   - If the parent ClassLoader cannot find the requested class, the child ClassLoader attempts to load the class itself.

3. **Class Resolution**:
   - Once a class is located, the ClassLoader reads the bytecode from the class file and defines the class structure in memory.
   - It performs bytecode verification to ensure the class is well-formed and does not violate security constraints.
   - If the class has not been loaded before, the ClassLoader also initializes static fields and performs static initialization blocks.

4. **Class Loading Mechanisms**:
   - Java supports multiple ClassLoader implementations, each with its own loading mechanisms.
   - The most common ClassLoader implementations include the Bootstrap ClassLoader, Extension ClassLoader, System ClassLoader, and custom ClassLoaders.
   - Custom ClassLoaders can be used to load classes from non-standard locations, such as databases or remote servers.

5. **Class Unloading**:
   - While classes are loaded into memory dynamically, they are not unloaded automatically when they are no longer needed.
   - Instead, classes are subject to garbage collection like other objects in the JVM.
   - However, custom ClassLoader implementations may allow for class unloading in specific scenarios, such as when a custom ClassLoader is discarded.

Overall, the ClassLoader plays a crucial role in the dynamic loading and resolution of Java classes during runtime, enabling Java programs to adapt to changing runtime environments and load classes from various sources.

### Homework 3 Question List (write necessary code to answer the following questions)

### Describe the difference between unchecked and checked exceptions in Java.
In Java, exceptions are categorized into two main types: checked exceptions and unchecked exceptions. Here's the difference between them:

1. **Checked Exceptions**:
   - Checked exceptions are subclasses of `Exception` (excluding subclasses of `RuntimeException` and `Error`).
   - These exceptions must be either caught (handled) or declared in the method signature using the `throws` keyword.
   - The compiler enforces handling of checked exceptions at compile-time, ensuring that developers explicitly handle potential exceptions that may occur during program execution.
   - Examples of checked exceptions include `IOException`, `SQLException`, and `ClassNotFoundException`.
   - Checked exceptions are typically used to represent exceptional conditions that the program can reasonably be expected to recover from, such as file not found or database connection failure.

2. **Unchecked Exceptions**:
   - Unchecked exceptions are subclasses of `RuntimeException` and `Error`, including their subclasses.
   - Unlike checked exceptions, unchecked exceptions are not required to be caught or declared in the method signature.
   - Unchecked exceptions are typically programming errors or unexpected conditions that may occur during runtime and are beyond the control of the program.
   - Examples of unchecked exceptions include `NullPointerException`, `ArrayIndexOutOfBoundsException`, `IllegalArgumentException`, and `ArithmeticException`.
   - Unchecked exceptions are not enforced by the compiler at compile-time, allowing developers to choose whether or not to handle them explicitly.
   - Unchecked exceptions are often used to represent critical errors or situations where it's not feasible to recover programmatically, such as divide by zero or attempting to access a null reference.

In summary, the key difference between checked and unchecked exceptions lies in how they are enforced and handled by the compiler and runtime environment. Checked exceptions must be explicitly handled or declared, while unchecked exceptions are optional and can be left unhandled if desired. Checked exceptions are typically used for recoverable errors, while unchecked exceptions represent unexpected conditions or programming errors.

### What is the difference between finally, final, and finalize in Java?
Here's the difference between `finally`, `final`, and `finalize` in Java:

1. **finally**:
   - `finally` is a block of code that is used in exception handling to ensure that certain code is always executed, regardless of whether an exception is thrown or not.
   - It follows the `try` or `try-catch` block and precedes any `catch` or `catch-finally` blocks.
   - Code within the `finally` block will execute even if an exception occurs in the `try` block and is caught by a `catch` block, or if no exception occurs at all.
   - `finally` is often used to release resources, such as closing file handles or database connections, that were opened in the `try` block.
   - Example:
     ```java
     try {
         // Code that may throw an exception
     } catch (Exception e) {
         // Exception handling
     } finally {
         // Code that always executes, regardless of whether an exception occurred
         // This block is commonly used for resource cleanup
     }
     ```

2. **final**:
   - `final` is a keyword used to declare constants, variables, methods, and classes in Java.
   - When applied to a variable, it indicates that the variable's value cannot be changed once initialized (i.e., it becomes a constant).
   - When applied to a method, it indicates that the method cannot be overridden by subclasses.
   - When applied to a class, it indicates that the class cannot be subclassed (i.e., it becomes a final class).
   - Example:
     ```java
     final int x = 10; // Constant variable
     final class MyClass { } // Final class
     ```

3. **finalize**:
   - `finalize` is a method defined in the `Object` class and is called by the garbage collector before reclaiming an object's memory.
   - It is used for performing cleanup or resource releasing tasks before an object is destroyed.
   - However, it is not recommended to rely on `finalize` for resource cleanup, as its execution timing and reliability are not guaranteed.
   - It's typically better to use `finally` blocks or try-with-resources statements for resource cleanup.
   - Example:
     ```java
     class MyClass {
         protected void finalize() {
             // Cleanup code before object destruction
         }
     }
     ```

In summary, `finally` is used in exception handling to ensure code execution, `final` is used to declare constants, variables, methods, or classes, and `finalize` is a method used for object cleanup before garbage collection.

### Define try-with resource. How can you say that it differs from an ordinary try?
The try-with-resources statement is a feature introduced in Java 7 that simplifies resource management by automatically closing resources after they are no longer needed. Here's how it works and how it differs from an ordinary try statement:

1. **Syntax**:
   - The try-with-resources statement has the following syntax:
     ```java
     try (resource initialization) {
         // Code that uses the resource
     } catch (Exception e) {
         // Exception handling
     }
     ```
   - The `resource initialization` part declares one or more resources to be managed by the try-with-resources statement. These resources must implement the `AutoCloseable` interface or its subinterface, `Closeable`.
   - The resources are declared within the parentheses after the `try` keyword, separated by semicolons.

2. **Automatic Resource Management**:
   - With try-with-resources, the declared resources are automatically closed when the try block exits, either normally or due to an exception.
   - The `close()` method of each resource is called in the reverse order of their declaration.
   - This ensures that resources are properly released, even if an exception occurs during execution of the try block.

3. **Cleaner Syntax**:
   - The try-with-resources statement provides a cleaner and more concise syntax for managing resources compared to traditional try-catch-finally blocks.
   - It eliminates the need for explicit finally blocks to release resources, reducing boilerplate code and improving readability.

4. **Automatic Exception Handling**:
   - In try-with-resources, if an exception occurs during resource initialization or while executing the try block, the exception is propagated to the catch block after all resources are closed.
   - If multiple exceptions occur (e.g., both in the try block and during resource closing), any exceptions thrown during resource closing are suppressed and can be accessed using the `getSuppressed()` method of the caught exception.

In summary, try-with-resources provides a cleaner and more efficient way to manage resources in Java compared to traditional try-catch-finally blocks. It automatically closes resources after they are no longer needed and simplifies exception handling, making code more concise and readable.

### Define Runtime Exception. Describe it with the help of an example.
A Runtime Exception in Java is a type of unchecked exception that occurs during the execution of a Java program. Unlike checked exceptions, which must be either caught or declared in the method signature, runtime exceptions do not need to be explicitly handled by the programmer. Runtime exceptions typically arise due to programming errors, such as logical mistakes or invalid operations, and they can occur at any point during program execution.

Here's a definition and an example of a runtime exception:

1. **Definition**:
   - A Runtime Exception in Java is a subclass of `RuntimeException` or its subclasses (including built-in exceptions like `NullPointerException`, `ArrayIndexOutOfBoundsException`, `ArithmeticException`, etc.).
   - These exceptions occur during the execution of a program and are typically caused by logical errors, invalid operations, or other runtime conditions that cannot be detected by the compiler.

2. **Example**:
   ```java
   public class DivideByZeroExample {
       public static void main(String[] args) {
           int numerator = 10;
           int denominator = 0;
           
           // Attempting to divide by zero will result in ArithmeticException
           int result = numerator / denominator; // This line throws ArithmeticException
           
           System.out.println("Result: " + result); // This line will not be executed
       }
   }
   ```
   In this example, we attempt to divide an integer by zero, which is an invalid arithmetic operation. This results in an `ArithmeticException` being thrown at runtime, specifically a "divide by zero" exception. Since this exception is not caught or handled within the program, it propagates up the call stack and terminates the program with an error message. This demonstrates how a runtime exception can occur during the execution of a Java program due to a logical error or invalid operation.

### What is the difference between NoClassDefFoundError and ClassNotFoundException in Java
The `NoClassDefFoundError` and `ClassNotFoundException` are both exceptions related to class loading in Java, but they occur in different situations and have distinct causes. Here's how they differ:

1. **NoClassDefFoundError**:
   - `NoClassDefFoundError` occurs when the Java Virtual Machine (JVM) or a ClassLoader is unable to find the definition of a class at runtime, even though the class was available during compilation.
   - This error typically indicates that the class was present during compilation but is missing at runtime.
   - `NoClassDefFoundError` is usually caused by a missing class file or a class file that is not in the expected location.
   - It can also occur if a class that the application depends on is present in the classpath during compilation but not during execution, due to issues such as incorrect classpath configuration or missing dependencies.
   - Example:
     ```java
     public class NoClassDefFoundErrorExample {
         public static void main(String[] args) {
             // Attempting to instantiate a class that is not available at runtime
             MyClass obj = new MyClass(); // This line throws NoClassDefFoundError
         }
     }
     ```

2. **ClassNotFoundException**:
   - `ClassNotFoundException` occurs when the `Class.forName()` method or the `ClassLoader.loadClass()` method is unable to find the class definition at runtime.
   - This exception is typically thrown when the specified class cannot be found in the classpath or is not accessible by the ClassLoader.
   - Unlike `NoClassDefFoundError`, `ClassNotFoundException` is usually caused by a class that is missing or unavailable at compile-time or runtime.
   - It commonly occurs when attempting to dynamically load a class using reflection or when working with external libraries or modules.
   - Example:
     ```java
     public class ClassNotFoundExceptionExample {
         public static void main(String[] args) {
             try {
                 // Attempting to load a class dynamically
                 Class<?> clazz = Class.forName("com.example.MyClass"); // This line throws ClassNotFoundException
             } catch (ClassNotFoundException e) {
                 e.printStackTrace();
             }
         }
     }
     ```

In summary, `NoClassDefFoundError` occurs when a class that was available during compilation is missing at runtime, while `ClassNotFoundException` occurs when the JVM or ClassLoader cannot find the specified class definition at runtime, regardless of its availability during compilation.


### Why should we clean up activities such as I/O resources in the finally block?
Cleaning up activities such as I/O resources in the `finally` block is important for several reasons:

1. **Resource Release**:
   - I/O resources such as file handles, network connections, or database connections consume system resources.
   - Failure to release these resources properly can lead to resource leaks, where resources are not released back to the system after they are no longer needed.
   - The `finally` block ensures that resources are released regardless of whether an exception occurs during the execution of the `try` block.

2. **Exception Handling**:
   - The `finally` block is executed after the `try` block completes, whether an exception occurs or not.
   - This makes it a suitable place to include resource cleanup code, as it ensures that resources are released even if an exception is thrown and caught within the `try` block.
   - Without proper cleanup in the `finally` block, resources may remain open or locked, leading to resource contention or corruption.

3. **Robustness and Reliability**:
   - Proper resource cleanup in the `finally` block contributes to the robustness and reliability of the program.
   - It helps prevent resource exhaustion and ensures that subsequent operations can proceed without interference from lingering resources.

4. **Avoiding Memory Leaks**:
   - In the case of objects that allocate native resources, such as file handles or database connections, failure to release these resources can lead to memory leaks.
   - The `finally` block ensures that these resources are properly released, preventing memory leaks and improving the overall memory management of the application.

5. **Best Practice**:
   - Cleaning up resources in the `finally` block is considered a best practice in Java programming.
   - It follows the principle of "resource acquisition is initialization" (RAII), which promotes the automatic cleanup of resources when they are no longer needed.
   - By adhering to this practice, developers can write more reliable and maintainable code.

In summary, cleaning up activities such as I/O resources in the `finally` block ensures proper resource release, improves exception handling, enhances program robustness, and follows best practices for resource management in Java.

### Describe OutofMemoryError in exception handling.
`OutOfMemoryError` is an error in Java that occurs when the Java Virtual Machine (JVM) runs out of memory to allocate new objects. It is a subclass of `Error`, which indicates serious problems that are not typically recoverable by the application. Here's a description of `OutOfMemoryError` in exception handling:

1. **Cause**:
   - `OutOfMemoryError` occurs when the JVM attempts to allocate memory for a new object, but there is not enough memory available in the heap to fulfill the request.
   - This can happen due to various reasons, such as:
      - The application is allocating too many objects, exceeding the available heap space.
      - The application has a memory leak, where objects are being held in memory unnecessarily and not released for garbage collection.
      - The JVM is configured with insufficient heap size, leading to exhaustion of available memory.
      - The application is attempting to load large datasets or process large files that exceed the available memory.

2. **Types**:
   - There are different types of `OutOfMemoryError` depending on which area of memory is exhausted:
      - `java.lang.OutOfMemoryError: Java heap space`: This occurs when the JVM's heap memory is exhausted.
      - `java.lang.OutOfMemoryError: PermGen space` (or `Metaspace` in newer JVMs): This occurs when the JVM's permanent generation (or Metaspace) is exhausted, typically caused by loading too many classes or excessive use of metadata.
      - `java.lang.OutOfMemoryError: Unable to create new native thread`: This occurs when the JVM cannot create new native threads due to operating system limits on thread creation.

3. **Handling**:
   - `OutOfMemoryError` is considered a fatal error, and it usually indicates a serious problem with the application or the environment.
   - In most cases, `OutOfMemoryError` cannot be handled programmatically, as it indicates that the JVM is unable to continue execution due to insufficient resources.
   - However, in certain scenarios, developers may take preventive measures to avoid `OutOfMemoryError`, such as optimizing memory usage, analyzing memory consumption using profilers, increasing heap size, or redesigning the application architecture to manage memory more efficiently.

4. **Prevention**:
   - To prevent `OutOfMemoryError`, it's essential to design applications with memory efficiency in mind.
   - This includes:
      - Properly managing object creation and destruction to avoid memory leaks.
      - Using data structures and algorithms that minimize memory usage.
      - Monitoring and tuning JVM parameters such as heap size and garbage collection settings.
      - Employing tools like profilers and heap analyzers to identify memory bottlenecks and optimize memory usage.

In summary, `OutOfMemoryError` is a critical error that occurs when the JVM runs out of memory to allocate new objects. It typically indicates serious issues with memory management in the application and requires preventive measures to avoid or mitigate its occurrence.

### What is Generics in Java? What are the advantages of using Generics?
Generics in Java provide a way to create classes, interfaces, and methods that operate on objects of specified types while providing compile-time type safety. Generics allow developers to write code that is more flexible, reusable, and type-safe. Here's a detailed explanation of what generics are and their advantages:

1. **Generics in Java**:
   - Generics were introduced in Java 5 (JDK 1.5) as a means to add compile-time type safety to collections and other classes.
   - Generics allow classes, interfaces, and methods to be parameterized with types, enabling the creation of reusable components that can work with different data types.
   - Generics use parameterized types, which are classes or interfaces that take type parameters enclosed in angle brackets (`<>`).

2. **Advantages of Using Generics**:
   - **Type Safety**: Generics provide compile-time type safety by allowing the compiler to perform type checking at compile time. This helps detect and prevent type errors before they occur at runtime, reducing the risk of ClassCastException and other type-related errors.
   - **Code Reusability**: Generics enable the creation of reusable components that can work with different data types. This promotes code reusability and reduces code duplication by allowing developers to write generic algorithms and data structures that can be used with multiple types.
   - **Abstraction**: Generics allow developers to write code in a more abstract and generic way, focusing on the behavior of components rather than specific data types. This promotes cleaner and more modular code design, making it easier to understand and maintain.
   - **Performance**: Generics have minimal runtime overhead because generic type information is erased (removed) during compilation (type erasure). This means that generic code has similar performance characteristics to non-generic code.
   - **Compile-Time Checking**: Generics enable the compiler to perform compile-time type checking, ensuring that operations on objects are type-safe and preventing type-related errors at runtime. This helps catch errors early in the development process, reducing the likelihood of bugs and improving code quality.
   - **Interoperability**: Generics support interoperability with legacy code and libraries that do not use generics. This allows developers to use generics alongside existing non-generic code and libraries, making it easier to migrate to a more type-safe and modern codebase.

Overall, the advantages of using generics in Java include improved type safety, code reusability, abstraction, performance, compile-time checking, and interoperability. Generics help developers write cleaner, more modular, and less error-prone code by providing compile-time type safety and promoting code reuse and abstraction.

### How Generics works in Java ? What is type erasure ?
Generics in Java provide a way to create classes, interfaces, and methods that operate on objects of specified types while providing compile-time type safety. Generics allow developers to write code that is more flexible, reusable, and type-safe.

Here's how generics work in Java and an explanation of type erasure:

1. **Generics in Java**:
   - Generics were introduced in Java 5 (JDK 1.5) as a means to add compile-time type safety to collections and other classes.
   - Generics allow classes and methods to be parameterized with types, enabling the creation of reusable components that can work with different data types.
   - The main benefit of generics is type safety, as it enables the compiler to detect and report type errors at compile time rather than at runtime.

2. **Parameterized Types**:
   - Generics use parameterized types, which are classes or interfaces that take type parameters.
   - Type parameters are enclosed in angle brackets (`<>`) and are typically represented by single uppercase letters, such as `T`, `E`, or `K`.
   - Example of a parameterized class:
     ```java
     public class Box<T> {
         private T value;
         
         public void setValue(T value) {
             this.value = value;
         }
         
         public T getValue() {
             return value;
         }
     }
     ```

3. **Type Safety**:
   - Generics provide type safety by allowing the compiler to perform type checking at compile time.
   - This ensures that operations on objects are type-safe and prevents runtime errors such as ClassCastException.
   - Example:
     ```java
     Box<Integer> integerBox = new Box<>();
     integerBox.setValue(10); // Valid operation
     // integerBox.setValue("Hello"); // Compilation error: incompatible types
     ```

4. **Type Erasure**:
   - Java generics are implemented using type erasure, which means that generic type information is erased (removed) during compilation.
   - At runtime, generic types are replaced with their raw types or with the upper bound (e.g., Object) if no bound is specified.
   - Type erasure is necessary for backward compatibility with pre-existing code and to support Java's platform independence.
   - Example:
     ```java
     // Before compilation (source code)
     List<Integer> list = new ArrayList<>();
     list.add(10); // Equivalent to: list.add(Integer.valueOf(10));
     
     // After compilation (bytecode)
     List list = new ArrayList();
     list.add(Integer.valueOf(10));
     ```

5. **Limitations of Type Erasure**:
   - Type erasure has some limitations, such as the inability to determine generic type information at runtime (e.g., with reflection) and the loss of type safety when working with raw types.
   - Despite these limitations, type erasure enables backward compatibility and allows generics to work seamlessly with existing Java code.

In summary, generics in Java provide compile-time type safety by using parameterized types. Type erasure is the process by which generic type information is removed during compilation, replacing it with raw types or upper bounds. While type erasure has limitations, it enables backward compatibility and supports Java's platform independence.

### What is the difference between List<? extends T>  and  List <? super T>?
The difference between `List<? extends T>` and `List<? super T>` lies in their usage and the types of elements they can accept. Let's break down each one:

1. **List<? extends T>**:
   - This is a bounded wildcard parameterized type, denoted by `<? extends T>`.
   - It represents a list that can hold elements of any subtype of the type `T`, including `T` itself.
   - With `List<? extends T>`, you can only read elements from the list, but you cannot add elements to it. This is because the compiler cannot guarantee the type safety of adding elements to a collection of unknown subtypes.
   - Example:
     ```java
     List<? extends Number> numbers = new ArrayList<>();
     Number n = numbers.get(0); // OK: Reading is allowed
     // numbers.add(10); // Compilation error: Adding is not allowed
     ```

2. **List<? super T>**:
   - This is also a bounded wildcard parameterized type, denoted by `<? super T>`.
   - It represents a list that can hold elements of any supertype of the type `T`, including `T` itself.
   - With `List<? super T>`, you can add elements of type `T` or any subtype of `T` to the list, but you cannot reliably read elements from it. This is because the compiler cannot guarantee the type safety of reading elements from a collection of unknown supertypes.
   - Example:
     ```java
     List<? super Integer> integers = new ArrayList<>();
     integers.add(10); // OK: Adding is allowed
     // Integer i = integers.get(0); // Compilation error: Reading is not allowed
     ```

In summary:
- `List<? extends T>` is suitable when you only need to read elements from the list and don't need to add elements to it. It represents a collection of elements of an unknown subtype of `T`.
- `List<? super T>` is suitable when you need to add elements to the list and don't need to read elements from it reliably. It represents a collection of elements of an unknown supertype of `T`.

Understanding the difference between `extends` and `super` in wildcards is crucial for writing generic code that is flexible and type-safe.


### What is Optional class (write a demo code to use ofNullable, orElse, orElseThrow method)
The `Optional` class in Java is a container object that may or may not contain a non-null value. It is primarily used to represent an optional value that may be absent. Here's a demo code to demonstrate the usage of `Optional` class methods such as `ofNullable`, `orElse`, and `orElseThrow`:

```java
import java.util.Optional;

public class OptionalDemo {
    public static void main(String[] args) {
        // Creating an Optional object with a non-null value
        Optional<String> optionalWithValue = Optional.of("Hello, world!");

        // Creating an Optional object with a null value
        Optional<String> optionalWithNull = Optional.ofNullable(null);

        // Using ofNullable to create an Optional object with a potentially null value
        Optional<String> optionalNullable = Optional.ofNullable("This is an optional value");

        // Using orElse method to provide a default value if the optional is empty
        String valueOrDefault = optionalWithNull.orElse("Default Value");
        System.out.println("Value or Default: " + valueOrDefault);

        // Using orElseThrow method to throw an exception if the optional is empty
        String valueOrThrow = optionalWithNull.orElseThrow(() -> new IllegalStateException("Value is empty"));
        System.out.println("Value or Throw: " + valueOrThrow);

        // Printing the values of Optional objects
        System.out.println("Optional with value: " + optionalWithValue.get());
        System.out.println("Optional with null: " + optionalWithNull);
        System.out.println("Optional with nullable value: " + optionalNullable.orElse("Value is null"));
    }
}
```

In this demo code:
- We create `Optional` objects using the `ofNullable` method, which allows us to handle both non-null and potentially null values.
- We use the `orElse` method to provide a default value if the optional is empty.
- We use the `orElseThrow` method to throw an exception if the optional is empty.
- We retrieve the value from the `Optional` object using the `get` method (Note: It's generally safer to use `orElse` or `orElseThrow` to avoid `NoSuchElementException`).
- We print the values of `Optional` objects to demonstrate their behavior.

### what is functional interface
A functional interface in Java is an interface that contains exactly one abstract method. Functional interfaces are also known as SAM (Single Abstract Method) interfaces. They serve as the foundation for lambda expressions and method references in Java, enabling functional programming constructs.

Here are some key points about functional interfaces:

1. **Single Abstract Method (SAM)**: A functional interface must declare exactly one abstract method. It can have multiple default or static methods, but only one abstract method.

2. **Lambda Expressions**: Functional interfaces can be implemented using lambda expressions, which provide a concise way to create instances of functional interfaces.

3. **Method References**: Functional interfaces can also be implemented using method references, which provide a way to refer to methods without invoking them.

4. **Annotation**: Starting from Java 8, the `@FunctionalInterface` annotation can be used to explicitly declare an interface as a functional interface. This annotation ensures that the interface has only one abstract method, though it's not mandatory to use it.

5. **Functional Programming**: Functional interfaces facilitate functional programming paradigms in Java, allowing developers to write more concise, readable, and expressive code by treating functions as first-class citizens.

Example of a functional interface:

```java
@FunctionalInterface
interface MyFunction {
    int apply(int x, int y); // Abstract method
}
```

Usage of the functional interface with lambda expression:

```java
MyFunction add = (x, y) -> x + y;
System.out.println(add.apply(3, 5)); // Output: 8
```

In this example, `MyFunction` is a functional interface with a single abstract method `apply`. We create an instance of `MyFunction` using a lambda expression to define the implementation of the `apply` method, which adds two integers. This demonstrates how functional interfaces enable the use of lambda expressions for functional programming in Java.

### What is default method
A default method in Java is a method defined within an interface with a default implementation. It was introduced in Java 8 to enable the addition of new methods to existing interfaces without breaking backward compatibility.

Here are some key points about default methods:

1. **Introduction in Java 8**: Default methods were introduced in Java 8 as a feature to enhance the functionality of interfaces without breaking existing implementations.

2. **Default Implementation**: Unlike abstract methods in interfaces, default methods have a default implementation provided within the interface itself. This implementation is used if a class implementing the interface does not provide its own implementation for the default method.

3. **Syntax**: The syntax for defining a default method in an interface is similar to that of regular interface methods, except that it includes the `default` keyword followed by the method body.

4. **Usage**: Default methods are primarily used to add new methods to existing interfaces in order to provide additional functionality without requiring all implementing classes to provide their own implementations.

5. **Example**:

```java
public interface MyInterface {
    // Abstract method (implicitly public and abstract)
    void abstractMethod();
    
    // Default method with a default implementation
    default void defaultMethod() {
        System.out.println("Default implementation of defaultMethod");
    }
}
```

In this example, `defaultMethod` is a default method defined within the `MyInterface` interface. It provides a default implementation that prints a message. Classes implementing `MyInterface` can choose to override the `defaultMethod` if they want to provide a custom implementation, but they are not required to do so.

### what is the difference between Predicate, Supplier, Consumer, Function?
The differences between Predicate, Supplier, Consumer, and Function interfaces in Java primarily lie in their purpose and the type of operation they perform. Let's break down each one:

1. **Predicate**:
   - Purpose: Used for evaluating a condition or making a decision based on input.
   - Functional Method: `test(T t)` - Evaluates the given argument and returns a boolean result.
   - Example: Checking if a string is empty, testing if a number is even, etc.
   - Example Code:
     ```java
     Predicate<String> isEmpty = s -> s.isEmpty();
     boolean result = isEmpty.test("Hello"); // Returns false
     ```

2. **Supplier**:
   - Purpose: Represents a supplier of results, possibly empty.
   - Functional Method: `get()` - Returns a result.
   - Example: Providing a default value, generating random numbers, etc.
   - Example Code:
     ```java
     Supplier<Double> randomDouble = () -> Math.random();
     double value = randomDouble.get(); // Returns a random double value
     ```

3. **Consumer**:
   - Purpose: Represents an operation that accepts a single input and returns no result.
   - Functional Method: `accept(T t)` - Performs the operation on the given argument.
   - Example: Printing elements of a list, modifying objects, etc.
   - Example Code:
     ```java
     Consumer<Integer> printNumber = n -> System.out.println(n);
     printNumber.accept(10); // Prints 10
     ```

4. **Function**:
   - Purpose: Represents a function that accepts one argument and produces a result.
   - Functional Method: `apply(T t)` - Applies the function to the given argument.
   - Example: Converting between different types, performing calculations, etc.
   - Example Code:
     ```java
     Function<Integer, String> intToString = n -> String.valueOf(n);
     String result = intToString.apply(123); // Returns "123"
     ```

In summary:
- **Predicate**: Evaluates a condition and returns a boolean result.
- **Supplier**: Supplies a result, possibly empty.
- **Consumer**: Accepts a single input and performs an operation with no result.
- **Function**: Accepts one argument and produces a result.

These interfaces are fundamental building blocks in functional programming paradigms in Java and are widely used in various contexts to represent different types of operations and transformations.

### write a piece of code to use the  Predicate, Supplier, Consumer, Function interface

```
import java.util.ArrayList;
import java.util.List;
import java.util.function.Consumer;
import java.util.function.Function;
import java.util.function.Predicate;
import java.util.function.Supplier;

public class Main {
public static void main(String[] args) {
// Predicate example
Predicate<String> startsWithA = s -> s.startsWith("A");
System.out.println(startsWithA.test("Apple"));  // Output: true
System.out.println(startsWithA.test("Banana")); // Output: false

        // Supplier example
        Supplier<Double> randomDouble = Math::random;
        System.out.println(randomDouble.get()); // Output: a random double value

        // Consumer example
        Consumer<String> printUpperCase = s -> System.out.println(s.toUpperCase());
        printUpperCase.accept("hello"); // Output: HELLO

        // Function example
        Function<Integer, String> intToString = i -> "The integer is: " + i;
        System.out.println(intToString.apply(42)); // Output: The integer is: 42

        // Using Predicate, Supplier, Consumer, and Function together
        List<Integer> numbers = new ArrayList<>();
        for (int i = 1; i <= 10; i++) {
            numbers.add(i);
        }

        Predicate<Integer> isEven = n -> n % 2 == 0;
        Supplier<String> messageSupplier = () -> "Number is even: ";
        Consumer<String> printMessage = s -> System.out.println(s);
        Function<Integer, String> evenNumberToString = n -> "Even number: " + n;

        for (Integer number : numbers) {
            if (isEven.test(number)) {
                printMessage.accept(messageSupplier.get() + evenNumberToString.apply(number));
            }
        }
    }
}

```
### what is method reference
Method reference in Java is a shorthand syntax for lambda expressions to invoke a method. It provides a way to refer to a method without executing it. Method reference allows you to reuse existing methods and treat them as lambda expressions, making the code more concise and readable.

There are several types of method references:

1. **Reference to a static method**: `ClassName::staticMethodName`
   Example:
   ```java
   Function<String, Integer> parseIntFunction = Integer::parseInt;
   ```

2. **Reference to an instance method of a particular object**: `objectName::instanceMethodName`
   Example:
   ```java
   String str = "Hello";
   Consumer<Integer> lengthPrinter = str::length;
   ```

3. **Reference to an instance method of an arbitrary object of a particular type**: `ClassName::instanceMethodName`
   Example:
   ```java
   List<String> list = Arrays.asList("Apple", "Banana", "Orange");
   list.forEach(System.out::println);
   ```

4. **Reference to a constructor**: `ClassName::new`
   Example:
   ```java
   Supplier<StringBuilder> stringBuilderSupplier = StringBuilder::new;
   ```

Method references are particularly useful when the lambda expression directly calls a method without any additional logic. They provide a more compact and readable way to express the same functionality. Additionally, they improve code reusability by allowing you to leverage existing methods.



