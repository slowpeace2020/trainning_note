## Homework  1 List (write necessary code to answer the following questions)
### List vs Set

### LinkedList vs ArrayList

### What is Map Interface

### How does HashMap work

### What is hash collision

### What is Collections used for

### What is immutable class

### HashTable vs HashMap vs ConcurrentHashmap

### String vs StringBuilder vs StringBuffer

### Comparator vs Comparable, when to use which one

### Overriding vs overloading

### JRE vs JDK vs JVM

### Java 8 basic data types

### Primitive type, reference type

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
this：
The this keyword is used to refer to the current object, usually used in the following situations:
Reference the member variables or methods of the current object in an instance method.
Call other constructors within the constructor.
Pass the current object as parameter in the method.

super:
The super keyword is used to refer to parent class objects, usually used in the following situations:
Access member variables or methods of the parent class in the subclass.
Call the parent class's constructor in the subclass constructor.
Call the overridden method of the parent class in the subclass.

the difference:

this refers to the current object and is used in instance methods of the current class.
super refers to the parent class object and is used in the subclass to access the members of the parent class or call the constructor of the parent class.

this is mainly used to refer to members or methods of the current object, or to call other constructors in the constructor.
super is mainly used in subclasses to access members or methods of the parent class, or to call the constructor of the parent class in the subclass constructor.

Use this() to call other constructors of the current class.
Use super() to call the constructor of the parent class.
In general, this and super are keywords used to refer to the current object and parent class objects in class methods. Their main difference lies in the objects and usage scenarios. this is mainly used to refer to members or methods of the current object, and super is mainly used in subclasses to access members or methods of the parent class.

### abstract class vs interface
Similarities:
Abstract classes and interfaces are templates used to define the behavior of a class and can be inherited or implemented by subclasses or implementation classes.
Both abstract classes and interfaces support polymorphism, and objects of subclasses or implementation classes can be referenced through parent class or interface types.
the difference:
Method implementation: Abstract classes can contain method implementations, while interfaces can only contain method declarations without method bodies.
Multiple inheritance: A class can inherit multiple interfaces, but can only inherit one abstract class.
Constructor: Abstract classes can have constructors, but interfaces cannot have constructors.
Member variables: Abstract classes can contain member variables, while interfaces cannot contain member variables (before Java 8).
Design purpose: Abstract classes are used to describe the "is-a" relationship between classes, while interfaces are used to describe the "has-a" relationship between classes, and provide a mechanism for multiple inheritance.

### Jvm architecture
The JVM (Java Virtual Machine) architecture refers to the virtual machine environment that Java applications rely on when running. It is responsible for translating Java bytecode into machine code for a specific platform, and provides memory management, garbage collection, and security at runtime. and other functions. The basic architecture of JVM includes the following important components:
ClassLoader: The class loader is responsible for loading bytecode files into memory and converting them into runtime classes. The JVM has three built-in class loaders: Bootstrap ClassLoader, Extension ClassLoader and Application ClassLoader, which are responsible for loading class libraries in different paths.
Runtime Data Area: The runtime data area is the main part of the JVM memory and is used to store program data and runtime information. It mainly includes method area, heap, virtual machine stack (VM Stack), native method stack (Native Method Stack), program counter (Program Counter), etc.
Execution Engine: The execution engine is responsible for executing Java bytecode and converting it into machine code for execution. Execution engines usually include two modes: interpreter (Interpreter) and just-in-time compiler (Just-In-Time Compiler, JIT Compiler), which are used to improve program execution efficiency.
Garbage Collector: The garbage collector is responsible for managing objects in the heap memory, automatically reclaiming memory space that is no longer used, and preventing memory leaks and memory overflows. JVM has built-in different types of garbage collectors, such as Serial GC, Parallel GC, CMS GC, G1 GC, etc.
Native Interface: The native method interface allows Java applications to call native (Native) methods, that is, methods written in native languages ​​​​(such as C, C++). The native method interface enables Java programs to interact with the underlying system to achieve more advanced functionality and performance optimization.

