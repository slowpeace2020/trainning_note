# Day5

- [CompletableFuture](#completablefuture)
- [Lock](#lock)
- [parallel vs concurrent](#parallel-vs-concurrent)
- [Lock Usage, Category, Interface](#lock-usage-category-interface)

- [Synchronized Keyword](#synchronized-keyword)
- [Synchronized vs lock](#synchronized-vs-lock)

- [ReentrantLock](#reentrantlock)


### CompletableFuture
Future and CompletionState
[CompletableFuture Usage](https://juejin.cn/post/6844904195162636295)

`CompletableFuture` is a class in Java that represents a future result of an asynchronous computation. It allows you to write asynchronous, non-blocking code in a more fluent and readable manner compared to traditional approaches such as callbacks or using `Future` and `Executor`.

Here's a basic example of how to use `CompletableFuture`:

```java
import java.util.concurrent.CompletableFuture;
import java.util.concurrent.ExecutionException;

public class CompletableFutureExample {
    public static void main(String[] args) throws InterruptedException, ExecutionException {
        // Create a CompletableFuture representing an asynchronous computation
        CompletableFuture<String> future = CompletableFuture.supplyAsync(() -> {
            // Simulate a time-consuming task
            try {
                Thread.sleep(2000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            // Return a result once the task is complete
            return "Hello, CompletableFuture!";
        });

        // Define what to do when the computation is complete
        future.thenAccept(result -> {
            System.out.println("Result: " + result);
        });

        // You can perform other tasks here while waiting for the CompletableFuture to complete

        // Block and wait for the result
        String result = future.get();
        System.out.println("Blocking Result: " + result);

        // Alternatively, you can use join() which throws an unchecked exception
        // String result = future.join();
    }
}
```

In this example:

1. We create a `CompletableFuture` using `CompletableFuture.supplyAsync()` method, which takes a `Supplier` representing the asynchronous computation. In this case, we simulate a time-consuming task by sleeping the thread for 2 seconds.
2. We then attach a callback to the `CompletableFuture` using the `thenAccept()` method. This callback will be invoked when the asynchronous computation is complete, and it will print the result.
3. We can perform other tasks while waiting for the `CompletableFuture` to complete.
4. Finally, we block and wait for the result using the `get()` method. Alternatively, you can use the `join()` method which throws an unchecked exception if the computation fails.

`CompletableFuture` offers many other methods for combining, chaining, and composing asynchronous computations, making it a powerful tool for writing concurrent code in Java.

Here are some of the commonly used methods in the `CompletableFuture` class:

1. `static CompletableFuture<Void> allOf(CompletableFuture<?>... cfs)`: Returns a CompletableFuture that completes when all of the given CompletableFutures complete, with a null result.

2. `static CompletableFuture<Object> anyOf(CompletableFuture<?>... cfs)`: Returns a CompletableFuture that completes when any of the given CompletableFutures complete, with the result of the first completed CompletableFuture.

3. `CompletableFuture<U> thenApply(Function<? super T,? extends U> fn)`: Returns a new CompletableFuture that is completed with the result of applying the given function to the result of this CompletableFuture.

4. `CompletableFuture<Void> thenAccept(Consumer<? super T> action)`: Returns a new CompletableFuture that, when this CompletableFuture completes, executes the given action with the result of this CompletableFuture as the argument.

5. `CompletableFuture<Void> thenRun(Runnable action)`: Returns a new CompletableFuture that, when this CompletableFuture completes, executes the given action.

6. `CompletableFuture<U> thenCompose(Function<? super T,? extends CompletionStage<U>> fn)`: Returns a new CompletableFuture that, when this CompletableFuture completes normally, is executed with this CompletableFuture's result as the argument to the supplied function.

7. `CompletableFuture<T> exceptionally(Function<Throwable,? extends T> fn)`: Returns a new CompletableFuture that is completed normally with the same value as this CompletableFuture if it completed normally, but if this CompletableFuture completed exceptionally, then it is completed with the result of applying the given function to the exception.

8. `boolean complete(T value)`: If not already completed, sets the value returned by `get()` and related methods to the given value.

9. `CompletableFuture<T> completeExceptionally(Throwable ex)`: Completes this CompletableFuture with the given exception.

These are just a few of the methods available in the `CompletableFuture` class for handling and combining the results of asynchronous computations. There are many more methods available for various purposes.

### Lock

A `Lock` in Java is a mechanism used to control access to a shared resource by multiple threads. It provides a way for threads to acquire exclusive access to a resource, execute their critical section of code, and then release the lock so that other threads can access the resource.

The `Lock` interface in Java provides a more flexible and sophisticated approach to thread synchronization compared to the intrinsic locking provided by the `synchronized` keyword. Some key features of `Lock` include:

1. **Explicit control**: Unlike intrinsic locks, which are acquired implicitly when entering a synchronized block or method, a `Lock` must be explicitly acquired and released by calling its `lock()` and `unlock()` methods, respectively.

2. **Non-blocking try-lock**: The `tryLock()` method attempts to acquire the lock without blocking the calling thread. It returns `true` if the lock was acquired successfully and `false` otherwise.

3. **Timeout-based locking**: The `tryLock(long timeout, TimeUnit unit)` method attempts to acquire the lock within the specified time period. If the lock cannot be acquired before the timeout expires, it returns `false`.

4. **Condition support**: The `Lock` interface provides support for condition variables, which allow threads to wait for certain conditions to become true before proceeding.

Using `Lock` provides more control and flexibility over synchronization compared to intrinsic locks. However, it also requires more careful management, as failing to properly release a lock can lead to deadlock or resource contention issues. Therefore, it's essential to always release the lock in a `finally` block to ensure proper cleanup, even in the case of exceptions.

#### parallel vs concurrent
"Parallel" and "concurrent" are terms often used in the context of programming and execution of tasks, especially in the context of multi-threading and multi-processing. While they are related concepts, they have distinct meanings:

1. **Parallel**: Parallelism refers to the simultaneous execution of multiple tasks or processes. In a parallel execution model, tasks are divided into smaller subtasks that can be executed independently and concurrently on multiple processing units, such as multiple CPU cores or distributed computing nodes. The goal of parallelism is to increase throughput and performance by utilizing the available resources efficiently.

2. **Concurrent**: Concurrency, on the other hand, refers to the ability of a system to execute multiple tasks or processes simultaneously, seemingly overlapping in time. Concurrent execution doesn't necessarily imply parallelism; it can be achieved on a single processing unit through techniques like interleaved execution, time slicing, or multitasking. In a concurrent system, tasks may be executed concurrently, but they may not be truly running at the same time due to sharing resources or being scheduled by the operating system.

In summary, parallelism is about executing multiple tasks simultaneously using multiple resources, whereas concurrency is about managing multiple tasks in a way that gives the appearance of simultaneous execution, even if they are actually taking turns to execute on a single resource.

Both parallelism and concurrency are important concepts in modern software development, especially in scenarios where performance, responsiveness, and resource utilization are critical factors. They are used in various domains such as concurrent programming, distributed systems, parallel computing, and more.

#### lock usage,category,interface
In Java, locks are used to control access to shared resources in a multithreaded environment. They ensure that only one thread can access the resource at a time, preventing concurrent access that might lead to data corruption or inconsistency. Locks are classified into several categories based on their behavior and features. Additionally, Java provides various interfaces and classes for implementing locks. Let's explore these aspects:

### Categories of Locks
1. **ReentrantLocks**: These locks allow a thread to acquire the lock multiple times without causing a deadlock. They implement the `Lock` interface and provide more flexibility and features compared to intrinsic locks obtained using the `synchronized` keyword.

2. **ReadWriteLocks**: This type of lock allows multiple threads to read a resource simultaneously but enforces exclusive access for writing. It consists of two locks: one for reading (`ReadLock`) and one for writing (`WriteLock`). This approach can improve concurrency in scenarios where reads are more frequent than writes.

3. **StampedLocks**: Introduced in Java 8, stamped locks provide an optimistic locking mechanism that can be more efficient in read-dominated scenarios. They support both optimistic and pessimistic locking modes.

4. **Fairness Policy**: Some locks support a fairness policy, where threads acquire the lock in the order in which they requested it. This policy helps prevent thread starvation but may impact performance.

### Interfaces and Classes:

1. **Lock Interface**: This interface defines the basic behavior of a lock, including methods like `lock()`, `tryLock()`, `unlock()`, and `newCondition()`. Implementations include `ReentrantLock`, `ReadWriteLock.ReadLock`, `ReadWriteLock.WriteLock`, and `StampedLock`.

2. **ReentrantLock Class**: This class provides a reentrant mutual exclusion lock with the same basic behavior as the implicit monitor lock acquired using the `synchronized` keyword. It supports various features such as fairness policy, interruptible locking, and timed locking.

3. **ReadWriteLock Interface**: This interface represents a pair of associated locks, one for reading and one for writing. It defines methods for acquiring read and write locks (`readLock()` and `writeLock()`).

4. **StampedLock Class**: This class provides a set of non-exclusive read/write locks with optimistic read locking. It supports methods like `tryOptimisticRead()`, `tryReadLock()`, `tryWriteLock()`, and more.

When using locks in Java, it's essential to follow best practices, such as releasing the lock in a finally block and avoiding nested lock acquisitions to prevent deadlocks. Additionally, the choice of lock type depends on factors such as performance requirements, concurrency patterns, and the nature of the shared resource.

### synchronized keyword
The `synchronized` keyword in Java is used to create a critical section, ensuring that only one thread can execute a block of code at a time. It's a built-in mechanism for implementing mutual exclusion and synchronization in multithreaded programs.

#### Usage:
You can use `synchronized` in two ways:

1. **Synchronized Methods**: You can declare a method as synchronized, which means only one thread can execute that method at a time for a given instance of the class.

    ```java
    public synchronized void synchronizedMethod() {
        // Critical section
        // Only one thread can execute this method at a time
    }
    ```

2. **Synchronized Blocks**: You can create a synchronized block by specifying an object as a monitor. Only one thread can execute the code within the synchronized block for a given monitor object at a time.

    ```java
    Object lock = new Object();
    synchronized(lock) {
        // Critical section
        // Only one thread can execute this block at a time
    }
    ```

#### How it Works:
- When a thread enters a synchronized method or block, it attempts to acquire the lock associated with the monitor object. If the lock is available, the thread proceeds to execute the critical section. If the lock is not available (i.e., another thread holds the lock), the thread is blocked until the lock becomes available.
- When the thread exits the synchronized method or block, it releases the lock, allowing other threads to acquire it.

#### Benefits:
- **Thread-Safety**: Using `synchronized` ensures that shared resources are accessed in a thread-safe manner, preventing data corruption or inconsistency.
- **Simplicity**: `synchronized` provides a simple way to synchronize access to critical sections without explicitly managing locks and conditions.

#### Drawbacks:
- **Performance Overhead**: Synchronization adds some overhead due to lock acquisition and release, which can impact performance, especially in highly concurrent applications.
- **Potential Deadlocks**: Improper use of synchronization can lead to deadlocks, where threads wait indefinitely for each other to release locks.
- **Less Flexibility**: `synchronized` provides limited flexibility compared to other synchronization mechanisms such as `Lock` interfaces, which offer features like non-blocking locking, timed locking, and fairness policies.

#### Best Practices:
- Use synchronization judiciously, only where necessary to ensure thread safety.
- Keep synchronized blocks as small as possible to minimize contention and improve performance.
- Always release locks in a `finally` block to ensure they are released even if an exception occurs.
- Consider using higher-level concurrency utilities like `java.util.concurrent` package classes when appropriate, as they offer more flexibility and features compared to `synchronized`.

### Synchronized vs lock
Synchronized and Lock are both mechanisms used to achieve synchronization between threads, but there are some differences between them.

1. **Lock Type**:
   - `synchronized`: A keyword in Java used to synchronize code blocks or methods.
   - `Lock`: An interface in Java with multiple implementations like ReentrantLock and ReadWriteLock.

2. **Usage**:
   - `synchronized`: Implicit lock management by the JVM, no need for manual control.
   - `Lock`: Requires explicit lock acquisition and release using lock() and unlock() methods.

3. **Interruptibility**:
   - `synchronized`: Thread waits indefinitely until it acquires the lock.
   - `Lock`: Provides interruptibility; the waiting thread can be interrupted during lock acquisition.

4. **Fairness**:
   - `synchronized`: Does not guarantee fairness in lock acquisition.
   - `Lock`: Can specify fairness through constructor, allowing the longest-waiting thread to acquire the lock first.

5. **Condition Variables**:
   - `Lock`: Provides a Condition interface for implementing thread wait/notify mechanisms.
   - `synchronized`: Achieves similar functionality using wait(), notify(), and notifyAll() methods of the Object class.

In summary, `synchronized` is simple and easy to use, suitable for most synchronization scenarios. On the other hand, `Lock` provides more flexibility and features, suitable for complex synchronization scenarios. In terms of performance, `Lock` is usually more efficient than `synchronized`, but it requires manual management of lock acquisition and release, which can lead to errors if not handled properly.

### ReentrantLock
fair lock vs. unfair lock
`ReentrantLock` is a class in Java that provides a flexible and powerful alternative to intrinsic locks obtained using the `synchronized` keyword. It implements the `Lock` interface and supports reentrant locking, meaning a thread can acquire the lock multiple times without blocking itself, as long as it releases the lock the same number of times.

#### Fair Lock vs. Unfair Lock:

1. **Fair Lock**:
    - In a fair lock, threads acquire the lock in the order in which they requested it.
    - When multiple threads are waiting to acquire the lock, the lock guarantees that they will be granted access in a fair manner, following a first-come, first-served policy.
    - Fairness ensures that no thread is indefinitely starved of acquiring the lock, preventing potential thread starvation scenarios.
    - Achieving fairness may come at the cost of some performance, as the lock needs to maintain a queue of waiting threads and may introduce additional overhead.

2. **Unfair Lock**:
    - In an unfair lock, threads may acquire the lock out of order.
    - When a lock is released, the lock implementation may allow any waiting thread to acquire the lock, regardless of the order in which they requested it.
    - Unfair locks prioritize speed over fairness, potentially allowing some threads to acquire the lock more frequently than others.
    - While unfair locks may offer better performance in scenarios with low contention, they can lead to thread starvation if some threads are consistently blocked by others.

#### Choosing Between Fair and Unfair Locks:
- **Fair Lock**: Use a fair lock when fairness is essential, and you want to ensure that threads are granted access to the lock in the order they requested it. This is important in scenarios where all threads should be treated equally, or when avoiding thread starvation is critical.
- **Unfair Lock**: Use an unfair lock when performance is more important than fairness, and you are willing to sacrifice fairness for better throughput. Unfair locks may be suitable in scenarios where contention is low, and the overhead of maintaining a fair queue is unnecessary.

In Java, you can create fair and unfair `ReentrantLock` instances by specifying the fairness policy in the constructor:

- `ReentrantLock fairLock = new ReentrantLock(true);` (creates a fair lock)
- `ReentrantLock unfairLock = new ReentrantLock(false);` (creates an unfair lock)

By default, `ReentrantLock` instances are created as unfair locks.




