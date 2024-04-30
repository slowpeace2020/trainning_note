
## java 8 new features

Java 8 introduced many new features and improvements, among the most significant are:

1. **Lambda Expressions**: Lambda expressions are anonymous functions that can be passed as parameters to methods or constructors. They simplify code, making it easier and more elegant to write functional-style code.

2. **Stream API**: The Stream API provides a more concise and efficient way to process collection data. It supports operations similar to SQL queries, such as filtering, mapping, reducing, etc., greatly simplifying the handling and transformation of collection data.

3. **Functional Interfaces**: Functional interfaces are interfaces that contain only one abstract method and can be implemented using lambda expressions. Java 8 provides some built-in functional interfaces, such as Consumer, Predicate, Supplier, etc., to facilitate the use of functional programming.

4. **Method References**: Method references provide a more concise way to represent lambda expressions. They allow direct reference to existing methods without the need to create new lambda expressions for passing to other methods.

5. **Default Methods**: Interfaces can now contain methods with default implementations. This allows interfaces to be extended with new methods without breaking compatibility with classes that already implement the interface.

6. **Optional Class**: The Optional class is a container object that may or may not contain a value. It provides a better way to handle values that may be null, avoiding NullPointerExceptions.

7. **New Date/Time API**: Java 8 introduced a new Date and Time API (java.time package), providing more powerful and flexible date and time handling capabilities, supporting more operations and formatting options.

8. **CompletableFuture**: CompletableFuture is a new Future implementation that supports asynchronous programming. It provides rich methods for handling the results and exceptions of asynchronous operations, as well as for combining and chaining multiple asynchronous operations.

These features make Java 8 a significant milestone, bringing more flexibility, readability, and performance improvements to Java programming.

### what is functional interface
### what is deadlack
### how to detect deadlack
Detecting deadlocks in a Java application typically involves analyzing thread dumps or using tools designed for monitoring and profiling concurrency issues. Here are some common approaches:

1. **Thread Dump Analysis**: Obtain a thread dump of the running Java application. This can be done using tools like `jstack` (comes with the JDK) or by sending a signal to the JVM (e.g., SIGQUIT on Unix-like systems). Analyze the thread dump to identify threads that are in a deadlock state. Deadlocked threads often have a stack trace indicating that they are waiting for a monitor or lock that is held by another thread, which is also waiting for a resource held by the first thread.

2. **Thread Dump from IDE or Profiler**: Many integrated development environments (IDEs) and profiling tools provide features for capturing thread dumps and analyzing them visually. These tools can help identify deadlocks by highlighting threads that are in a blocked state or by showing dependencies between threads.

3. **Monitoring Tools**: There are specialized monitoring and profiling tools designed for detecting concurrency issues, including deadlocks. Some popular tools include Java Mission Control, VisualVM, and YourKit Java Profiler. These tools often provide real-time monitoring of thread activity, including deadlock detection and visualization.

4. **Automated Tools**: There are also automated tools and libraries that can help detect deadlocks in Java applications. For example, the `jdeps` tool included with the JDK can be used to analyze dependencies between classes and detect potential deadlocks caused by circular dependencies. Additionally, third-party libraries like ThreadSafe can perform static analysis of code to identify potential concurrency issues, including deadlocks.

When analyzing a deadlock, it's important to identify the threads involved, the resources they are contending for (e.g., locks, semaphores), and the sequence of events leading up to the deadlock. Once a deadlock is identified, steps can be taken to resolve it, such as redesigning locking strategies, using timeouts, or restructuring the code to avoid circular dependencies.

# what is lock
# what is volatile
In Java, the `volatile` keyword is used to indicate that a variable's value may be changed by multiple threads concurrently. When a variable is declared as `volatile`, it ensures that any thread that reads the variable will see the most recent value written to it by any other thread, rather than a cached or stale value.

Here are some key points about `volatile`:

1. **Visibility**: The primary purpose of `volatile` is to ensure visibility of changes to variables across threads. Without `volatile`, a thread may cache the value of a variable locally and not see changes made to that variable by other threads.

2. **No Atomicity**: Unlike synchronization mechanisms like `synchronized` blocks or the `java.util.concurrent` atomic classes, `volatile` does not provide atomicity for compound actions (such as incrementing a variable). It only ensures visibility of individual read and write operations.