Method Area:
The method area is part of the JVM and is used to store data such as metadata information, static variables, constant pools, and method bytecodes of the class.
The method area is a memory area shared by threads and is used to store loaded class information, including class structure information, static variables, constants and method codes, etc.
The method area is created when the JVM starts and is a logical part of the heap. However, it is different from the memory management of the heap and is usually implemented using the permanent generation (Permanent Generation).
Heap:
The heap is the memory area used by the JVM to store object instances, including objects, arrays, and class instances created through the new keyword.
The heap is a memory area shared by all threads and is used to store dynamically allocated object data. It is the most important memory allocation area in Java programs.
The management of heap memory is handled by the garbage collector, which is mainly used to recycle objects that are no longer used and release the memory space they occupy.
Virtual machine stack (VM Stack):
The virtual machine stack is a private memory area for each thread and is used to store information such as the thread's method call stack, local variable table, and operand stack.
Each method creates a stack frame when executed, which is used to store data such as local variables and operand stacks of the method.
The size of the virtual machine stack is fixed when the JVM is started. If the stack space is insufficient or an overflow occurs, a StackOverflowError exception will be thrown.
Native Method Stack:
The native method stack is similar to the virtual machine stack, but it is a stack space used to execute native methods (Native Method), that is, methods written in local languages ​​(such as C, C++).
The local method stack is also private to each thread and is used to perform local method calls that interact with Java programs, such as calling functions written in C language through JNI (Java Native Interface).
Program Counter:
The program counter is a memory area private to each thread that records the address or index of the bytecode instruction currently executed by the thread.
The program counter is the working pointer of the thread execution engine. It is used to record the location of thread execution and ensure the recovery and continued execution of the thread.
The program counter plays an important role in a multi-threaded environment, ensuring that threads can be accurately restored to their execution positions when switching and ensuring the correct execution order of threads.


### Java modifier scope: public, private, protected, default scope
Access modifiers in Java are used to control access to classes, variables, methods, and constructors. The main access modifiers include public, private, protected and default. Their scope of action is as follows:
public:
Classes, methods and variables modified by public can be accessed anywhere within the same package or in different packages.
The public access modifier has the greatest access rights, interfaces and functions exposed to the outside world.
private:
Classes, methods and variables modified by private can only be accessed within the class in which they are defined, and cannot be directly accessed by other classes.
The private access modifier provides the strictest access control and is used to hide the internal implementation details of the class.
protected:
Protected classes, methods and variables can be accessed within the same package and subclasses, but cannot be directly accessed in other packages.
The protected access modifier allows subclasses to access protected members of the parent class and is used to implement inheritance and polymorphism.
default:
When no access modifier is used for a member, the default access modifier is package-level access.
The default access modifier limits the access scope of classes, methods and variables to the same package and cannot be accessed by other packages.

### What is static scope
Static scope (Static Scope) means that the visible range of variables in the program is determined at compile time, not at run time. In a static scope, the visibility of a variable depends on where the variable is declared and the structure of the program, regardless of the execution path of the code.
In static scope, the scope of a variable begins at its declaration and extends to the end of the code block or function that contains the declaration. This means that variables declared in a code block or function are visible and accessible only within this code block or function, and are not visible in external code blocks or functions.
Static scope can ensure the reliability and maintainability of the program because the scope of the variable is determined at compile time and will not be affected by the runtime state of the program. This makes it easier for programmers to understand and debug code, avoiding errors caused by unclear variable scope.
Corresponding to the static scope is the dynamic scope (Dynamic Scope). The dynamic scope means that the visibility of the variable depends on the execution path and call stack of the program, rather than the declaration location of the variable. In dynamic scoping, a variable's scope is determined by the program's execution path and may have different visibility in different function calls. However, in most programming languages, including Java, static scoping is commonly used.

