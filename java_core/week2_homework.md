## Homework 4

### Coding:

- [Create a list of students](#create-a-list-of-students)
- [Intermediate operation vs terminal operation](#intermediate-operation-vs-terminal-operation)
- [Thread lifecycle, how does thread transfer from one state to another](#thread-lifecycle-how-does-thread-transfer-from-one-state-to-another)
- [How to create a thread (4 ways, write code)](#how-to-create-a-thread-4-ways-write-code)
- [How does thread pool work](#how-does-thread-pool-work)
- [What is the potential problem for the newCachedThreadPool and newFixedThreadPool and why](#what-is-the-potential-problem-for-the-newcachedthreadpool-and-newfixedthreadpool-and-why)
- [What is Future](#what-is-future)
- [What is CompletableFuture](#what-is-completablefuture)
- [Future vs CompletableFuture](#future-vs-completablefuture)
- [Lock vs synchronized](#lock-vs-synchronized)
- [What is wait(), notify(), notifyAll(), join()](#what-is-wait-notify-notifyall-join)

## Homework 5

### Question List (write necessary code to answer the following questions)

- [What is DeadLock](#what-is-deadlock)
- [How to create deadlock (write the code by using ReentrantLock)](#how-to-create-deadlock-write-the-code-by-using-reentrantlock)
- [How to prevent deadlock and why](#how-to-prevent-deadlock-and-why)
- [CompletableFuture vs Future](#completablefuture-vs-future)
- [CompletableFuture common API](#completablefuture-common-api)
- [Use CompletableFuture to implement the following logic](#use-completablefuture-to-implement-the-following-logic)
- [Write the producer and consumer model (by using synchronized keyword)](#write-the-producer-and-consumer-model-by-using-synchronized-keyword)
- [Synchronized normal method vs synchronized static method](#synchronized-normal-method-vs-synchronized-static-method)

## Homework 4

### Coding:
create a list of students, Student Class has name, age, score three fields.
List<Student> list = new ArrayList<>();

```
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;

class Student {
    private String name;
    private int age;
    private int score;

    public Student(String name, int age, int score) {
        this.name = name;
        this.age = age;
        this.score = score;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public int getScore() {
        return score;
    }
}

```

#### use stream api to find all the students’ name starting with ‘A’
```
List<String> namesStartingWithA = students.stream()
                                          .filter(student-> student.getName().startsWith("A))
                                          .map(Student::getName)
                                          .collect(Collections.toList());

```
#### use stream api to get the sum of all the students score
```
int totalScore = students.stream().mapToInt(Student::getSocre).sum();
```

#### use stream api to find all the students whose sore >= 60
```
List<Student> studentsWithScoreGreaterThan60 = students.stream()
                                                       .filter(student->student.getScore()>=60)
                                                       .collect(Collectors.toList());

```
#### use stream api to retrieve all students name
```
List<String> namesStartingWithA = students.stream()
                                          .map(Student::getName)
                                          .collect(Collections.toList());
```
#### use stream api to count the frequency of each age
```
students.stream()
        .collect(Collectors.groupingBy(Student::getAge,Collectors.counting()))
        .forEach((age,count)->(System.out.println("Age: "+age+", Count: "+count)));

```

### Intermediate operation vs terminal operation
In Java Stream API, operations can be categorized into two types: intermediate operations and terminal operations.

#### Intermediate Operations:
Intermediate operations are operations that are applied on a stream and return a new stream. These operations do not produce a result immediately, but they transform the elements of the stream as they pass through the pipeline. Intermediate operations are lazy, which means they do not perform any processing until a terminal operation is invoked.

Examples of intermediate operations include `filter()`, `map()`, `sorted()`, `distinct()`, `limit()`, and `skip()`. These operations are typically used for data transformation, filtering, and manipulation.

#### Terminal Operations:
Terminal operations are operations that consume a stream and produce a result. When a terminal operation is invoked, the entire stream pipeline is executed, and the result is generated. Once a terminal operation is applied to a stream, the stream is consumed, and it cannot be reused.

Examples of terminal operations include `forEach()`, `collect()`, `reduce()`, `count()`, `anyMatch()`, `allMatch()`, and `noneMatch()`. These operations are used to trigger the processing of the stream and obtain a final result.

Here's a brief comparison between intermediate and terminal operations:

- **Intermediate Operations:**
    - Return a new stream.
    - Lazy evaluation: do not perform any processing until a terminal operation is invoked.
    - Used for data transformation and stream manipulation.

- **Terminal Operations:**
    - Consume a stream and produce a result.
    - Trigger the processing of the stream.
    - Once applied, the stream is consumed and cannot be reused.

In summary, intermediate operations are used to transform and manipulate the elements of a stream, while terminal operations are used to produce a final result from the stream.

### Thread lifecycle, how does thread transfer from one state to another
In the thread lifecycle, a thread transitions from one state to another based on its execution and external conditions. Here's how a thread typically moves through its lifecycle states:

1. **New:** A thread is in the "New" state when it's created but not yet started using the `start()` method.

2. **Runnable:** After calling the `start()` method, the thread becomes "Runnable." It's ready to run but might not be executing immediately because the scheduler hasn't selected it yet.

3. **Blocked:** The thread can transition to the "Blocked" state when it's waiting for a lock to be released by another thread. This happens when it attempts to access a synchronized block or method already locked by another thread.

4. **Waiting:** Threads can enter the "Waiting" state when they explicitly wait for another thread to notify them or when they wait for a specific period of time using methods like `wait()` or `sleep()`. They remain in this state until they're either notified or the timeout expires.

5. **Timed Waiting:** This state is similar to the "Waiting" state, but it's distinguished by a specific timeout period. Threads enter the "Timed Waiting" state when they call methods like `sleep()` or `join()` with a timeout parameter.

6. **Terminated:** Finally, a thread enters the "Terminated" state when it completes its execution or is explicitly terminated by calling the `stop()` method. Once terminated, the thread cannot be restarted.

Each transition in the thread lifecycle occurs based on specific actions taken by the thread or external events, such as acquiring or releasing locks, waiting for notifications, or completing execution. Understanding these state transitions is crucial for effective multithreaded programming.

### Thread State Transitions:
- **New -> Runnable:** Transition occurs when the `start()` method is called, and the thread becomes eligible to run.
- **Runnable -> Running:** Transition occurs when the scheduler selects the thread for execution and begins executing its `run()` method.
- **Running -> Blocked/Waiting:** Transition occurs when the thread is waiting for some condition to be satisfied, such as waiting for I/O or waiting for a lock.
- **Blocked/Waiting -> Runnable:** Transition occurs when the condition the thread was waiting for is satisfied, and it becomes eligible to run again.
- **Running -> Timed Waiting:** Transition occurs when the thread calls methods like `sleep()` or `join()` with a timeout parameter, and the thread waits for the specified time.
- **Timed Waiting -> Runnable:** Transition occurs when the specified time elapses, or the condition the thread was waiting for is satisfied, and the thread becomes eligible to run again.
- **Any State -> Terminated:** Transition occurs when the thread completes its execution or is explicitly terminated.

These transitions are managed by the Java Virtual Machine and the underlying operating system scheduler based on various factors such as thread priorities, scheduling algorithms, and resource availability.

### How to create a thread (4 ways, write code)
In Java, there are several ways to create a thread. Here are four common methods:

1. Extending the Thread class.
2. Implementing the Runnable interface.
3. Using the Callable and Future interfaces.
4. Thread Pool

#### 1. Extending the Thread class:

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class Main {
    public static void main(String[] args) {
        MyThread thread = new MyThread();
        thread.start(); // Start the thread
    }
}
```

#### 2. Implementing the Runnable interface:

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(new MyRunnable());
        thread.start(); // Start the thread
    }
}
```

#### 3. Using the Callable and Future interfaces:

```java
import java.util.concurrent.Callable;
import java.util.concurrent.ExecutionException;
import java.util.concurrent.FutureTask;

class MyCallable implements Callable<String> {
    public String call() {
        return "Thread is running...";
    }
}

public class Main {
    public static void main(String[] args) throws InterruptedException, ExecutionException {
        FutureTask<String> futureTask = new FutureTask<>(new MyCallable());
        Thread thread = new Thread(futureTask);
        thread.start(); // Start the thread

        // Get the result from the FutureTask
        String result = futureTask.get();
        System.out.println(result);
    }
}
```

#### 4. thread pool:

Using a thread pool is a common and efficient way to manage threads in Java, especially in applications that require frequent creation and execution of tasks. Java provides the `ExecutorService` framework to work with thread pools. Here's an example of how to create and use a thread pool:

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class Main {
    public static void main(String[] args) {
        // Create a thread pool with a fixed number of threads
        int numberOfThreads = 5;
        ExecutorService executor = Executors.newFixedThreadPool(numberOfThreads);
        
        // Submit tasks to the thread pool
        for (int i = 0; i < 10; i++) {
            Runnable task = new MyTask(i);
            executor.submit(task);
        }
        
        // Shutdown the thread pool
        executor.shutdown();
    }
}

class MyTask implements Runnable {
    private int taskId;

    public MyTask(int taskId) {
        this.taskId = taskId;
    }

    @Override
    public void run() {
        System.out.println("Task " + taskId + " is running on thread " + Thread.currentThread().getName());
    }
}
```

In this example:

1. We create a `ThreadPoolExecutor` using the `Executors.newFixedThreadPool()` factory method, specifying the desired number of threads in the pool.

2. We submit tasks to the thread pool using the `submit()` method, passing instances of `Runnable` or `Callable` implementations.

3. Each task is executed concurrently by one of the threads in the pool.

4. Finally, we shut down the thread pool using the `shutdown()` method to release the resources associated with it once all tasks have been completed.

Using a thread pool helps manage the lifecycle of threads efficiently, reduces the overhead of thread creation, and ensures optimal resource utilization.

### How does thread pool work
A thread pool is a collection of pre-initialized threads that are ready to perform tasks. Instead of creating a new thread for every task, a thread pool maintains a pool of threads and reuses them to execute multiple tasks over the lifetime of the application. Thread pools offer several advantages, including improved performance, better resource management, and reduced overhead associated with thread creation and destruction.

Here's how a thread pool typically works:

1. **Initialization:** When a thread pool is created, it initializes a fixed number of threads based on the pool size specified during initialization. These threads are placed in a pool and are ready to accept tasks for execution.

2. **Task Submission:** When a task needs to be executed, it is submitted to the thread pool. Tasks can be submitted either synchronously or asynchronously depending on the application's requirements.

3. **Task Queuing:** If all threads in the pool are busy executing tasks when a new task is submitted, the task is placed in a queue known as the task queue. The task queue holds pending tasks until a thread becomes available to execute them.

4. **Task Execution:** When a thread becomes available, it retrieves a task from the task queue and executes it. This process continues until all tasks have been completed.

5. **Thread Reuse:** After a thread completes the execution of a task, it becomes available to execute another task. Instead of being terminated, threads are returned to the pool, allowing them to be reused for subsequent tasks.

6. **Thread Termination:** Thread pools typically have a maximum thread idle time or a maximum thread count limit. If a thread remains idle for a specified period or the number of threads exceeds the maximum limit, excess threads may be terminated to free up system resources.

By using a thread pool, applications can manage the concurrent execution of tasks efficiently, minimize thread creation overhead, and optimize resource utilization. Thread pools are commonly used in multithreaded applications such as web servers, database servers, and concurrent processing systems.

### What is the potential problem for the newCachedThreadPool and newFixedThreadPool and why
The `newCachedThreadPool` and `newFixedThreadPool` are two types of thread pools provided by the `Executors` class in Java. While they offer convenience and ease of use, they also come with potential problems, each associated with their specific characteristics:

#### Potential Problems with `newCachedThreadPool`:

1. **Unbounded Thread Creation:** The `newCachedThreadPool` creates threads on-demand to handle incoming tasks. While this allows for efficient resource utilization when the workload is light, it can lead to the creation of a large number of threads under heavy load. Since there is no limit to the number of threads that can be created, this may consume excessive system resources and potentially lead to resource exhaustion.

2. **Memory Overhead:** Each thread created by the `newCachedThreadPool` consumes memory resources, including stack space and other associated data structures. In scenarios where a large number of threads are created, this can lead to increased memory consumption, potentially causing memory pressure and impacting overall system performance.

3. **Uncontrolled Backlog:** When tasks are submitted to the `newCachedThreadPool` and all existing threads are busy, new threads are created to handle incoming tasks. If the rate at which tasks are submitted exceeds the rate at which threads can process them, a backlog of pending tasks may accumulate in the task queue. This backlog can grow uncontrollably, leading to increased latency and potential resource contention.

#### Potential Problems with `newFixedThreadPool`:

1. **Fixed Thread Count:** Unlike the `newCachedThreadPool`, which dynamically adjusts the number of threads based on workload, the `newFixedThreadPool` maintains a fixed number of threads throughout its lifetime. While this provides control over resource usage, it can lead to suboptimal performance in scenarios where the workload varies significantly over time.

2. **Resource Saturation:** Since the `newFixedThreadPool` maintains a fixed number of threads, there is a risk of resource saturation under heavy load. If the number of threads is insufficient to handle the incoming workload, tasks may be queued indefinitely, leading to increased latency and potential resource contention.

3. **Underutilization of Resources:** In scenarios where the workload is light, the fixed number of threads allocated by the `newFixedThreadPool` may result in underutilization of available system resources. Idle threads consume memory and other resources without actively contributing to task execution, potentially impacting overall system efficiency.

In summary, while the `newCachedThreadPool` and `newFixedThreadPool` offer convenience and simplicity, they also come with potential drawbacks related to resource management, scalability, and performance optimization. It's essential to carefully consider these factors and choose the appropriate thread pool implementation based on the specific requirements and characteristics of the application.

### What is Future
In Java, `Future` is an interface that represents the result of an asynchronous computation. It provides a way to retrieve the result of a computation that may not yet be available. `Future` allows you to submit a task for execution asynchronously and obtain a handle (`Future` object) to retrieve the result of the task once it's completed.

The `Future` interface defines methods to check if the computation is complete, to wait for its completion, and to retrieve the result of the computation when it becomes available. It also allows for cancellation of the associated task.

Here are some key points about `Future`:

1. **Asynchronous Computation:** `Future` is used to represent the result of an asynchronous computation, which may be running concurrently with other parts of the program.

2. **Non-blocking:** While the computation represented by a `Future` is in progress, the calling thread can continue its execution without blocking.

3. **Result Retrieval:** The `get()` method of the `Future` interface is used to retrieve the result of the computation. If the computation is not yet complete, the `get()` method will block until the result becomes available.

4. **Completion Check:** The `isDone()` method of the `Future` interface can be used to check if the computation associated with the `Future` has completed.

5. **Cancellation:** The `cancel()` method of the `Future` interface can be used to cancel the associated computation. Once a `Future` is cancelled, attempts to retrieve its result will result in cancellation exceptions.

`Future` is commonly used in conjunction with the `ExecutorService` framework to perform asynchronous computations and manage concurrent tasks. It provides a flexible and efficient way to work with asynchronous operations and handle their results in Java applications.

### What is CompletableFuture
`CompletableFuture` is a class introduced in Java 8 that represents a future result of an asynchronous computation. It provides a powerful way to work with asynchronous programming, allowing developers to compose complex asynchronous operations easily.

Here are some key features and functionalities of `CompletableFuture`:

1. **Asynchronous Computation:** Like the `Future` interface, `CompletableFuture` represents the result of an asynchronous computation. However, it provides more flexibility and control over the asynchronous execution flow.

2. **Completion Actions:** `CompletableFuture` allows you to define completion actions that will be executed when the computation is completed. You can specify these actions using methods such as `thenApply`, `thenAccept`, and `thenRun`.

3. **Combining and Chaining:** `CompletableFuture` supports fluent API methods for combining multiple asynchronous computations and chaining them together. This enables developers to express complex asynchronous workflows in a concise and readable manner.

4. **Exception Handling:** `CompletableFuture` provides methods for handling exceptions that occur during the asynchronous computation. You can use methods like `exceptionally` and `handle` to specify how to handle exceptions when they occur.

5. **Asynchronous Execution:** `CompletableFuture` supports asynchronous execution by allowing computations to be executed in a separate thread or executor. You can specify the executor to use for asynchronous tasks when creating `CompletableFuture` instances.

6. **Timeouts and Cancellation:** `CompletableFuture` supports setting timeouts for asynchronous computations and cancelling them if they take too long to complete. This helps prevent blocking and resource wastage in situations where timely completion is crucial.

7. **Integration with Streams:** `CompletableFuture` can be integrated with Java Streams API, allowing asynchronous computations to be seamlessly combined with stream processing operations.

Overall, `CompletableFuture` provides a versatile and efficient way to work with asynchronous computations in Java, offering powerful features for composing, chaining, and handling asynchronous tasks. It has become an essential component in modern Java applications, especially in scenarios involving concurrent programming and reactive systems.

### Future vs CompletableFuture
`Future` and `CompletableFuture` are both used to represent the result of asynchronous computations in Java, but they differ in their capabilities and features. Here's a comparison between the two:

#### Future:

1. **Limited Functionality:** The `Future` interface, introduced in Java 5, provides basic support for asynchronous computation result retrieval.

2. **Blocking Get:** The `get()` method of `Future` blocks until the result of the computation is available. If the computation is not yet complete, the calling thread will be blocked until the result is ready.

3. **No Exception Handling:** `Future` does not provide built-in support for handling exceptions that occur during computation. If an exception occurs, it must be handled explicitly by the calling code.

4. **No Completion Actions:** `Future` does not support attaching completion actions to be executed when the computation is complete.

#### CompletableFuture:

1. **Enhanced Functionality:** `CompletableFuture`, introduced in Java 8, extends the capabilities of `Future` by providing a more comprehensive set of features for asynchronous programming.

2. **Non-blocking Get:** Like `Future`, `CompletableFuture` offers a `get()` method to retrieve the result of the computation. However, it also provides non-blocking methods like `join()` to obtain the result without blocking.

3. **Exception Handling:** `CompletableFuture` offers built-in support for exception handling through methods like `exceptionally` and `handle`. Developers can specify how to handle exceptions that occur during computation.

4. **Completion Actions:** Unlike `Future`, `CompletableFuture` allows you to attach completion actions using methods like `thenApply`, `thenAccept`, and `thenRun`. These actions are executed asynchronously when the computation is complete, enabling fluent chaining of asynchronous operations.

5. **Combining and Chaining:** `CompletableFuture` supports combining and chaining multiple asynchronous computations using methods like `thenCompose`, `thenCombine`, and `thenAcceptBoth`.

6. **Timeouts and Cancellation:** `CompletableFuture` provides methods for setting timeouts on asynchronous computations and cancelling them if they take too long to complete.

7. **Stream Integration:** `CompletableFuture` integrates seamlessly with Java Streams API, allowing asynchronous computations to be combined with stream processing operations.

In summary, while both `Future` and `CompletableFuture` serve similar purposes, `CompletableFuture` offers more advanced features and capabilities for asynchronous programming, making it a preferred choice for modern Java applications. It provides enhanced control, exception handling, and composability, enabling developers to express complex asynchronous workflows more concisely and effectively.

### Lock vs synchronized
Both `Lock` and `synchronized` are mechanisms in Java used for thread synchronization to control access to shared resources in a multi-threaded environment. However, they have some differences in their usage and behavior:

#### Lock:

1. **Interface:** `Lock` is an interface defined in the `java.util.concurrent.locks` package.

2. **Explicit Control:** With `Lock`, you have more explicit control over locking and unlocking mechanisms. You acquire a lock explicitly using the `lock()` method and release it using the `unlock()` method.

3. **Reentrant:** `Lock` implementations, such as `ReentrantLock`, support reentrant locking, which means a thread can acquire the same lock multiple times without causing a deadlock.

4. **Condition Support:** `Lock` provides additional features like support for conditions (`Condition` interface) which allow threads to wait for certain conditions to be met before proceeding.

5. **Try-Lock:** `Lock` provides a `tryLock()` method that allows a thread to attempt to acquire the lock without blocking. This can be useful for avoiding potential deadlocks or excessive waiting.

#### synchronized:

1. **Keyword:** `synchronized` is a keyword in Java used to create synchronized blocks or methods.

2. **Implicit Lock:** With `synchronized`, the locking and unlocking mechanisms are implicit. When a thread enters a synchronized block or method, it automatically acquires the lock associated with the object or class and releases it when the block or method exits.

3. **Reentrant:** `synchronized` methods and blocks are inherently reentrant, meaning a thread can acquire the same lock multiple times without deadlock.

4. **No Condition Support:** Unlike `Lock`, `synchronized` does not support conditions directly. It relies on methods like `wait()` and `notify()` for inter-thread communication and synchronization.

5. **Block-Level Synchronization:** With `synchronized`, you can synchronize entire methods or blocks of code, but you cannot synchronize on arbitrary conditions or provide finer-grained control over locking.

In summary, `Lock` provides more flexibility and control over locking mechanisms, supports additional features like conditions, and allows for non-blocking lock acquisition. On the other hand, `synchronized` provides simpler and more convenient synchronization at the method or block level but lacks some of the advanced features provided by `Lock`. The choice between them depends on the specific requirements and complexity of the synchronization scenario in your application.

### What is wait(), notify(), notifyAll(), join()
1. **wait():**
    - `wait()` is a method defined in the `Object` class in Java.
    - It is used for inter-thread communication and synchronization.
    - When a thread calls `wait()` on an object, it releases the lock on that object and waits until another thread notifies it using the `notify()` or `notifyAll()` method.
    - `wait()` must be called from within a synchronized block or method.

2. **notify():**
    - `notify()` is a method defined in the `Object` class in Java.
    - It is used to wake up a single thread that is waiting on the object's monitor.
    - When a thread calls `notify()` on an object, it wakes up one of the threads that are waiting on that object's monitor.
    - The choice of which thread to wake up is arbitrary and depends on the JVM implementation.

3. **notifyAll():**
    - `notifyAll()` is a method defined in the `Object` class in Java.
    - It is used to wake up all threads that are waiting on the object's monitor.
    - When a thread calls `notifyAll()` on an object, all threads that are waiting on that object's monitor are notified and can attempt to acquire the lock.

4. **join():**
    - `join()` is a method defined in the `Thread` class in Java.
    - It is used to wait for a thread to complete its execution before continuing with the current thread's execution.
    - When a thread calls `join()` on another thread, it waits until the other thread completes execution or the specified timeout period elapses.
    - `join()` is often used to coordinate the execution of multiple threads, allowing one thread to wait for the completion of another thread's task before proceeding.

These methods are fundamental for implementing synchronization, communication, and coordination between threads in Java programs. They enable developers to control the execution flow and ensure proper synchronization and cooperation between concurrent threads.

## Homework 5
Question List (write necessary code to answer the following questions)

### What is DeadLock
A deadlock in Java occurs when two or more threads are blocked indefinitely, each waiting for the other to release a resource that they need in order to proceed. As a result, the threads end up waiting indefinitely, and the program becomes unresponsive. Deadlocks are a common problem in multi-threaded programming and can be difficult to detect and resolve.

Deadlocks typically occur when the following conditions are met:

1. **Mutual Exclusion:** Each thread holds a resource (such as a lock) that is required by another thread in order to proceed. These resources cannot be shared simultaneously between threads.

2. **Hold and Wait:** Each thread holds at least one resource and is waiting to acquire additional resources that are held by other threads.

3. **No Preemption:** Resources cannot be forcibly taken away from a thread; they must be released voluntarily by the thread holding them.

4. **Circular Wait:** There exists a circular chain of two or more threads, where each thread is waiting for a resource that is held by the next thread in the chain.

When these conditions are met, a deadlock can occur because none of the threads can make progress—they are all waiting for resources that are held by other threads, creating a circular dependency.

Detecting and resolving deadlocks can be challenging, as they often involve complex interactions between multiple threads and resources. Common techniques for preventing deadlocks include:

- Avoiding circular dependencies by acquiring resources in a consistent order.
- Using timeouts or other mechanisms to break deadlock situations.
- Minimizing the use of locks and synchronization where possible.
- Using higher-level concurrency constructs that handle resource management automatically, such as `java.util.concurrent` classes.

Overall, deadlocks are a serious issue in multi-threaded programming and require careful design and attention to avoid.

### How to create deadlock (write the code by using ReentrantLock)
Creating a deadlock using `ReentrantLock` involves acquiring multiple locks in different threads in such a way that they depend on each other for release. Here's an example of how to create a deadlock using `ReentrantLock`:

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

public class DeadlockExample {
    private static final Lock lock1 = new ReentrantLock();
    private static final Lock lock2 = new ReentrantLock();

    public static void main(String[] args) {
        Thread thread1 = new Thread(() -> {
            lock1.lock();
            System.out.println(Thread.currentThread().getName() + " acquired lock1");
            try {
                // Introduce some delay to ensure both threads acquire their locks
                Thread.sleep(100);
                lock2.lock();
                System.out.println(Thread.currentThread().getName() + " acquired lock2");
                // Critical section
                System.out.println(Thread.currentThread().getName() + " performing some operation");
            } catch (InterruptedException e) {
                e.printStackTrace();
            } finally {
                lock2.unlock();
                System.out.println(Thread.currentThread().getName() + " released lock2");
                lock1.unlock();
                System.out.println(Thread.currentThread().getName() + " released lock1");
            }
        });

        Thread thread2 = new Thread(() -> {
            lock2.lock();
            System.out.println(Thread.currentThread().getName() + " acquired lock2");
            try {
                // Introduce some delay to ensure both threads acquire their locks
                Thread.sleep(100);
                lock1.lock();
                System.out.println(Thread.currentThread().getName() + " acquired lock1");
                // Critical section
                System.out.println(Thread.currentThread().getName() + " performing some operation");
            } catch (InterruptedException e) {
                e.printStackTrace();
            } finally {
                lock1.unlock();
                System.out.println(Thread.currentThread().getName() + " released lock1");
                lock2.unlock();
                System.out.println(Thread.currentThread().getName() + " released lock2");
            }
        });

        thread1.start();
        thread2.start();
    }
}
```

In this example, `thread1` acquires `lock1` and then tries to acquire `lock2`, while `thread2` acquires `lock2` and then tries to acquire `lock1`. This creates a circular dependency where each thread is waiting for the lock held by the other thread, resulting in a deadlock situation.

### How to prevent deadlock and why
Preventing deadlocks involves designing your concurrent code in such a way that the conditions necessary for a deadlock to occur are avoided. Here are some strategies for preventing deadlocks:

1. **Lock Ordering:**
    - Always acquire locks in a fixed and predefined order. By establishing a consistent lock acquisition order across all threads, you can prevent circular dependencies and reduce the likelihood of deadlocks.
    - For example, if Thread A always acquires Lock 1 before Lock 2, and Thread B always acquires Lock 2 before Lock 1, the potential for a deadlock is eliminated.

2. **Lock Timeout:**
    - Use lock timeouts to avoid indefinite blocking. Instead of waiting indefinitely for a lock to become available, threads can wait for a specified period of time before timing out.
    - If a lock cannot be acquired within the timeout period, the thread can release any acquired locks and retry later, preventing potential deadlocks.

3. **Lock Hierarchy:**
    - Establish a hierarchy of locks and ensure that locks are acquired in a hierarchical order. This helps prevent nested locks from being acquired out of order, which can lead to deadlocks.
    - For example, if Lock B is always acquired within the scope of Lock A, threads should acquire Lock A before attempting to acquire Lock B.

4. **Avoid Nested Locks:**
    - Minimize the use of nested locks, where one lock is acquired while holding another lock. Nested locks increase the complexity of lock acquisition and make it more difficult to reason about potential deadlocks.
    - Instead, design your code to use coarse-grained locks that cover larger sections of code, reducing the need for nested locking.

5. **Deadlock Detection and Recovery:**
    - Implement deadlock detection mechanisms to identify and recover from deadlock situations when they occur. This can involve periodically checking for deadlock conditions and taking appropriate action, such as releasing locks and retrying.

Preventing deadlocks is essential for maintaining the stability and reliability of concurrent applications. By carefully designing your code to follow these principles, you can minimize the risk of deadlocks and ensure smooth execution of concurrent operations.

### CompletableFuture vs Future
`CompletableFuture` and `Future` are both interfaces in Java that represent asynchronous computations and provide a way to retrieve the result of an asynchronous operation. However, they have some key differences:

1. **CompletableFuture**:
    - Introduced in Java 8, `CompletableFuture` extends the `Future` interface and provides a more flexible and powerful way to work with asynchronous computations.
    - `CompletableFuture` supports chaining of multiple asynchronous operations using fluent API methods like `thenApply`, `thenAccept`, `thenCompose`, etc.
    - It allows for combining multiple `CompletableFuture` instances using methods like `thenCombine`, `thenCombineAsync`, `thenAcceptBoth`, etc.
    - `CompletableFuture` provides support for error handling using methods like `exceptionally`, `handle`, `exceptionallyCompose`, etc.
    - It supports asynchronous execution using `Executor` services and allows specifying a custom executor for each asynchronous operation.

2. **Future**:
    - `Future` represents the result of an asynchronous computation, but it is a more limited interface compared to `CompletableFuture`.
    - `Future` provides methods to check if the computation is complete (`isDone`) and to retrieve the result (`get`) of the computation.
    - It does not provide built-in support for chaining asynchronous operations or combining multiple asynchronous computations.
    - `Future` does not support explicit error handling or composition of asynchronous operations.

In summary, `CompletableFuture` offers more features and flexibility for working with asynchronous computations compared to `Future`. It provides a richer API for composing, combining, and handling asynchronous operations, making it more suitable for complex asynchronous workflows and concurrent programming tasks.

### CompletableFuture common API
The `CompletableFuture` class in Java provides several common APIs for working with asynchronous computations. Some of the common methods and APIs provided by `CompletableFuture` include:

1. **Creation Methods**:
    - `CompletableFuture.runAsync(Runnable runnable)`: Executes the given `Runnable` asynchronously and returns a `CompletableFuture<Void>` that is completed when the `Runnable` completes.
    - `CompletableFuture.supplyAsync(Supplier<U> supplier)`: Executes the given `Supplier` asynchronously and returns a `CompletableFuture<U>` that is completed with the result of the `Supplier`.

2. **Completion Stage Methods**:
    - `thenApply(Function<? super T,? extends U> fn)`: Applies the given function to the result of the current `CompletableFuture` and returns a new `CompletableFuture` with the result of the function applied.
    - `thenAccept(Consumer<? super T> action)`: Performs the given action with the result of the current `CompletableFuture` and returns a new `CompletableFuture<Void>` that is completed when the action completes.
    - `thenCombine(CompletionStage<? extends U> other, BiFunction<? super T,? super U,? extends V> fn)`: Combines the results of the current `CompletableFuture` and another `CompletionStage` using the given function.

3. **Error Handling**:
    - `exceptionally(Function<Throwable,? extends T> fn)`: Returns a new `CompletableFuture` that is completed with the result of the given function if the current `CompletableFuture` completes exceptionally.
    - `handle(BiFunction<? super T, Throwable, ? extends U> fn)`: Combines the result of the current `CompletableFuture` and any exception that occurred during its computation using the given function.

4. **Combining and Chaining**:
    - `thenCompose(Function<? super T, ? extends CompletionStage<U>> fn)`: Applies the given function to the result of the current `CompletableFuture` and returns a new `CompletableFuture` that represents the result of the function applied.
    - `thenCombineAsync(CompletionStage<? extends U> other, BiFunction<? super T,? super U,? extends V> fn)`: Combines the results of the current `CompletableFuture` and another `CompletionStage` asynchronously using the given function.

5. **Waiting for Completion**:
    - `join()`: Waits for the completion of the `CompletableFuture` and returns its result, throwing an unchecked exception if the computation completed exceptionally.

These are some of the common APIs provided by `CompletableFuture` for asynchronous programming in Java. They allow for composing, combining, and handling asynchronous computations in a flexible and expressive manner.\
[CompletableFuture example](https://modouxiansheng.top/2019/08/13/%E4%B8%8D%E5%AD%A6%E6%97%A0%E6%95%B0-Java8-%E5%BC%82%E6%AD%A5%E7%BC%96%E7%A8%8B-2019/)

### Use CompletableFuture to implement the following logic
initial Num = 1 <br>
async: num += 10 <br>
sync: num *=4  <br>
async: consume result and print <br>
exception: if exception, handle it <br>


```java
import java.util.concurrent.CompletableFuture;
import java.util.concurrent.ExecutionException;

public class CompletableFutureExample {
    public static void main(String[] args) {
        int initialNum = 1;

        CompletableFuture<Integer> asyncAddition = CompletableFuture.supplyAsync(() -> {
            System.out.println("Async: Adding 10 to initialNum...");
            return initialNum + 10;
        });

        CompletableFuture<Integer> synchronousMultiplication = asyncAddition.thenApply(result -> {
            System.out.println("Sync: Multiplying result by 4...");
            return result * 4;
        });

        CompletableFuture<Void> asyncConsumption = synchronousMultiplication.thenAcceptAsync(result -> {
            System.out.println("Async: Consuming result: " + result);
        });

        CompletableFuture<Void> exceptionHandling = asyncConsumption.exceptionally(ex -> {
            System.out.println("Exception occurred: " + ex.getMessage());
            return null; // Handle exception and return null to continue processing
        });

        // Wait for completion
        try {
            exceptionHandling.join();
        } catch (Exception e) {
            System.err.println("Error occurred while processing CompletableFuture: " + e.getMessage());
        }
    }
}
```

This code creates a `CompletableFuture` chain to perform the specified operations:

1. Asynchronously adds 10 to the initial number.
2. Synchronously multiplies the result by 4.
3. Asynchronously consumes the final result and prints it.
4. Handles any exceptions that may occur during the asynchronous processing.

Note: In this example, the exception handling is done using the `exceptionally` method, which allows you to handle exceptions that occur during the execution of the `CompletableFuture` chain. If an exception occurs at any stage of the chain, the `exceptionally` block will handle it and continue processing.


### Write the producer and consumer model (by using synchronized keyword)
Here's an example of the producer-consumer model implemented using the `synchronized` keyword in Java:

```java
import java.util.LinkedList;

class SharedResource {
    private final int capacity;
    private final LinkedList<Integer> buffer;

    SharedResource(int capacity) {
        this.capacity = capacity;
        this.buffer = new LinkedList<>();
    }

    synchronized void produce(int value) throws InterruptedException {
        while (buffer.size() == capacity) {
            wait(); // Wait if buffer is full
        }
        buffer.add(value);
        System.out.println("Produced: " + value);
        notifyAll(); // Notify consumers that new data is available
    }

    synchronized int consume() throws InterruptedException {
        while (buffer.isEmpty()) {
            wait(); // Wait if buffer is empty
        }
        int value = buffer.removeFirst();
        System.out.println("Consumed: " + value);
        notifyAll(); // Notify producers that space is available in buffer
        return value;
    }
}

class Producer extends Thread {
    private final SharedResource sharedResource;

    Producer(SharedResource sharedResource) {
        this.sharedResource = sharedResource;
    }

    @Override
    public void run() {
        try {
            for (int i = 1; i <= 5; i++) {
                sharedResource.produce(i);
                Thread.sleep(1000); // Simulate some processing time
            }
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}

class Consumer extends Thread {
    private final SharedResource sharedResource;

    Consumer(SharedResource sharedResource) {
        this.sharedResource = sharedResource;
    }

    @Override
    public void run() {
        try {
            for (int i = 0; i < 5; i++) {
                sharedResource.consume();
                Thread.sleep(2000); // Simulate some processing time
            }
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
    }
}

public class ProducerConsumerExample {
    public static void main(String[] args) {
        SharedResource sharedResource = new SharedResource(3); // Buffer capacity

        Producer producer = new Producer(sharedResource);
        Consumer consumer = new Consumer(sharedResource);

        producer.start();
        consumer.start();
    }
}
```

In this example:
- The `SharedResource` class represents the shared buffer between the producer and consumer threads. It has synchronized methods `produce` and `consume` to add and remove elements from the buffer.
- The `Producer` and `Consumer` classes extend `Thread` and override the `run` method to simulate producing and consuming items.
- In the `main` method, we create instances of the `Producer` and `Consumer` classes and start them.

### Synchronized normal method vs synchronized static method
In Java, both synchronized normal methods and synchronized static methods are used to achieve thread safety by preventing multiple threads from accessing critical sections of code concurrently. However, there are some differences between them:

1. **Lock Acquisition**:
    - Synchronized normal methods: When a synchronized instance method is invoked, the lock associated with the object instance (`this`) is acquired. Therefore, if multiple threads are invoking synchronized instance methods on different object instances, they can execute concurrently because they lock on different objects.
    - Synchronized static methods: When a synchronized static method is invoked, the lock acquired is on the class object representing the class itself (i.e., `ClassName.class`). Therefore, only one thread can execute any synchronized static method of the class at a time, regardless of which instance or object invoked the method.

2. **Instance vs Class Level Lock**:
    - Synchronized normal methods: Use instance-level lock (lock on `this` object).
    - Synchronized static methods: Use class-level lock (lock on `Class.class` object).

3. **Visibility and Inheritance**:
    - Synchronized normal methods: Each object instance has its own monitor lock, so synchronization is inherited by subclasses.
    - Synchronized static methods: The lock is acquired on the class object, which is shared among all instances and subclasses. Therefore, synchronization is also inherited by subclasses.

4. **Accessing Non-static Members**:
    - Synchronized normal methods: Can access both static and non-static members of the class.
    - Synchronized static methods: Cannot directly access non-static (instance) members of the class because they operate at the class level.

Here's an example illustrating the use of synchronized normal method and synchronized static method:

```java
public class SynchronizedExample {

    private static int staticCounter = 0;
    private int instanceCounter = 0;

    // Synchronized normal method (instance-level lock)
    public synchronized void incrementInstanceCounter() {
        instanceCounter++;
    }

    // Synchronized static method (class-level lock)
    public static synchronized void incrementStaticCounter() {
        staticCounter++;
    }
}
```

In this example, `incrementInstanceCounter` is a synchronized normal method, and `incrementStaticCounter` is a synchronized static method. Each method ensures that only one thread can execute it at a time based on the type of lock it acquires.

