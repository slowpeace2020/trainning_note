### 1. What is the automatic unboxing/boxing in Java
2. What is the difference between & and &&?
3. Can switch work on byte/long/String?
4. What are the differences and functions of break, continue and return?
5. What is the difference between object-oriented and process-oriented?
6. What are the characteristics of object-oriented programming?
7. What problem does polymorphism solve?
8. What does the this keyword do?
9. What are the differences between member variables and local variables? 
12. What is the difference between == and equals?
13. Have you ever rewritten hashcode and equals? Why do you have to rewrite the hashCode method when rewriting equals?
14. Is String a Java basic data type? Can it be inherited?
17. What is Integer cache?
18. What are Common methods of Object class?
19. How many types of IO streams are there in Java?
20. Now that we have a byte stream, why do we need a character stream?
21. What are the difference between BIO, NIO and AIO
22. What is serialization? 
23. What is deserialization?
24. What is reflection?
25. How much do you know about Lambda expressions?
26. What are the common collection frameworks?
27. Do you understand the expansion mechanism of ArrayList?
28. Do you understand fail-fast and fail-safe?
29. How much do you know about CopyOnWriteArrayList?
30. Can you tell me about the data structure of HashMap?
31. How much do you know about red-black trees? Why not use binary tree/balanced tree?
32. Do you know the put process of HashMap?
33. How to find elements in HashMap?
34. How is the hash function of HashMap designed?
35. Why can the hash function reduce hash collisions?
36. Why is the capacity of HashMap a multiple of 2?
37. If you initialize a HashMap and pass a capacity of 17, what will it do?
38. What are the methods to resolve hash conflicts?
39. When will the HashMap capacity be expanded? 
40. Why is the expansion factor 0.75?
40. Do you understand the HashMap expansion mechanism?
41. What main optimizations has jdk1.8 made to HashMap? Why?
42. Is HashMap thread-safe? What are the problems with multi-threading?
43. Is there any way to solve the thread insecurity problem of HashMap?
44. Are the internal nodes of HashMap ordered?
45. How LinkedHashMap achieves ordering?
46. How to achieve ordering in TreeMap?
47. The difference between TreeMap and HashMap
48. Tell me about the underlying implementation of HashSet?
49. What is the difference between parallelism and concurrency?
50. What are processes and threads?
51. How to understand coroutines?
52. What is shared memory of threads?
53. Why is the run() method executed when the start() method is called? Why not call the run() method directly?
54. What are the commonly used scheduling methods for threads?
55. What is the difference between sleep and wait?
56. What is thread context switching?
57. Do you understand daemon threads?
58. What are the communication methods between threads?

59. Is there any solution to the thread safety issue?
60. What is ThreadLocal?
61. How is ThreadLocal implemented?
62. What is a weak reference 
63. what is a strong reference?
63. what is a soft reference?
63. what is a virtual reference?
63. What's going on with ThreadLocal memory leaks?
64. Tell me about your understanding of the Java memory model?
65. Why do threads need to use their own memory?
66. Tell me about your understanding of atomicity?
66. Tell me about your understanding of visibility?
66. Tell me about your understanding of order?
67. So what is instruction rearrangement?
68. Do you understand the implementation principle of volatile?
69. Tell me about thread synchronization
70. In addition to atomicity, how to achieve synchronized visibility, orderliness, and reentrancy?
71. What optimizations has synchronized done?
72. What is the difference between synchronized and ReentrantLock?
73.  Tell me about your understanding of AQS?
74. ReentrantLock implementation principle?
75. How does ReentrantLock achieve fair locking?
76. Tell me about your understanding of CAS?
77. What methods does Java have to ensure atomicity? How to ensure that i++ results are correct under multi-threading?
78. How much do you know about the atomic operation class?
79. How to troubleshoot the deadlock problem?
80. Can you tell me about the implementation of ConcurrentHashMap?
81. How does ConcurrentHashMap ensure visibility?
82. Why ConcurrentHashMap is more efficient than Hashtable
83. Do you understand CountDownLatch (countdown counter)?
84. Do you understand CyclicBarrier (synchronization barrier)?
85. What is the difference between CyclicBarrier and CountDownLatch?
86. Do you understand Semaphore?
88. What are the rejection policies of the thread pool?
89. What kind of work queues does the thread pool have?
90. What is the difference between thread pool submission execute and submit?
91. Do you know how to close the thread pool?
92. How should the number of threads in the thread pool be configured?
93. What are the common thread pools?
95. Do you know how to handle thread pool exceptions?
96. Can you tell me how many states the thread pool has?
97. What should you pay attention to when using the thread pool?
99. Talk about the garbage collection mechanism of JVM

### 1. What is the automatic unboxing/boxing in Java

Automatic boxing and unboxing in Java are features introduced in Java 5 (JDK 5.0) to simplify the process of converting between primitive types and their corresponding wrapper classes (e.g., `int` and `Integer`). These features automatically handle the conversion between primitive types and their wrapper classes, making code more concise and readable.

1. **Boxing**:
    - Boxing is the process of converting a primitive type into its corresponding wrapper class. For example, converting an `int` to an `Integer`.
    - When you assign a primitive value to a variable of a wrapper class, Java automatically boxes the primitive value into an object of the wrapper class.
    - Example:
      ```java
      int intValue = 10;
      Integer integerValue = intValue; // Boxing: int to Integer
      ```

2. **Unboxing**:
    - Unboxing is the process of converting a wrapper class object back to its corresponding primitive type.
    - When you assign a wrapper class object to a variable of a primitive type, Java automatically unboxes the wrapper object and extracts the primitive value.
    - Example:
      ```java
      Integer integerValue = 20;
      int intValue = integerValue; // Unboxing: Integer to int
      ```

3. **Automatic Conversion**:
    - Boxing and unboxing are automatically performed by the Java compiler, so you don't need to explicitly call wrapper class constructors or methods like `valueOf()` and `intValue()`.
    - This makes code more concise and readable by reducing the need for explicit conversion code.
    - Example:
      ```java
      // Before Java 5 (without autoboxing/unboxing)
      Integer integerValue = Integer.valueOf(30); // Explicit boxing
      int intValue = integerValue.intValue();     // Explicit unboxing
 
      // With autoboxing/unboxing (Java 5 and later)
      Integer integerValue = 30; // Automatic boxing
      int intValue = integerValue; // Automatic unboxing
      ```

4. **Performance Considerations**:
    - While automatic boxing and unboxing provide convenience, they can also have performance implications if used excessively in performance-critical code. Each boxing and unboxing operation involves the creation of wrapper objects, which can incur overhead in terms of memory allocation and garbage collection.
    - It's important to use automatic boxing and unboxing judiciously, especially in performance-sensitive code where manual conversion may be more efficient.

In summary, automatic boxing and unboxing in Java simplify the conversion between primitive types and their corresponding wrapper classes by automatically handling the conversion process, making code more concise and readable. However, care should be taken to avoid excessive use in performance-critical code.

### 2. What is the difference between & and &&?
   In Java, the `&` and `&&` operators are both used for performing logical AND operations, but they have different behaviors and are used in different contexts:

1. **Single Ampersand (`&`)**:
    - The single ampersand (`&`) is a bitwise AND operator when used with integer types (byte, short, int, long). It performs a bitwise AND operation on the corresponding bits of the operands.
    - When used with boolean operands, the single ampersand (`&`) is a logical AND operator. It evaluates both operands and returns `true` if both operands are `true`, otherwise it returns `false`.
    - The single ampersand (`&`) always evaluates both sides of the expression, even if the left operand is `false`.

2. **Double Ampersand (`&&`)**:
    - The double ampersand (`&&`) is a short-circuit logical AND operator. It behaves similarly to the single ampersand (`&`) when used with boolean operands, but with one key difference: it short-circuits the evaluation of the right operand if the left operand evaluates to `false`.
    - If the left operand of `&&` is `false`, the right operand is not evaluated because the overall result will be `false` regardless of the right operand's value.
    - Short-circuiting can be useful for improving performance and avoiding unnecessary evaluations, especially when the right operand involves expensive computations or side effects.

Here's a summary of the differences between `&` and `&&`:

- `&`: Bitwise AND operator for integer types; Logical AND operator for boolean operands; Always evaluates both sides.
- `&&`: Short-circuit logical AND operator for boolean operands; Evaluates the right side only if the left side is `true`.

Example:

```java
int a = 5;
int b = 10;

// Bitwise AND
int result1 = a & b; // result1 = 0

boolean x = true;
boolean y = false;

// Logical AND with single ampersand
boolean result2 = x & y; // result2 = false

// Logical AND with double ampersand
boolean result3 = x && y; // result3 = false

// Short-circuiting behavior
boolean result4 = y && (a / 0 > 0); // Since y is false, the right operand is not evaluated (avoids division by zero error)
```

In summary, `&` is used for bitwise AND operations and both logical AND operations, while `&&` is specifically used for short-circuiting logical AND operations with boolean operands.

### 3. Can switch work on byte/long/String?
In Java, the `switch` statement can work with `byte`, `short`, `char`, `int`, `enum`, and `String` types. However, it cannot directly work with `long` or any other non-integer types apart from `char`.

Here's how `switch` statements work with different types:

1. **Integer Types (`byte`, `short`, `char`, `int`)**:
    - You can use `byte`, `short`, `char`, and `int` with `switch` statements. These types are implicitly converted to `int` before being used in the `switch` statement.
    - Example:
      ```java
      byte b = 2;
      switch (b) {
          case 1:
              // Case for value 1
              break;
          case 2:
              // Case for value 2
              break;
          default:
              // Default case
      }
      ```

2. **Enum Types**:
    - You can use `enum` types with `switch` statements. Each enum constant corresponds to a case label.
    - Example:
      ```java
      enum Color { RED, GREEN, BLUE }
 
      Color color = Color.GREEN;
      switch (color) {
          case RED:
              // Case for RED
              break;
          case GREEN:
              // Case for GREEN
              break;
          case BLUE:
              // Case for BLUE
              break;
      }
      ```

3. **String Type**:
    - Since Java 7, you can use `String` with `switch` statements. Each case label must be a constant expression (literal or `final` variable).
    - Example:
      ```java
      String day = "Monday";
      switch (day) {
          case "Monday":
              // Case for Monday
              break;
          case "Tuesday":
              // Case for Tuesday
              break;
          // Other cases
          default:
              // Default case
      }
      ```

4. **Long Type**:
    - `long` cannot be directly used with `switch` statements. Attempting to use `long` will result in a compilation error.
    - If you need to use a `long` value in a `switch`-like construct, consider using an `if-else` ladder or other control flow structures.

In summary, `switch` statements in Java can work with `byte`, `short`, `char`, `int`, `enum`, and `String` types, but not with `long` or other non-integer types.

### 4. What are the differences and functions of break, continue and return?
`break`, `continue`, and `return` are control flow statements in Java that serve different purposes and have different behaviors:

1. **break**:
    - The `break` statement is used to terminate the execution of a loop (such as `for`, `while`, or `do-while`) or a `switch` statement prematurely.
    - When a `break` statement is encountered inside a loop or `switch` statement, the control flow exits the innermost enclosing loop or `switch` statement, and execution continues with the next statement after the loop or `switch` block.
    - Example:
      ```java
      for (int i = 0; i < 5; i++) {
          if (i == 3) {
              break; // Exit loop when i equals 3
          }
          System.out.println(i);
      }
      ```

2. **continue**:
    - The `continue` statement is used to skip the current iteration of a loop and continue with the next iteration.
    - When a `continue` statement is encountered inside a loop, the remaining code inside the loop for the current iteration is skipped, and the loop proceeds with the next iteration.
    - Example:
      ```java
      for (int i = 0; i < 5; i++) {
          if (i == 3) {
              continue; // Skip iteration when i equals 3
          }
          System.out.println(i);
      }
      ```

3. **return**:
    - The `return` statement is used to exit a method prematurely and optionally return a value to the caller.
    - When a `return` statement is encountered inside a method, the method immediately terminates, and control flow returns to the caller. If the method has a return type, it must return a value of the appropriate type (unless the return type is `void`).
    - Example:
      ```java
      public int add(int a, int b) {
          return a + b; // Return sum of a and b
      }
      ```

4. **Differences**:
    - `break` is used to exit loops and switch statements prematurely.
    - `continue` is used to skip the remaining code in the current iteration of a loop and proceed with the next iteration.
    - `return` is used to exit methods prematurely and optionally return a value to the caller.

In summary, `break`, `continue`, and `return` are control flow statements in Java used for different purposes: `break` for exiting loops and switch statements, `continue` for skipping iterations in loops, and `return` for exiting methods and returning values to the caller.

### 5. What is the difference between object-oriented and process-oriented?
Object-oriented programming (OOP) and process-oriented programming (POP) are two different paradigms used for software development, each with its own approach to solving problems and organizing code. Here are the key differences between them:

1. **Abstraction**:
    - **Object-Oriented Programming (OOP)**: OOP emphasizes modeling real-world entities as objects, which have both state (attributes) and behavior (methods). Objects encapsulate data and behavior, and interactions between objects occur through method calls and message passing.
    - **Process-Oriented Programming (POP)**: POP focuses on breaking down a problem into a series of steps or procedures. Programs are organized as sequences of instructions that manipulate data, typically using functions or procedures to perform specific tasks.

2. **Data Encapsulation**:
    - **OOP**: OOP promotes data encapsulation, where data (attributes) and behavior (methods) are bundled together within objects. Objects control access to their internal data, exposing only necessary interfaces to the outside world.
    - **POP**: In POP, data and functions are separate entities. Data is typically stored in variables that can be accessed and modified directly by functions.

3. **Inheritance**:
    - **OOP**: Inheritance allows new classes (subclasses or derived classes) to inherit properties and behavior from existing classes (superclasses or base classes). This promotes code reuse and supports the "is-a" relationship between classes.
    - **POP**: POP does not inherently support inheritance. Code reuse is typically achieved by duplicating or replicating code across different functions.

4. **Polymorphism**:
    - **OOP**: Polymorphism allows objects of different classes to be treated as objects of a common superclass through method overriding and method overloading. This enables dynamic method dispatch and facilitates code flexibility and extensibility.
    - **POP**: POP does not inherently support polymorphism. Code behavior is typically determined statically based on the function being called.