### how does classloader work
The class loader (ClassLoader) is an important component of the Java Virtual Machine (JVM), responsible for loading bytecode into memory and converting it into runtime classes. The class loader mainly completes the following tasks:
Loading: The class loader is responsible for finding and loading the bytecode file of the class. When a program needs to use a class, the class loader will find the corresponding bytecode file based on the name of the class and load it into memory.
Linking: The class loader links the loaded bytecode file into an executable binary format. The linking process includes three stages: verification, preparation and parsing:
Verification: Ensure that the loaded bytecode file complies with the Java virtual machine specifications and will not endanger the security of the virtual machine.
Preparation: Allocate memory for static variables of the class and initialize default values.
Resolution: Convert symbolic references into direct references, that is, resolve references to classes, fields, and methods into memory addresses.
Initialization: The class loader will perform static initialization of the class after the link is completed. This includes performing assignments to static variables and performing initialization logic in static code blocks.
The Java virtual machine has three built-in class loaders: Bootstrap ClassLoader, Extension ClassLoader and Application ClassLoader. They are respectively responsible for loading class libraries under different paths:
Bootstrap ClassLoader: Responsible for loading the Java core class library, usually stored in the lib directory of the JRE.
Extension ClassLoader: Responsible for loading jar packages in the JRE extension directory, usually stored in the JRE's lib/ext directory.
Application ClassLoader: Also known as the system class loader, it is responsible for loading the class library specified on the user classpath (classpath).
In addition to these three built-in class loaders, Java also supports custom class loaders. Custom class loaders can load classes from different sources based on specific needs, such as loading classes from the network, database, or other non-traditional storage media. The implementation of ClassLoader usually inherits the ClassLoader class and overrides its methods, such as findClass() method and loadClass() method.
In short, the class loader is an important component of the Java virtual machine, responsible for loading bytecode into memory and converting it into runtime classes. It implements class loading through loading, linking, and initialization processes, providing Java applications with the ability to dynamically load and run-time expansion.

### Homework 3 Question List (write necessary code to answer the following questions)

### Describe the difference between unchecked and checked exceptions in Java.
> In Java, exceptions are divided into two main types: Unchecked Exceptions and Checked Exceptions. The differences between them are as follows:
Unchecked Exceptions:
Unchecked exceptions are exceptions inherited from the RuntimeException class or its subclasses, such as NullPointerException, ArrayIndexOutOfBoundsException, etc.
The compiler does not require the programmer to explicitly catch or declare an unchecked exception in the code, so it is also called an unchecked exception.
Unchecked exceptions usually indicate program errors or logic errors, such as null pointer references, array index out of bounds, etc. These exceptions are usually caused by programmer error and therefore do not require forced handling at compile time.
Checked Exceptions:
Checked exceptions are exceptions that inherit from the Exception class, but are not exceptions from the RuntimeException class and its subclasses.
The compiler requires programmers to explicitly catch or declare checked exceptions in the code, otherwise an error will occur during compilation.
Checked exceptions usually represent problems caused by external factors, such as files not found, network connections being interrupted, etc. These exceptions are usually beyond the control of the programmer and therefore need to be handled at compile time to ensure the robustness and reliability of the program.
In short, unchecked exceptions are caused by program errors or logical errors and do not require explicit handling in the code; checked exceptions are caused by external factors or uncontrollable factors and need to be explicitly handled in the code to ensure the stability of the program. sex.

### What is the difference between finally, final, and finalize in Java?
> finally: finally is a keyword used to define a code block in a try-catch statement block, which will always be executed regardless of whether an exception occurs. The finally block is usually used to perform cleanup work, such as releasing resources, closing files, etc., to ensure that no matter what exception occurs in the try block, the resources will be released correctly. The finally block is optional, but if it is present, it will be executed at the end of the try block.
> final: final is a keyword used to declare constants and prohibit class inheritance or method overriding. When we declare a variable as final, its value cannot be modified. If a class is declared final, it means that the class is not inheritable and cannot have subclasses. If a method is declared final, it means that the method cannot be overridden by subclasses. The final keyword is usually used to improve the safety, stability and performance of the program.
> finalize: finalize is a method in the Object class, used to be called when the garbage collector performs object recycling. The finalize method is called before the object is garbage collected and can be used to perform some cleanup operations, such as releasing resources or closing connections. However, because the execution timing of the finalize method is uncertain and unreliable, it is not recommended to perform important cleanup operations in it. After Java 9, the finalize method has been deprecated and its use is no longer recommended.

### Define try-with resource. How can you say that it differs from an ordinary try?
> try-with-resource is a syntax introduced in Java 7 to more conveniently manage resources, such as I/O streams, database connections, etc. It allows us to open a resource within a try block and automatically close the resource at the end of the try block, regardless of whether an exception occurs. The try-with-resource syntax uses implementation classes of the AutoCloseable interface as resources, which are initialized in the try-with-resource declaration and automatically closed at the end of the try block.
Compared with ordinary try blocks, try-with-resource has the following important differences:
Automatically close resources: Resources declared in try-with-resource will be automatically closed at the end of the try block. There is no need to manually call the close() method to release the resource. This greatly simplifies resource management code and guarantees that resources are properly closed after use, even when an exception occurs.
Exception handling: In a normal try block, if an exception occurs, we need to manually close the resource in the finally block to ensure that the resource is released. In try-with-resource, the closing of the resource is handled by code automatically generated by the compiler. Regardless of whether an exception occurs, the resource will be closed correctly.
Simplicity and readability: The try-with-resource syntax is more concise and clear, making the code more readable and understandable. By initializing resources in the try-with-resource statement, we can know at a glance which resources are used in the try block and will be automatically closed at the end of the try block.
In short, try-with-resource provides a simpler and safer way to manage resources. Compared with traditional try blocks, it can automatically close resources, reduce code redundancy and errors, and improve code reliability. Maintainability and readability.

