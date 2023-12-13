# Synchronization in Java

In a multi-threaded environment, synchronization is crucial to ensure that threads behave as expected and avoid data inconsistencies. In Java, synchronization is achieved using mechanisms like the `synchronized` keyword, `Lock` interface, and methods such as `wait()`, `notify()`, and `notifyAll()`. Here, we'll cover the fundamentals of synchronization in Java.

## Synchronized Blocks and Methods

### Using the `synchronized` Keyword

The `synchronized` keyword can be applied to methods or blocks of code to ensure that only one thread can execute the synchronized code at a time.

#### Synchronized Method

```java
class SynchronizedExample {
    private int counter = 0;

    public synchronized void increment() {
        counter++;
    }
}
```

#### Synchronized Block

```java
class SynchronizedExample {
    private Object lock = new Object();
    private int counter = 0;

    public void increment() {
        synchronized (lock) {
            counter++;
        }
    }
}
```

### Intrinsic Locks and Monitor

In Java, each object has an intrinsic lock (or monitor) associated with it. The `synchronized` keyword uses this lock to achieve synchronization.

```java
class SynchronizedExample {
    private int counter = 0;

    public void increment() {
        synchronized (this) {
            counter++;
        }
    }
}
```

## Using the `Lock` Interface

The `Lock` interface provides a more flexible and explicit way of achieving synchronization.

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

class SynchronizedExample {
    private Lock lock = new ReentrantLock();
    private int counter = 0;

    public void increment() {
        lock.lock();
        try {
            counter++;
        } finally {
            lock.unlock();
        }
    }
}
```

## Thread Communication

Threads can communicate and coordinate their activities using methods such as `wait()`, `notify()`, and `notifyAll()`.

```java
class SharedResource {
    private boolean isDataReady = false;

    public synchronized void produceData() {
        // Produce data
        isDataReady = true;
        notify(); // Notify waiting threads
    }

    public synchronized void consumeData() throws InterruptedException {
        while (!isDataReady) {
            wait(); // Wait for data to be ready
        }
        // Consume data
    }
}
```

## Deadlock Avoidance

Deadlock is a situation where two or more threads are unable to proceed because each is waiting for the other to release a lock. To avoid deadlock, ensure that threads always acquire locks in the same order.

```java
class DeadlockAvoidanceExample {
    private final Object lock1 = new Object();
    private final Object lock2 = new Object();

    public void method1() {
        synchronized (lock1) {
            // Critical section 1

            synchronized (lock2) {
                // Critical section 2
            }
        }
    }

    public void method2() {
        synchronized (lock1) {
            // Critical section 3

            synchronized (lock2) {
                // Critical section 4
            }
        }
    }
}
```

## Summary

- Synchronization in Java is essential for managing access to shared resources in a multi-threaded environment.
- The `synchronized` keyword, `Lock` interface, and methods like `wait()`, `notify()`, and `notifyAll()` are used for synchronization.
- Be cautious of deadlock situations and ensure locks are acquired in a consistent order.
- Effective synchronization improves program reliability and prevents data inconsistencies.

For more details on synchronization in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/essential/concurrency/).