5. **Modularity**:
    - **OOP**: OOP promotes modularity by organizing code into classes and objects, which can be independently developed, tested, and maintained. Objects interact through well-defined interfaces, promoting code separation and reusability.
    - **POP**: POP organizes code into functions or procedures, which are typically grouped based on related tasks or functionalities. Modularity is achieved by breaking down tasks into smaller, manageable units of code.

6. **Example**:
    - **OOP**: Examples of OOP languages include Java, C++, Python, and C#. In Java, for instance, you would create classes representing real-world entities (e.g., `Car`, `Person`) with attributes and methods.
    - **POP**: Examples of POP languages include C, Pascal, and assembly language. In C, for example, you would write functions to perform specific tasks (e.g., `calculateArea()`, `displayMessage()`).

In summary, object-oriented programming (OOP) emphasizes modeling real-world entities as objects with state and behavior, while process-oriented programming (POP) focuses on breaking down problems into sequences of steps or procedures. OOP promotes data encapsulation, inheritance, polymorphism, and modularity, whereas POP emphasizes sequential execution of tasks using functions or procedures.
### 6. What are the characteristics of object-oriented programming?
Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects," which are instances of classes that encapsulate data (attributes) and behavior (methods). OOP is characterized by several key features that distinguish it from other programming paradigms. Here are the main characteristics of object-oriented programming:

1. **Encapsulation**:
    - Encapsulation refers to the bundling of data (attributes) and methods (behavior) that operate on the data within a single unit, called an "object." Objects encapsulate the state of an entity and control access to that state through methods, providing a way to ensure data integrity and hide implementation details from the outside world.

2. **Abstraction**:
    - Abstraction is the process of simplifying complex systems by modeling them at higher levels of abstraction. In OOP, abstraction is achieved through classes and interfaces, which define abstract data types with properties and behaviors relevant to the problem domain. Abstraction allows programmers to focus on essential aspects of an entity while hiding irrelevant details.

3. **Inheritance**:
    - Inheritance is a mechanism that allows a new class (subclass or derived class) to inherit properties and behaviors from an existing class (superclass or base class). Subclasses can extend or modify the behavior of their superclass, promoting code reuse and facilitating the creation of hierarchical class structures. Inheritance supports the "is-a" relationship between classes, where a subclass is a specialized version of its superclass.

4. **Polymorphism**:
    - Polymorphism allows objects of different classes to be treated as objects of a common superclass through method overriding and method overloading. This enables dynamic method dispatch, where the appropriate method implementation is determined at runtime based on the actual type of the object. Polymorphism enhances code flexibility and extensibility, allowing programs to be written in a more generic and reusable manner.

5. **Modularity**:
    - Modularity is the principle of organizing code into independent, reusable modules or components. In OOP, classes serve as modular units of code, encapsulating related data and behavior into cohesive units. Modular design promotes code reusability, maintainability, and scalability by allowing components to be developed, tested, and maintained independently.

6. **Message Passing**:
    - In OOP, objects communicate and interact with each other by sending messages. Message passing involves invoking methods on objects to perform actions or exchange information. Objects can collaborate by invoking methods on each other, allowing for flexible and dynamic interactions between components of a system.

7. **Association**:
    - Association represents the relationship between classes, where one class is connected to another class through a reference or association link. Associations can be one-to-one, one-to-many, or many-to-many, depending on the cardinality of the relationship. Associations enable objects to collaborate and interact with each other, forming complex relationships within a system.

In summary, object-oriented programming (OOP) is characterized by encapsulation, abstraction, inheritance, polymorphism, modularity, message passing, and association. These features enable developers to create modular, reusable, and maintainable software systems by modeling real-world entities as objects with well-defined behaviors and relationships.

### 7. What problem does polymorphism solve?
Polymorphism solves the problem of needing to handle different types of objects in a uniform manner within a program. In object-oriented programming, polymorphism allows objects of different classes to be treated as objects of a common superclass. This enables you to write code that operates on objects of a superclass without needing to know the specific subclass type at compile time.

Here are the main problems that polymorphism helps to solve:

1. **Flexibility and Extensibility**:
    - Polymorphism allows you to write code that is more flexible and extensible by operating on objects at a higher level of abstraction. This means you can write code that works with a superclass interface, and later, if new subclasses are added, they can seamlessly integrate with the existing code without modification.

2. **Code Reusability**:
    - Polymorphism promotes code reusability by enabling you to write generic algorithms and behaviors that can be applied to objects of multiple subclasses. This reduces code duplication and promotes modular design, as common functionality can be implemented once in a superclass and reused across multiple subclasses.

3. **Ease of Maintenance**:
    - Polymorphism simplifies the maintenance of code by reducing dependencies on specific subclass implementations. Changes made to a superclass or its methods automatically propagate to all subclasses, ensuring consistent behavior across the application. This makes it easier to update and modify the codebase without affecting other parts of the system.

4. **Dynamic Dispatch**:
    - Polymorphism enables dynamic dispatch, where the appropriate method implementation is determined at runtime based on the actual type of the object. This allows for flexible and dynamic behavior, as the method invoked can vary depending on the actual type of the object. Dynamic dispatch supports late binding, where method calls are resolved dynamically at runtime, rather than statically at compile time.

5. **Enhanced Code Readability and Maintainability**:
    - Polymorphism improves code readability and maintainability by allowing you to write code that operates on objects at a higher level of abstraction, without needing to be concerned with the specific details of each subclass implementation. This makes the codebase easier to understand, debug, and maintain over time.

In summary, polymorphism solves the problem of needing to handle different types of objects in a uniform manner by enabling objects of different classes to be treated as objects of a common superclass. This promotes flexibility, extensibility, code reusability, ease of maintenance, dynamic dispatch, and enhanced code readability and maintainability in object-oriented programs.

### 8. What does the this keyword do?
In Java, the `this` keyword is a reference to the current object within an instance method or constructor. It can be used to refer to instance variables, invoke other constructors in the same class, or pass the current object as an argument to other methods.

Here are the main uses of the `this` keyword:

1. **Referencing Instance Variables**:
    - When a method or constructor is invoked on an object, the `this` keyword can be used to refer to instance variables of the current object. This is useful when there is ambiguity between local variables and instance variables with the same name.
    - Example:
      ```java
      public class MyClass {
          private int value;
 
          public void setValue(int value) {
              this.value = value; // Assign value to instance variable
          }
      }
      ```

2. **Invoking Other Constructors**:
    - Within a constructor, the `this` keyword can be used to invoke other constructors in the same class. This allows constructor chaining, where one constructor can call another constructor to perform common initialization tasks.
    - Example:
      ```java
      public class MyClass {
          private int value;
 
          public MyClass() {
              this(0); // Invoke parameterized constructor with default value
          }
 
          public MyClass(int value) {
              this.value = value; // Assign value to instance variable
          }
      }
      ```

3. **Passing the Current Object**:
    - The `this` keyword can be used to pass the current object as an argument to other methods. This is commonly used in method chaining or when passing the current object to other objects for further processing.
    - Example:
      ```java
      public class MyClass {
          public void doSomething() {
              // Pass the current object to another method
              someOtherMethod(this);
          }
 
          private void someOtherMethod(MyClass obj) {
              // Process the current object
          }
      }
      ```