### Define Runtime Exception. Describe it with the help of an example.
> Runtime Exception refers to an exception that may occur during the running of the program. It usually does not need to be explicitly caught or declared to be thrown in the code. Unlike checked exceptions, runtime exceptions are usually caused by program errors or logic errors rather than external factors. Since runtime exceptions are usually due to programmer error, they do not need to be checked at compile time, but may cause the program to terminate abnormally at runtime.

### What is the difference between NoClassDefFoundError and ClassNotFoundException in Java
> NoClassDefFoundError (Class Definition Not Found Error): This exception indicates that the virtual machine found the bytecode of the class at runtime, but when trying to instantiate or access the class, it could not find the definition of the class. Typically this is because the class exists at compile time but is missing at runtime, possibly due to a wrong class path, a class being deleted or moved, a class loader issue, etc. NoClassDefFoundError is an error (Error), indicating a serious problem at the system level and is generally unrecoverable.
ClassNotFoundException (class not found exception): This exception indicates that a reference to a class exists at compile time, but the definition of the class cannot be found at run time. Usually, this is caused by class path errors, missing dependent libraries, JAR packages not being loaded, etc. ClassNotFoundException is a checked exception (Checked Exception) that needs to be explicitly caught or declared to be thrown in the code.
In short, NoClassDefFoundError represents a critical error when a class exists at compile time but is missing at runtime, while ClassNotFoundException represents an exception when the class definition cannot be found at runtime, possibly due to classpath issues or dependency issues.

### Why should we clean up activities such as I/O resources in the finally block?
> In Java, the main reason to clean up resources (such as I/O resources) is to ensure that the resources are released and closed correctly to avoid resource leaks and system resource exhaustion problems. The finally block is a mechanism commonly used in exception handling. It ensures that the code within it will be executed regardless of whether an exception occurs. Therefore, it is often used to clean up resources.
Here are a few important reasons why we should clean up activities (like I/O resources) in finally blocks:
Ensure resources are released: Closing I/O resources in the finally block ensures that the resources are released correctly when the program ends. This can avoid resource leaks, that is, resources are still held but cannot be released after the program is executed, resulting in a waste of system resources and possible memory overflow.
Handling exceptions: Exceptions may occur in the try block. If the exception occurs after opening the resource but before closing the resource, the resource may not be closed correctly, resulting in resource leakage. Placing the code that closes the resource in a finally block ensures that the resource is closed correctly regardless of whether an exception occurs.
Ensure the reliability of the code: Cleaning up resources in the finally block can enhance the reliability and robustness of the code. Even when the code in the try block throws an exception or returns, the code in the finally block will be executed, thus ensuring that resource cleanup is always performed.
In short, the main purpose of cleanup activities (such as I/O resources) is to ensure that resources are released and closed correctly to improve program stability and reliability. Placing the code that cleans up resources in a finally block ensures that the resource is closed correctly regardless of whether an exception occurs.

### Describe OutofMemoryError in exception handling.
> OutOfMemoryError is a runtime error (RuntimeException) in Java that indicates that the application is trying to use memory that exceeds the JVM's available memory limit. OutOfMemoryError is thrown when the JVM cannot allocate enough memory to meet the needs of the application.
OutOfMemoryError is usually caused by the following situations:
Memory leak: When there is a memory leak in the application, the memory usage will gradually increase, eventually causing the JVM to exhaust the available memory and throw an OutOfMemoryError. Memory leaks are usually caused by improper object reference management or resources that are not released correctly.
Excessive amount of data: When an application needs to process a large amount of data, if memory usage is not properly optimized, the JVM may be unable to allocate enough memory and throw an OutOfMemoryError.
Recursive calls lead to stack overflow: If there are too many recursive calls in the application, the method call stack may overflow, leading to OutOfMemoryError.
Because OutOfMemoryError is a serious error, once it occurs, it usually causes the application to crash. When handling OutOfMemoryError, the code usually needs to be optimized to reduce memory consumption, or to increase the JVM's available memory limit. In addition, you can also use monitoring and tuning tools to identify and solve memory leaks to prevent the occurrence of OutOfMemoryError.