3. **No Mutual Exclusion**: `volatile` does not provide mutual exclusion. It does not prevent multiple threads from accessing or modifying the variable concurrently. It only guarantees that reads and writes of the variable will be seen by all threads in the correct order.

4. **Use Cases**: `volatile` is commonly used for flags or status variables that are accessed by multiple threads but do not require complex atomic operations. Examples include flags to indicate termination of a thread, flags to control loops, or variables used for inter-thread communication.

5. **Performance Impact**: Accessing `volatile` variables can have a performance impact compared to regular variables, as it may require flushing CPU caches and ensuring memory consistency. However, this overhead is typically small compared to other synchronization mechanisms.

In summary, `volatile` is a keyword in Java used to ensure visibility of changes to variables across threads. It is useful in scenarios where variables are accessed by multiple threads and atomicity or mutual exclusion is not required, but visibility is crucial.

## sleep vs wait
在Java中，`wait()` 和 `sleep()` 都是用于线程控制的方法，但它们之间有几个关键的区别：

1. **wait()**：
    - `wait()` 方法是 Object 类的一个实例方法，用于线程间的通信和同步。
    - 调用 `wait()` 方法会使当前线程进入等待状态，并释放对象的锁，直到其他线程调用相同对象的 `notify()` 或 `notifyAll()` 方法唤醒等待的线程，或者直到等待时间超时。
    - `wait()` 方法通常与 `notify()` 或 `notifyAll()` 一起使用，用于实现线程间的协作和同步。

2. **sleep()**：
    - `sleep()` 方法是 Thread 类的一个静态方法，用于暂停当前线程的执行一段指定的时间。
    - 调用 `sleep()` 方法会使当前线程进入阻塞状态，并暂停执行指定的时间，但不会释放对象的锁。
    - `sleep()` 方法通常用于暂停线程的执行，例如在定时任务、动画效果或模拟等场景下使用。

关键区别总结如下：

- `wait()` 是 Object 类的实例方法，用于线程间的通信和同步，会释放对象的锁。
- `sleep()` 是 Thread 类的静态方法，用于暂停当前线程的执行，不会释放对象的锁。
- `wait()` 需要在同步块或同步方法中调用，而 `sleep()` 可以在任何地方调用。
- `wait()` 需要与 `notify()` 或 `notifyAll()` 一起使用，用于实现线程间的协作。
- `sleep()` 可以在不需要线程间通信的情况下使用，例如延迟执行或暂停线程执行。

综上所述，`wait()` 和 `sleep()` 在功能和使用方式上有明显的区别，需要根据具体的需求和场景选择合适的方法。

## garbage collector
垃圾回收器（Garbage Collector）是一种内存管理机制，用于自动检测和释放程序中不再使用的内存（即垃圾），以便回收这些内存供程序重新使用。在Java和其他高级编程语言中，垃圾回收器是一项重要的特性，可以有效地减少内存泄漏和程序错误。

垃圾回收器的主要作用包括：

1. **标记垃圾对象**：垃圾回收器会周期性地检查程序中的对象，并标记那些不再被引用的对象为垃圾对象。

2. **回收垃圾内存**：一旦标记了垃圾对象，垃圾回收器就会将这些对象所占用的内存释放掉，以便其他对象可以使用。

3. **内存压缩**：有些垃圾回收器会进行内存压缩操作，将存活的对象移动到内存的一端，以便回收更多的空间。

4. **提高内存使用效率**：通过回收不再使用的内存，垃圾回收器可以提高程序的内存使用效率，减少内存泄漏和内存溢出的风险。

5. **降低程序员负担**：垃圾回收器可以自动管理内存，减轻了程序员手动释放内存的负担，提高了开发效率和代码质量。

不同的编程语言和运行时环境可能会使用不同类型的垃圾回收器，包括标记-清除（Mark and Sweep）、复制（Copying）、标记-整理（Mark and Compact）等。每种垃圾回收器都有其优缺点，需要根据具体的应用场景和性能需求进行选择和配置。

在Java虚拟机（JVM）中，有几种不同的垃圾回收器（Garbage Collector），每种垃圾回收器都有其自身的特点、优缺点和适用场景。以下是常见的垃圾回收器：