4. **Returning the Current Object**:
    - In fluent interfaces or builder patterns, the `this` keyword can be used to return the current object from a method, allowing method calls to be chained together.
    - Example:
      ```java
      public class MyClass {
          private int value;
 
          public MyClass setValue(int value) {
              this.value = value;
              return this; // Return the current object
          }
      }
 
      // Method chaining example
      MyClass obj = new MyClass().setValue(10);
      ```

In summary, the `this` keyword in Java is a reference to the current object within an instance method or constructor. It can be used to reference instance variables, invoke other constructors, pass the current object as an argument, or return the current object from a method.

### 9. What are the differences between member variables and local variables?
Member variables (also known as instance variables) and local variables are two types of variables in Java, each with distinct characteristics and scopes. Here are the main differences between them:

1. **Scope**:
    - **Member Variables**: Member variables are declared within a class but outside of any method, constructor, or block. They are accessible to all methods and constructors within the class and can be accessed using the instance of the class.
    - **Local Variables**: Local variables are declared within a method, constructor, or block (such as a loop or conditional statement). They are only accessible within the block where they are declared and have limited scope.

2. **Lifetime**:
    - **Member Variables**: Member variables exist as long as the object of the class exists. They are created when an object of the class is instantiated and are destroyed when the object is garbage collected.
    - **Local Variables**: Local variables exist only within the block where they are declared and are destroyed when the block is exited. They do not persist beyond the execution of the method, constructor, or block in which they are declared.

3. **Initialization**:
    - **Member Variables**: Member variables can have default values assigned to them if not explicitly initialized. They are initialized when an object of the class is created and can be explicitly initialized using constructors or assignment statements.
    - **Local Variables**: Local variables must be explicitly initialized before they are used. They do not have default values and will result in a compilation error if accessed before being initialized.

4. **Access Modifiers**:
    - **Member Variables**: Member variables can have access modifiers (e.g., `public`, `private`, `protected`, or package-private) that control their visibility and accessibility from other classes.
    - **Local Variables**: Local variables cannot have access modifiers. They are only accessible within the block where they are declared and are not visible to other methods or classes.

5. **Concurrency**:
    - **Member Variables**: Member variables are shared among all methods and threads that have access to the object. Access to member variables from multiple threads must be properly synchronized to avoid race conditions and ensure thread safety.
    - **Local Variables**: Local variables are thread-safe by nature since they are confined to the execution of a single method or block. They are not shared among threads and do not require explicit synchronization.

In summary, member variables (instance variables) and local variables differ in terms of scope, lifetime, initialization, access modifiers, and concurrency considerations. Member variables are associated with objects of a class, have class-wide scope, and persist as long as the object exists. Local variables are associated with method execution, have limited scope, and exist only within the block where they are declared.
### 12. What is the difference between == and equals?
In Java, the `==` operator and the `equals()` method are used for comparison, but they serve different purposes and behave differently depending on the types of operands involved:

1. **`==` Operator**:
    - The `==` operator is a binary operator used to compare the equality of two operands.
    - For primitive types (e.g., `int`, `double`, `boolean`), `==` compares the actual values of the operands. If the values are equal, the result is `true`; otherwise, it is `false`.
    - For reference types (e.g., objects), `==` compares the references (memory addresses) of the objects, not their contents. It checks whether two references point to the same object in memory.
    - Example:
      ```java
      int a = 5;
      int b = 5;
      System.out.println(a == b); // true (values are equal)
      
      String str1 = new String("Hello");
      String str2 = new String("Hello");
      System.out.println(str1 == str2); // false (different memory addresses)
      ```

2. **`equals()` Method**:
    - The `equals()` method is a method defined in the `Object` class, which is the superclass of all classes in Java. It is used to compare the contents (values) of objects for equality.
    - The `equals()` method must be overridden in user-defined classes to provide meaningful comparison based on the object's state (contents).
    - By default, the `equals()` method in the `Object` class compares the references (memory addresses) of objects, similar to the `==` operator.
    - Example:
      ```java
      String str1 = new String("Hello");
      String str2 = new String("Hello");
      System.out.println(str1.equals(str2)); // true (contents are equal)
      ```

In summary, the main difference between `==` and `equals()` is:

- `==` compares the references (memory addresses) of objects for reference types, while it compares the values of operands for primitive types.
- `equals()` compares the contents (values) of objects for equality. It must be explicitly overridden in user-defined classes to provide meaningful comparison based on the object's state.
### 13. what’s the relationship between hashcode and equals? Have you ever rewritten hashcode and equals? Why do you have to rewrite the hashCode method when rewriting equals?
The relationship between `hashCode()` and `equals()` methods in Java is crucial when dealing with objects that are stored in hash-based collections like `HashMap`, `HashSet`, and others. Understanding this relationship ensures correct behavior when objects are used as keys or elements in such collections.

Here's the relationship between `hashCode()` and `equals()`:

1. **Consistency**:
    - According to the Java documentation, if two objects are equal according to the `equals()` method, then their hash codes returned by the `hashCode()` method must be equal as well.
    - Conversely, if two objects have the same hash code (as returned by the `hashCode()` method), it does not necessarily mean that they are equal according to the `equals()` method. This situation is known as a hash collision.

2. **Contract**:
    - The `hashCode()` and `equals()` methods must follow the contract defined in the `Object` class:
        - If `equals()` returns `true` for two objects, their `hashCode()` values must be the same.
        - If `hashCode()` values are the same for two objects, it does not guarantee that they are equal according to the `equals()` method. However, it's a good practice to override `equals()` whenever you override `hashCode()` to maintain consistency.

3. **Usage in Hash-Based Collections**:
    - Hash-based collections in Java rely on the hash code to efficiently store and retrieve objects. When an object is added to a hash-based collection, its `hashCode()` method is called to determine the bucket where it should be stored.
    - Later, when searching for an object in the collection, the `hashCode()` method is used to find the appropriate bucket, and then the `equals()` method is called to check for actual equality within that bucket.

4. **Override Both Methods**:
    - When overriding the `equals()` method in a class, it's recommended to also override the `hashCode()` method to ensure consistency. This ensures that two objects that are considered equal according to `equals()` produce the same hash code.
    - If you override `hashCode()`, you must ensure that it complies with the general contract defined in the `Object` class. Specifically, equal objects must produce the same hash code.

In summary, the `hashCode()` and `equals()` methods are closely related in Java, especially when dealing with hash-based collections. They must be implemented correctly and consistently to ensure proper behavior when objects are used as keys or elements in such collections.
### 14. Is String a Java basic data type? Can it be inherited?
In Java, `String` is not considered a primitive data type like `int`, `double`, `boolean`, etc. Instead, it is a class that represents a sequence of characters. Despite not being a primitive data type, `String` is one of the most commonly used types in Java due to its versatility and importance in representing textual data.

Being a class, `String` can indeed be inherited like any other class in Java. However, `String` is a final class, which means it cannot be subclassed. This design decision was made to ensure the immutability and security of `String` objects.

Immutability means that once a `String` object is created, its state (the sequence of characters it represents) cannot be changed. This property is crucial for various reasons, including thread safety, security (e.g., preventing password modification), and efficiency (e.g., caching and optimization).