### What is Generics in Java? What are the advantages of using Generics?
> Generics is a programming mechanism in Java that allows us to define the data types that classes, interfaces, and methods can operate on when writing code, and to specify specific types when using them. Using generics, we can write the code once and then reuse it on multiple data types to increase the flexibility and reusability of the code.

> The main advantages of using generics include:
Type safety: Generics enable the compiler to detect type mismatch errors at compile time, thereby reducing the possibility of type errors occurring at runtime. This improves the reliability and stability of your code.
Code reuse: Generics allow us to write code once and then reuse it on multiple data types. This can reduce the workload of repeatedly writing similar code and improve the maintainability and scalability of the code.
Readability and maintainability: By using generics, we can explicitly specify the data types that classes, interfaces, and methods operate on, making the code clearer and easier to understand. This reduces the need for comments and documentation and improves code readability and maintainability.
Avoid type conversion: Using generics avoids the tedious and error-prone process of manual type conversion. The compiler automatically inserts the necessary type conversion code, simplifying the process of writing code.

> In short, generics are an important programming mechanism in Java. They provide a convenient and safe way to handle multiple data types, and have the advantages of improving code readability, maintainability, and reusability.

### How Generics works in Java ? What is type erasure ?
> In Java, generics are a programming mechanism that allows us to specify the data types that classes, interfaces, and methods can operate on when writing code to increase the type safety and reusability of the code. Generics work by the compiler performing type checking at compile time and inserting type conversion code when necessary.
When we use generics, we can define a class, interface, or method in which one or more type parameters represent the data type to be operated on. Then, when using the class, interface, or method, we can specify specific types for these type parameters, so that the code can handle various types of data.
Generics work through type erasure. Type erasure is the process of converting a generic type to a primitive type at compile time. At compile time, type parameters of generic types are erased and replaced with their original types. This means that at runtime, instances of a generic type will no longer contain information about the types of its parameters. This mechanism of type erasure makes Java backwards compatible and allows generic code to interoperate with code that does not use generics.
In summary, generics are implemented through type erasure, which allows us to write code once to handle multiple data types and increases the safety of the code through type checking by the compiler at compile time.

### What is the difference between List<? extends T>  and  List <? super T>?
> List<? extends T> and List<? super T> are two ways of using generic wildcards in Java. 
There are some important differences between them:
List<? extends T>: This represents a list that can store any type inherited from T. In other words, it can be a subclass of T, but you can't add any elements to it because you don't know which subclass it is. But you can safely get elements from it and make sure they are of type T or a subtype of T.
List<? super T>: This represents a list of types that can store any superclass of T. In other words, it can be a parent class of T, but you can't know exactly which parent class it is. You can add elements of type T to it because you know it's at least a parent of T, but you can't safely get elements from it because you can't determine their exact type.
In short, List<? extends T> is used to safely get elements from a list, while List<? super T> is used to safely add elements to a list

```
import java.util.ArrayList;
import java.util.List;

class Animal {
    public void eat() {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal {
    public void bark() {
        System.out.println("Dog is barking");
    }
}

class Cat extends Animal {
    public void meow() {
        System.out.println("Cat is meowing");
    }
}

public class Main {
    public static void main(String[] args) {
        // use List<? super T>
        List<? super Dog> dogList1 = new ArrayList<>();
        
        dogList1.add(new Dog());
        dogList1.add(new Dog());
        
            // Since the compiler cannot determine the exact type of the element taken from the list, we can only store it in a variable of type Object        for (Object obj : dogList1) {
            // The method of the Animal class cannot be called because the exact type of the element cannot be determined
            // obj.eat(); // Compile Error
            
            // But elements can be cast to Dog type
            Dog dog = (Dog) obj;
            dog.eat();
            dog.bark();
        }
        
        
        // use List<? extends T>
        List<? extends Animal> animals = new ArrayList<>();
        
        List<Dog> dogList = new ArrayList<>();
        dogList.add(new Dog());
        dogList.add(new Dog());
        animals = dogList;
        
        for (Animal animal : animals) {
            animal.eat();
            // The following call is illegal because the compiler cannot determine the exact type of animal
            // animal.bark();
            // animal.meow();
        }
    }
}



```