1. **Serial 垃圾回收器**（Serial Garbage Collector）：
    - Serial 垃圾回收器是最简单的一种，也是最古老的一种。它使用单个线程来进行垃圾回收操作，因此被称为串行回收器。
    - 适用于单核CPU或小型应用的环境。
    - 在JDK 8之前，它是新生代的默认垃圾回收器。

2. **Parallel 垃圾回收器**（Parallel Garbage Collector）：
    - Parallel 垃圾回收器也被称为多线程垃圾回收器，它使用多个线程并行进行垃圾回收操作，以提高垃圾回收的速度。
    - 适用于多核CPU和大型应用的环境。
    - 在JDK 8之前，它是老年代的默认垃圾回收器。

3. **CMS 垃圾回收器**（Concurrent Mark-Sweep Garbage Collector）：
    - CMS 垃圾回收器是一种以最短停顿时间为目标的垃圾回收器，它通过多线程并发标记和清除垃圾对象，以减少停顿时间。
    - 适用于对停顿时间有较高要求的应用场景。
    - 由于其清理过程可能会产生碎片，因此不适用于大内存堆。

4. **G1 垃圾回收器**（Garbage First Garbage Collector）：
    - G1 垃圾回收器是一种面向服务端应用的垃圾回收器，它将整个堆划分为多个区域，并使用并发标记-整理算法进行垃圾回收。
    - 适用于大内存堆和对停顿时间和吞吐量都有较高要求的应用场景。
    - 在JDK 9及之后，它是默认的垃圾回收器。

除了以上列出的垃圾回收器之外，还有一些其他的垃圾回收器，如ZGC（Z Garbage Collector）和Shenandoah，它们是JDK 11及之后版本引入的新型垃圾回收器，主要针对大内存堆和低延迟的应用场景。

分代模型（Generational Model）是一种用于内存管理的策略，通常用于垃圾回收器中。在分代模型中，堆内存被分为几个不同的代（Generation），每个代具有不同的生命周期和垃圾回收策略。这种模型基于一种观察：大多数对象很快就会变得不再可用，而一小部分对象会存活更长时间。

通常，分代模型将堆内存分为三个代：

1. **年轻代（Young Generation）**：
    - 年轻代是新创建对象的主要存放区域。
    - 新创建的对象首先被分配到年轻代的Eden空间中。
    - 当Eden空间填满时，触发一次Minor GC（新生代GC），将存活的对象复制到存活区（Survivor Space）中，并清理掉不再使用的对象。

2. **存活区（Survivor Space）**：
    - 存活区有两个，一般称为From空间和To空间。
    - Minor GC发生时，存活区中的对象会被复制到另一个空闲的存活区中，同时清理掉不再使用的对象。
    - 多次Minor GC后仍然存活的对象会被晋升到老年代。

3. **老年代（Old Generation）**：
    - 老年代是存放长时间存活的对象的区域。
    - 老年代的垃圾回收称为Major GC或Full GC，通常会耗费较长时间，因为需要检查整个老年代。
    - Major GC通常会触发一次Young GC，以清理掉年轻代中的对象，并为老年代腾出空间。

分代模型的基本思想是利用新对象通常早死的特性，采用不同的垃圾回收策略来处理不同代的对象，以提高垃圾回收的效率和性能。通过这种方式，大多数对象可以在年轻代中快速被清理掉，只有少量的长期存活对象会进入老年代，从而减少了老年代的垃圾回收频率和成本。

### exception 的种类

### map和flatmap的区别
在函数式编程中，`map` 和 `flatMap` 是两个常用的操作，用于处理集合类型（如列表、数组等）中的元素。它们之间的主要区别在于它们的操作方式和返回值类型。

1. **map**：
    - `map` 方法用于对集合中的每个元素执行指定的操作，并将操作的结果包装成新的集合返回。
    - 对于每个输入元素，`map` 方法都会生成一个对应的输出元素，因此输出集合的大小与输入集合相同。
    - `map` 方法的操作通常是一个函数，它将输入元素映射为输出元素。