Because `String` is final, it cannot be subclassed, and therefore it cannot be directly inherited by other classes. Any attempt to subclass `String` will result in a compilation error.

While you cannot subclass `String`, you can still use it in inheritance hierarchies as a superclass. For example, you can create subclasses that inherit from other classes and use `String` as a member variable, method parameter, or return type.

Here's an example of using `String` in an inheritance hierarchy:

```java
public class Person {
    private String name;

    public Person(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }
}

public class Student extends Person {
    private int studentId;

    public Student(String name, int studentId) {
        super(name);
        this.studentId = studentId;
    }

    public int getStudentId() {
        return studentId;
    }
}
```

In this example, the `Student` class inherits from the `Person` class, which has a `String` member variable `name`. While `Student` doesn't directly subclass `String`, it still uses `String` as part of its implementation.

### 17. What is Integer cache?
The Integer cache is an optimization technique used in Java to cache and reuse frequently used `Integer` objects within a certain range. This optimization is implemented for the `Integer` class (and similarly for `Byte`, `Short`, `Long`, `Character`) to improve memory utilization and performance.

In Java, `Integer` objects are typically created using the `Integer.valueOf(int)` method or by autoboxing (automatic conversion of primitive types to their corresponding wrapper objects). When you create an `Integer` object using these methods, Java checks if the requested integer value falls within a predefined range (typically -128 to 127 for `Integer`).

If the requested integer value falls within this range, Java checks if an `Integer` object representing that value already exists in the cache. If it does, the existing `Integer` object from the cache is returned instead of creating a new one. If it doesn't exist in the cache, a new `Integer` object is created and added to the cache for future reuse.

The Integer cache provides several benefits:

1. **Memory Optimization**: By reusing `Integer` objects from the cache, memory consumption is reduced, as multiple references to the same integer value point to the same `Integer` object in memory.

2. **Performance Improvement**: Reusing `Integer` objects from the cache eliminates the overhead of creating new objects, which can improve performance, especially in scenarios where a large number of `Integer` objects are created and discarded frequently.

3. **Equals Comparison**: Since cached `Integer` objects are reused, you can safely use the `==` operator for equality comparison of `Integer` objects within the cached range, as they reference the same object in memory.

It's important to note that the range of cached `Integer` values (-128 to 127 by default) is implementation-dependent and can vary between different Java Virtual Machine (JVM) implementations. Additionally, the cache behavior can be altered using JVM flags or system properties to adjust the range or disable caching altogether if necessary.

### 18. What are Common methods of Object class?
The `Object` class in Java is the root class for all other classes. It defines several common methods that are inherited by all other classes unless overridden. Some of the most commonly used methods of the `Object` class include:

1. **`toString()`**:
   - Returns a string representation of the object. By default, this method returns a string consisting of the class name followed by the "@" character and the object's hash code.

2. **`equals(Object obj)`**:
   - Compares this object with another object for equality. By default, it returns `true` if and only if the specified object is also an instance of the `Object` class and represents the same object as this instance (i.e., they have the same memory address).

3. **`hashCode()`**:
   - Returns a hash code value for the object. By default, this method returns the internal memory address of the object as its hash code. It is used in hash-based collections such as `HashMap` and `HashSet`.

4. **`getClass()`**:
   - Returns the runtime class of this object. It returns an instance of the `Class` class that represents the runtime class of the object. This method is often used for runtime type checking and reflection.

5. **`clone()`**:
   - Creates and returns a copy of this object. This method performs a shallow copy, meaning it creates a new object with the same field values as the original object. For a deep copy, you may need to override this method.

6. **`finalize()`**:
   - Called by the garbage collector before the object is reclaimed. This method is deprecated and should not be relied upon for resource cleanup. It's recommended to use try-with-resources or other resource management techniques instead.

7. **`notify()`**, **`notifyAll()`**, **`wait()`**:
   - Methods for inter-thread communication and synchronization. These methods are used in conjunction with the `wait()` and `notify()` mechanism for managing threads and synchronization.

These are some of the commonly used methods of the `Object` class. It's important to note that while these methods have default implementations in the `Object` class, they can be overridden in subclasses to provide custom behavior as needed. Additionally, Java provides other utility classes and interfaces, such as `java.util.Objects`, `Comparable`, and `Iterable`, which offer additional functionality for working with objects and collections.

### 19. How many types of IO streams are there in Java?
In Java, there are two main types of I/O (Input/Output) streams:

1. **Byte Streams**:
   - Byte streams, represented by classes in the `java.io` package, are used for reading and writing raw binary data as streams of bytes. They are suitable for handling input/output operations for binary files (such as images, audio files, and non-text files) and low-level data handling.
   - Some commonly used byte stream classes include `InputStream`, `OutputStream`, `FileInputStream`, `FileOutputStream`, `DataInputStream`, `DataOutputStream`, `BufferedInputStream`, and `BufferedOutputStream`.

2. **Character Streams**:
   - Character streams, represented by classes in the `java.io` package, are used for reading and writing text data as streams of characters. They are designed to handle text files and provide support for character encoding and decoding.
   - Character streams are built on top of byte streams and internally convert characters to bytes (using character encoding) when writing to an output stream and convert bytes to characters (using character decoding) when reading from an input stream.
   - Some commonly used character stream classes include `Reader`, `Writer`, `FileReader`, `FileWriter`, `BufferedReader`, `BufferedWriter`, `InputStreamReader`, and `OutputStreamWriter`.

These two types of streams provide different levels of abstraction and functionality for handling input/output operations in Java. Byte streams are suitable for handling binary data, while character streams are designed for handling text data with support for character encoding and decoding. Depending on the requirements of your application, you can choose the appropriate type of stream for performing I/O operations.
### 20. Now that we have a byte stream, why do we need a character stream?
While byte streams are suitable for handling binary data, character streams are specifically designed for handling text data. Here are several reasons why character streams are preferred for working with text data:

1. **Character Encoding**:
   - Character streams automatically handle character encoding and decoding, converting characters to bytes when writing to an output stream and converting bytes to characters when reading from an input stream. This ensures proper handling of character encoding schemes such as UTF-8, UTF-16, and others.

2. **Internationalization (i18n) and Localization (l10n)**:
   - Character streams provide built-in support for internationalization and localization, allowing you to work with text data containing characters from various languages and character sets. They ensure correct interpretation and representation of characters, regardless of the underlying character encoding.

3. **Text Processing**:
   - Character streams offer higher-level abstractions and methods specifically tailored for processing text data. They provide methods for reading and writing lines of text, searching for patterns within text, tokenizing text into words or phrases, and performing various text processing tasks.

4. **Efficiency**:
   - Character streams can be more efficient than byte streams when working with text data, especially when dealing with character encoding and decoding. They minimize the overhead associated with character encoding/decoding operations by performing them internally, resulting in better performance and reduced complexity.

5. **Platform Independence**:
   - Character streams provide platform-independent handling of text data, ensuring consistent behavior across different operating systems and environments. They abstract away the underlying byte-level representation of text data and provide a uniform interface for working with characters.

6. **Ease of Use**:
   - Character streams offer a more intuitive and convenient API for working with text data. They provide higher-level abstractions and methods that simplify common text processing tasks, making it easier to develop and maintain code that deals with text data.