### What is Optional class (write a demo code to use ofNullable, orElse, orElseThrow method)
> The Optional class is a container class in Java used to handle possibly null values. It avoids NullPointerException in your code and provides an elegant way to handle possible null situations.

> The main methods of the Optional class include:
ofNullable(T value): Creates an Optional instance containing the specified non-null value. If the specified value is null, an empty Optional is returned.
orElse(T other): Returns the value if it exists, otherwise returns the specified default value.
orElseThrow(Supplier<? extends X> exceptionSupplier): Returns the value if it exists, otherwise throws an exception using the provided exception supplier.

```
import java.util.Optional;

public class Main {
    public static void main(String[] args) {
        String value = null;

        // Create Optional instance using ofNullable method
        Optional<String> optional = Optional.ofNullable(value);

        // Use the orElse method to get the value, and if the value is empty, return the specified default value
        String result = optional.orElse("Default Value");
        System.out.println("Result using orElse: " + result); // output: Default Value

        // Use orElseThrow method to get the value, if the value is empty, throw an exception
        try {
            String result2 = optional.orElseThrow(() -> new IllegalArgumentException("Value cannot be null"));
        } catch (IllegalArgumentException e) {
            System.out.println("Exception thrown: " + e.getMessage()); // output: Value cannot be null
        }
    }
}


```
### what is functional interface

> In Java, a Functional Interface is an interface with only one abstract method. Functional interfaces can be implemented using Lambda expressions, which can be thought of as instances of functional interfaces.
Functional interfaces have the following characteristics:
Only one abstract method: There can be only one abstract method in a functional interface. This abstract method defines the functionality of the interface and can be implemented by Lambda expressions.
Can have default or static methods: A functional interface can contain default or static methods, but can have only one abstract method.
@FunctionalInterface annotation: Although it is not mandatory, functional interfaces are usually marked with the @FunctionalInterface annotation. This annotation ensures that the interface has only one abstract method. If more than one abstract method is defined in the interface, the compiler will report an error.
The introduction of functional interfaces in Java makes the Java language more flexible and powerful, making it easier to use Lambda expressions to implement some functions, such as event processing, thread processing, etc. Common functional interfaces include those defined in the java.util.function package, such as Predicate, Consumer, Supplier, Function, etc.

### What is default method
> In Java 8, the concept of default method (Default Method) of interfaces was introduced. Default methods allow defining methods with default implementations in an interface without affecting classes that already implement the interface. This feature was introduced to support the gradual evolution of interfaces, allowing new methods to be added to existing interfaces without destroying existing implementation classes.

```java
public interface MyInterface {
    
    void method1();

    default void defaultMethod() {
    }
}
```

> When a default method is defined in an interface, the class that implements the interface can choose whether to override the default method. If the default method is overridden, the overridden implementation will be used, otherwise the default implementation defined in the interface will be used.


### what is the difference between Predicate, Supplier, Consumer, Function?
> Predicate interface: The Predicate interface represents an assertion, which accepts an input parameter and returns a Boolean result. Usually used to filter elements in a collection or perform conditional judgments.
The Supplier interface represents a supplier, it does not accept any parameters and returns a result. Typically used to delay calculations or provide default values.
The Consumer interface represents a consumer, which accepts an input parameter but does not return a result. Usually used to perform certain operations or process input data.
The Function interface represents a function that accepts an input parameter and returns a result. Typically used to transform or map data.

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

> Method references are a syntax in Java used to simplify writing lambda expressions. It allows you to directly reference an existing method instead of writing a lambda expression to call it.

> There are several types of method references:

1. **Reference to a static method:** `ContainingClass::staticMethodName`
2. **Reference to an instance method of a particular object:** `objectReference::instanceMethodName`
3. **Reference to an instance method of an arbitrary object of a particular type:** `ContainingType::methodName`
4. **Reference to a constructor:** `ClassName::new`

> For example, consider a `Comparator` interface with a method `int compare(T o1, T o2)`. Instead of writing a lambda expression like `(o1, o2) -> o1.compareTo(o2)`, you can use a method reference `T::compareTo`.