2. **flatMap**：
    - `flatMap` 方法与 `map` 类似，但它的操作是一个返回集合的函数，而不是直接返回单个元素。
    - 对于每个输入元素，`flatMap` 方法会生成一个包含零个或多个输出元素的集合，并将所有输出元素合并成一个新的集合返回。
    - 因此，输出集合的大小可能会与输入集合不同。
    - `flatMap` 方法常用于处理嵌套集合（如列表的列表）或执行扁平化操作。

总的来说，`map` 用于将集合中的每个元素转换为另一个元素，而 `flatMap` 用于将集合中的每个元素转换为零个或多个元素，并将这些元素合并为一个新的集合。

## JVM的内存模型
JVM 的内存模型定义了 Java 程序在内存中的组织结构和管理方式。它主要包括以下几个部分：

1. **堆（Heap）**：
    - 堆是 JVM 中最大的一块内存区域，用于存储对象实例和数组。
    - 所有通过 `new` 关键字创建的对象都会被分配到堆中。
    - 堆内存由垃圾回收器（Garbage Collector）负责管理，用于回收不再使用的对象以释放内存空间。

2. **方法区（Method Area）**：
    - 方法区是用于存储类信息、静态变量、常量和编译后的代码等数据的内存区域。
    - 每个加载的类都会在方法区中创建一个 Class 对象，用于描述类的结构和属性。
    - 方法区内存由垃圾回收器管理，但通常不进行对象回收，而是进行类卸载等操作。

3. **栈（Stack）**：
    - 栈是线程私有的内存区域，用于存储线程的局部变量、方法参数、方法调用和返回信息等数据。
    - 每个线程都有自己的栈，栈内存大小在创建线程时确定，并且会随着线程的销毁而释放。
    - 栈内存由 Java 虚拟机自动分配和释放，不存在垃圾回收的概念。

4. **程序计数器（Program Counter）**：
    - 程序计数器是线程私有的内存区域，用于记录当前线程执行的字节码指令地址。
    - 在多线程环境下，每个线程都有自己的程序计数器，用于控制线程的执行流程。

5. **本地方法栈（Native Method Stack）**：
    - 本地方法栈与栈类似，但用于执行本地（Native）方法的内存区域。
    - 本地方法栈的作用和栈类似，但用于执行本地方法的调用和返回。

6. **直接内存（Direct Memory）**：
    - 直接内存不是 Java 虚拟机运行时数据区的一部分，而是通过 `java.nio.ByteBuffer` 类直接分配的内存空间。
    - 直接内存的分配和释放由操作系统管理，通常用于提高 I/O 操作的性能。

这些内存区域共同构成了 JVM 的内存模型，每个区域都有不同的作用和管理方式，用于支持 Java 程序的运行和内存管理。

## JVM是什么
JVM（Java Virtual Machine，Java 虚拟机）是 Java 程序的运行环境，它是一个虚拟的计算机，可以在不同的平台上运行 Java 程序。JVM 将 Java 代码编译成字节码，并提供了运行时环境来执行这些字节码。

以下是 JVM 的主要功能和特点：

1. **字节码执行**：JVM 通过将 Java 源代码编译成字节码（Bytecode），然后在运行时解释或编译执行字节码。这种中间表示的方式使得 Java 程序具有跨平台的特性，可以在任何安装了 JVM 的计算机上运行。

2. **内存管理**：JVM 负责管理 Java 程序的内存，包括分配内存、垃圾回收、内存模型等。它通过堆、栈、方法区等内存区域来存储数据和程序代码，并通过垃圾回收器来回收不再使用的内存。

3. **即时编译（Just-In-Time Compilation，JIT）**：JVM 可以将热点代码（即被频繁执行的代码）编译成本地机器码，以提高程序的执行效率。这种即时编译技术可以将字节码直接编译成本地机器码，而不是解释执行字节码。

4. **类加载机制**：JVM 负责加载、链接和初始化 Java 类。当 Java 程序需要使用某个类时，JVM 会负责从类路径中加载该类的字节码，并进行链接和初始化操作，以准备执行该类的代码。

5. **安全管理**：JVM 提供了安全管理机制，可以对 Java 程序的访问权限进行控制，以保护系统的安全性。

总的来说，JVM 是 Java 程序的运行时环境，它负责解释和执行 Java 字节码，并提供了内存管理、即时编译、类加载、安全管理等功能，使得 Java 程序具有跨平台、高效、安全的特性。