Overall, while byte streams are essential for handling raw binary data, character streams are indispensable for working with text data, providing built-in support for character encoding, internationalization, text processing, efficiency, platform independence, and ease of use. Depending on the nature of your application and the type of data you are working with, you may choose to use either byte streams or character streams, or a combination of both, to achieve your desired functionality.

### 21. What are the difference between BIO, NIO and AIO
BIO (Blocking I/O), NIO (Non-blocking I/O), and AIO (Asynchronous I/O) are different I/O models used in Java for performing input/output operations. Each model has its own characteristics, advantages, and use cases. Here are the main differences between them:

1. **Blocking I/O (BIO)**:
   - In BIO, I/O operations block the calling thread until the operation is completed. When a thread initiates an I/O operation (such as reading from or writing to a file or network socket), it remains blocked until the operation finishes.
   - BIO is synchronous and blocking, meaning that threads are unable to perform other tasks while waiting for I/O operations to complete.
   - While simple and straightforward to use, BIO can lead to scalability issues in applications with a large number of concurrent connections, as each connection requires a dedicated thread, potentially leading to resource exhaustion.

2. **Non-blocking I/O (NIO)**:
   - NIO introduces the concept of non-blocking I/O operations, where a thread can initiate multiple I/O operations and continue executing other tasks while waiting for the operations to complete.
   - NIO uses channels and buffers for performing I/O operations, allowing for more efficient handling of multiple connections with fewer threads.
   - NIO is based on selectors, which are used to monitor multiple channels for events (such as readiness for reading or writing), enabling a single thread to manage multiple I/O operations concurrently.
   - While NIO provides better scalability than BIO by allowing a single thread to handle multiple connections, it can be more complex to use due to the asynchronous and event-driven programming model.

3. **Asynchronous I/O (AIO)**:
   - AIO further extends the non-blocking I/O model by introducing true asynchronous I/O operations, where the calling thread is not required to wait for the completion of I/O operations.
   - In AIO, I/O operations are initiated asynchronously, and the calling thread is notified when the operation completes or encounters an error. This allows the thread to continue executing other tasks in the meantime.
   - AIO is particularly suitable for applications that require high concurrency and responsiveness, such as network servers and real-time systems.
   - AIO is supported in Java starting from Java 7 (with the `java.nio.channels.AsynchronousChannel` and related classes), providing a higher level of abstraction for performing asynchronous I/O operations.

In summary, the main differences between BIO, NIO, and AIO lie in their blocking behavior, concurrency model, and level of asynchrony. BIO blocks the calling thread until I/O operations complete, NIO allows a single thread to handle multiple connections concurrently using non-blocking I/O, and AIO introduces true asynchronous I/O operations, allowing threads to continue executing other tasks while waiting for I/O operations to complete. The choice between these models depends on the requirements of the application, including scalability, responsiveness, and complexity considerations.

### 22. What is serialization?
Serialization is the process of converting an object into a stream of bytes, which can then be stored persistently (such as in a file) or transmitted over a network. This serialized stream of bytes can later be deserialized, or reconstructed, to recreate the original object.

Serialization is commonly used in Java for various purposes, including:

1. **Persistence**: Serialized objects can be stored in files or databases to persistently save their state. This allows objects to be saved between program executions and shared across different instances of the application.

2. **Network Communication**: Serialized objects can be transmitted over a network between different Java applications or components. This is commonly used in distributed systems and client-server architectures.

3. **Caching**: Serialized objects can be cached in memory or on disk to improve performance and reduce resource consumption by avoiding the need to repeatedly recreate objects.

4. **Remote Method Invocation (RMI)**: Serialization is used in Java's RMI framework to pass objects between a client and a server.

To serialize an object in Java, the class of the object must implement the `Serializable` interface, which is a marker interface indicating that the class can be serialized. Additionally, any fields that should not be serialized (such as transient fields or sensitive data) can be marked with the `transient` keyword.

Java provides built-in mechanisms for serialization and deserialization through the `ObjectOutputStream` and `ObjectInputStream` classes, respectively. These classes allow objects to be written to an output stream and read from an input stream, enabling the serialization and deserialization process.

It's important to note that serialization does not serialize static fields, methods, or constructors of a class. Additionally, care should be taken when serializing objects with complex relationships (such as circular references or objects containing references to external resources), as these can lead to issues during serialization and deserialization.

### 23. What is deserialization?
Deserialization is the process of reconstructing an object from its serialized form, which is a stream of bytes. In Java, deserialization is the opposite of serialization: it takes a serialized stream of bytes and recreates the original object.

When an object is serialized, its state is converted into a sequence of bytes that represent the object's fields and their values. This serialized stream of bytes can be stored persistently (such as in a file) or transmitted over a network. Later, when deserialization is performed, the serialized stream of bytes is read and used to recreate the original object, restoring its state and behavior.

Deserialization is commonly used in Java for various purposes, including:

1. **Persistence**: Deserializing objects allows them to be restored from a persistent storage mechanism, such as a file or database, enabling the retrieval of previously saved objects between program executions.

2. **Network Communication**: Deserialization is used to reconstruct objects that have been transmitted over a network between different Java applications or components, allowing objects to be passed between client and server or between different instances of the same application.

3. **Caching**: Deserialization allows cached objects to be reconstructed from their serialized form, enabling them to be retrieved quickly from memory or disk without the need to recreate the objects from scratch.

4. **Remote Method Invocation (RMI)**: Deserialization is used in Java's RMI framework to reconstruct objects that have been passed between a client and a server during remote method invocations.

To perform deserialization in Java, the serialized stream of bytes is read using an `ObjectInputStream`, which reconstructs the object and its state. The class of the object being deserialized must be available in the classpath and must implement the `Serializable` interface to indicate that it can be serialized and deserialized.

It's important to note that deserialization can pose security risks if not performed carefully. Deserializing untrusted or malicious input can lead to security vulnerabilities such as remote code execution or denial-of-service attacks. To mitigate these risks, it's recommended to validate and sanitize deserialized input, use secure coding practices, and consider using alternative serialization mechanisms such as JSON or XML in security-sensitive scenarios. Additionally, objects that are deserialized should be validated and sanitized to ensure their integrity and prevent potential security vulnerabilities.

### 24. What is reflection?
Reflection is a powerful feature in Java that allows a program to examine or introspect its own structure, properties, and behavior at runtime. With reflection, a Java program can inspect classes, interfaces, fields, methods, and constructors, as well as manipulate them dynamically, without knowing their names at compile time.

Reflection enables Java programs to perform the following tasks at runtime:

1. **Inspecting Class Information**: Reflection allows a program to obtain information about classes, such as their names, modifiers, fields, methods, constructors, annotations, and interfaces.

2. **Creating Instances Dynamically**: Reflection enables dynamic instantiation of classes and invocation of constructors, allowing a program to create objects of classes whose names are not known until runtime.

3. **Accessing and Modifying Fields**: Reflection provides mechanisms for accessing and modifying fields (variables) of a class dynamically, even private fields that are not accessible directly.

4. **Invoking Methods Dynamically**: Reflection allows a program to invoke methods of a class dynamically, including public, private, protected, and package-private methods, without knowing their names at compile time.

5. **Working with Annotations**: Reflection enables the examination of annotations attached to classes, fields, methods, and other program elements, allowing a program to process annotations dynamically.

Reflection is widely used in Java frameworks, libraries, and tools for tasks such as dependency injection, serialization/deserialization, dynamic proxy generation, automatic configuration, and runtime analysis. However, reflection should be used judiciously, as it can introduce complexity, decrease performance, and bypass compile-time type checks. Additionally, reflection can lead to security vulnerabilities if not used carefully, as it allows access to private members and execution of arbitrary code.

In summary, reflection is a powerful feature of Java that enables runtime introspection and manipulation of classes, fields, methods, and other program elements, providing flexibility and extensibility to Java programs.
### 25. How much do you know about Lambda expressions?
I know quite a bit about lambda expressions! Lambda expressions were introduced in Java 8 as a way to provide concise syntax for representing anonymous functions or blocks of code. They enable the functional programming paradigm in Java by treating functions as first-class citizens.

Here are some key points about lambda expressions in Java:

1. **Syntax**: Lambda expressions have a compact syntax, typically consisting of parameters, an arrow (`->`), and a body. For example: `(parameters) -> expression` or `(parameters) -> { statements; }`.

2. **Functional Interfaces**: Lambda expressions are used primarily in the context of functional interfaces, which are interfaces with a single abstract method (SAM). Lambda expressions can be used to provide implementations for the abstract method of a functional interface.

3. **Type Inference**: In many cases, the types of parameters in lambda expressions can be inferred by the compiler, reducing the need for explicit type declarations.

4. **Target Typing**: Lambda expressions can be assigned to variables or passed as arguments to methods, and the compiler infers the target type based on the context in which the lambda expression is used.

5. **Variable Capture**: Lambda expressions can capture variables from their surrounding scope, including local variables and instance variables. The captured variables must be effectively final or effectively immutable.

6. **Functional Interfaces in Java API**: Java 8 introduced several new functional interfaces in the `java.util.function` package, such as `Predicate`, `Consumer`, `Function`, and `Supplier`, which are commonly used with lambda expressions.

7. **Method References**: Method references provide a shorthand syntax for creating lambda expressions that invoke existing methods. They allow you to refer to methods by name rather than providing a full lambda expression.

8. **Streams and the Stream API**: Lambda expressions are extensively used in conjunction with the Stream API introduced in Java 8. Streams provide a functional approach to processing collections of data, and lambda expressions are used to specify the processing logic.

Overall, lambda expressions are a powerful feature of Java that enable more concise and expressive code, particularly when working with functional programming concepts such as higher-order functions, function composition, and immutable data. They have greatly enhanced the readability, flexibility, and maintainability of Java codebases.

### 26. What are the common collection frameworks?
In Java, the common collection frameworks refer to the data structures and interfaces provided by the Java Collections Framework (JCF) and the Collections API. These frameworks offer a comprehensive set of classes and interfaces for working with collections of objects, such as lists, sets, maps, queues, and others. Some of the common collection frameworks in Java include:

1. **Interfaces**:
   - **Collection**: The root interface of the Java Collections Framework. It represents a group of objects, known as elements, and provides basic operations for working with collections, such as adding, removing, and querying elements.
   - **List**: An ordered collection that allows duplicate elements. It maintains the insertion order of elements and provides positional access to elements by index.
   - **Set**: A collection that does not allow duplicate elements. It ensures that each element is unique and provides operations for adding, removing, and testing for membership.
   - **Map**: An object that maps keys to values. It represents a collection of key-value pairs and provides methods for accessing, inserting, updating, and removing mappings.
   - **Queue**: A collection designed for holding elements prior to processing. It typically follows the first-in-first-out (FIFO) or priority-based ordering.

2. **Classes**:
   - **ArrayList**: A resizable array implementation of the List interface. It provides fast random access to elements and is suitable for scenarios where frequent access and iteration are common.
   - **LinkedList**: A doubly linked list implementation of the List interface. It provides efficient insertion and deletion operations, making it suitable for scenarios where frequent modification of the list structure is required.
   - **HashSet**: An implementation of the Set interface that uses a hash table for storage. It offers constant-time performance for basic operations such as adding, removing, and testing for membership.
   - **TreeSet**: An implementation of the Set interface based on a red-black tree. It maintains elements in sorted order and provides efficient operations for range queries and ordered traversal.
   - **HashMap**: An implementation of the Map interface that uses a hash table for storage. It provides constant-time performance for basic operations and is suitable for scenarios where fast key-based lookup is required.
   - **TreeMap**: An implementation of the Map interface based on a red-black tree. It maintains mappings in sorted order based on the keys and provides efficient operations for range queries and ordered traversal.

These are some of the common collection frameworks provided by the Java Collections Framework. They offer a wide range of data structures and algorithms for various use cases, making it easy to work with collections of objects in Java applications.

### 27. Do you understand the expansion mechanism of ArrayList?
Yes, I understand the expansion mechanism of ArrayList in Java.

ArrayList is an implementation of the List interface that uses a dynamic array to store elements. When elements are added to an ArrayList, it dynamically grows its internal array to accommodate the new elements. This expansion mechanism ensures that the ArrayList can efficiently store and access elements, even as the size of the list increases.

Here's how the expansion mechanism works:

1. **Initial Capacity**: When an ArrayList is created using the default constructor or the constructor that specifies an initial capacity, it initializes an internal array with the specified capacity. If no initial capacity is provided, it initializes the internal array with a default capacity (usually 10).

2. **Adding Elements**: As elements are added to the ArrayList using the `add()` method, it checks if there is enough space in the internal array to accommodate the new elements. If there is sufficient space, the elements are added to the array at the end.

3. **Expanding the Array**: If the internal array becomes full (i.e., the number of elements equals the capacity of the array), the ArrayList needs to expand its capacity to accommodate more elements. To do this, it creates a new array with a larger capacity (typically, the new capacity is calculated as `(oldCapacity * 3/2) + 1`), copies the existing elements from the old array to the new array, and then adds the new elements.

4. **Copying Elements**: The process of copying elements from the old array to the new array may involve iterating over the existing elements and copying them one by one. This incurs a performance overhead, especially when the ArrayList grows large.

5. **Resizing**: After the expansion, the ArrayList's internal array is resized to the new capacity, and the new elements are added to the end of the array.

6. **Capacity Management**: The ArrayList keeps track of its current size and capacity. The size represents the number of elements currently stored in the ArrayList, while the capacity represents the total number of elements that the internal array can hold without needing to be expanded.

Overall, the expansion mechanism of ArrayList ensures that it can efficiently handle dynamic resizing and accommodate a growing number of elements while minimizing memory overhead and performance impact. However, frequent expansions can still lead to performance degradation, so it's essential to choose an appropriate initial capacity and monitor the growth of ArrayLists in performance-sensitive applications.

### 28. Do you understand fail-fast and fail-safe?
Yes, I understand the concepts of fail-fast and fail-safe in the context of concurrent programming and data structures.

1. **Fail-Fast**:
   - Fail-fast is a design approach where a system or data structure detects and reports errors as soon as they occur, rather than allowing them to propagate or cause further issues.
   - In Java, fail-fast behavior is typically associated with collections such as ArrayList, HashMap, and ConcurrentHashMap. If a structural modification (such as adding or removing elements) is attempted on a collection while it is being iterated over, a ConcurrentModificationException is thrown immediately to indicate that the collection has been modified illegally.
   - Fail-fast behavior is achieved by using iterators that are aware of the collection's internal structure and can detect concurrent modifications during iteration. When a modification is detected, the iterator throws an exception to prevent further iteration and potential data corruption.

2. **Fail-Safe**:
   - Fail-safe is a design approach where a system or data structure gracefully handles errors or concurrent modifications without compromising the correctness or integrity of the operation.
   - In Java, fail-safe behavior is often associated with concurrent collections such as CopyOnWriteArrayList and ConcurrentHashMap. These collections use various mechanisms, such as copying the underlying data structure or using atomic operations, to ensure that modifications do not interfere with ongoing operations.
   - Fail-safe collections typically allow concurrent modifications to the collection while it is being iterated over. However, they do not throw exceptions when modifications occur, and the iterator reflects the state of the collection at the time of its creation.
   - Fail-safe behavior is beneficial in scenarios where concurrent access to data structures is common and where it is more important to maintain system stability and correctness than to detect and report errors immediately.

In summary, fail-fast and fail-safe are two different approaches to handling concurrent modifications in systems and data structures. Fail-fast behavior prioritizes immediate detection and reporting of errors to prevent data corruption, while fail-safe behavior focuses on gracefully handling concurrent modifications to ensure system stability and correctness. The choice between fail-fast and fail-safe depends on the specific requirements and priorities of the application or system.

29. How much do you know about CopyOnWriteArrayList?
30. I know quite a bit about `CopyOnWriteArrayList`! It's a concurrent collection class introduced in Java as part of the java.util.concurrent package. Here are some key points about `CopyOnWriteArrayList`:

1. **Thread-Safe List Implementation**: `CopyOnWriteArrayList` is a thread-safe implementation of the `List` interface. It provides concurrent access to its elements without the need for external synchronization.

2. **Copy-On-Write Semantics**: The name "CopyOnWrite" comes from its behavior: whenever the list is modified (e.g., by adding, setting, or removing elements), a new copy of the underlying array is created, and the modification is applied to the new copy. This ensures that the original array remains unchanged and that any ongoing iterations over the list see a consistent snapshot of the data.

3. **Reads Are Non-Blocking**: Reads (such as iterating over the elements of the list) are non-blocking and do not require synchronization. This makes `CopyOnWriteArrayList` suitable for scenarios where reads vastly outnumber writes.

4. **Writes Are Costly**: Because modifications involve copying the entire underlying array, writes (such as adding, setting, or removing elements) are relatively expensive compared to other list implementations. Therefore, `CopyOnWriteArrayList` is most suitable for scenarios where writes are infrequent compared to reads.

5. **Iterators**: Iterators returned by `CopyOnWriteArrayList` are snapshot iterators, meaning they provide a consistent view of the elements at the time the iterator was created. They do not reflect subsequent modifications made to the list after the iterator was obtained.

6. **Use Cases**: `CopyOnWriteArrayList` is commonly used in scenarios where a list needs to be shared among multiple threads, and reads vastly outnumber writes. It's often used in scenarios such as event notification systems, where the list of event listeners is frequently iterated over but rarely modified.

7. **Memory Overhead**: Because `CopyOnWriteArrayList` creates a new copy of the underlying array on each modification, it can incur significant memory overhead, especially for large lists or frequent modifications. This makes it less suitable for memory-constrained environments.

Overall, `CopyOnWriteArrayList` provides a convenient way to achieve thread-safe access to a list in scenarios where reads are predominant and writes are infrequent. However, its performance characteristics and memory overhead should be carefully considered when choosing it for a particular use case.

30. Can you tell me about the data structure of HashMap?
31. How much do you know about red-black trees? Why not use binary tree/balanced tree?
32. Do you know the put process of HashMap?
33. How to find elements in HashMap?
34. How is the hash function of HashMap designed?
35. Why can the hash function reduce hash collisions?
36. Why is the capacity of HashMap a multiple of 2?
37. If you initialize a HashMap and pass a capacity of 17, what will it do?
38. What are the methods to resolve hash conflicts?
39. When will the HashMap capacity be expanded?
40. Why is the expansion factor 0.75?
40. Do you understand the HashMap expansion mechanism?
41. What main optimizations has jdk1.8 made to HashMap? Why?
42. Is HashMap thread-safe? What are the problems with multi-threading?
43. Is there any way to solve the thread insecurity problem of HashMap?
44. Are the internal nodes of HashMap ordered?
45. How LinkedHashMap achieves ordering?
46. How to achieve ordering in TreeMap?
47. The difference between TreeMap and HashMap
48. Tell me about the underlying implementation of HashSet?
49. What is the difference between parallelism and concurrency?
50. What are processes and threads?
51. How to understand coroutines?
52. What is shared memory of threads?
53. Why is the run() method executed when the start() method is called? Why not call the run() method directly?
54. What are the commonly used scheduling methods for threads?
55. What is the difference between sleep and wait?
56. What is thread context switching?
57. Do you understand daemon threads?
58. What are the communication methods between threads?

59. Is there any solution to the thread safety issue?
60. What is ThreadLocal?
61. How is ThreadLocal implemented?
62. What is a weak reference
63. what is a strong reference?
63. what is a soft reference?
63. what is a virtual reference?
63. What's going on with ThreadLocal memory leaks?
64. Tell me about your understanding of the Java memory model?
65. Why do threads need to use their own memory?
66. Tell me about your understanding of atomicity?
66. Tell me about your understanding of visibility?
66. Tell me about your understanding of order?
67. So what is instruction rearrangement?
68. Do you understand the implementation principle of volatile?
69. Tell me about thread synchronization
70. In addition to atomicity, how to achieve synchronized visibility, orderliness, and reentrancy?
71. What optimizations has synchronized done?
72. What is the difference between synchronized and ReentrantLock?
73.  Tell me about your understanding of AQS?
74. ReentrantLock implementation principle?
75. How does ReentrantLock achieve fair locking?
76. Tell me about your understanding of CAS?
77. What methods does Java have to ensure atomicity? How to ensure that i++ results are correct under multi-threading?
78. How much do you know about the atomic operation class?
79. How to troubleshoot the deadlock problem?
80. Can you tell me about the implementation of ConcurrentHashMap?
81. How does ConcurrentHashMap ensure visibility?
82. Why ConcurrentHashMap is more efficient than Hashtable
83. Do you understand CountDownLatch (countdown counter)?
84. Do you understand CyclicBarrier (synchronization barrier)?
85. What is the difference between CyclicBarrier and CountDownLatch?
86. Do you understand Semaphore?
88. What are the rejection policies of the thread pool?
89. What kind of work queues does the thread pool have?
90. What is the difference between thread pool submission execute and submit?
91. Do you know how to close the thread pool?
92. How should the number of threads in the thread pool be configured?
93. What are the common thread pools?
95. Do you know how to handle thread pool exceptions?
96. Can you tell me how many states the thread pool has?
97. What should you pay attention to when using the thread pool?
99. Talk about the garbage collection mechanism of JVM

