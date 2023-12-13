# Threads and Concurrency in Java

Concurrency in Java involves the execution of multiple threads simultaneously, allowing for the effective utilization of resources and the improvement of program responsiveness. Here, we'll cover the basics of working with threads in Java.

## Understanding Threads

A thread is the smallest unit of execution in a program. In Java, threads are instances of the `Thread` class or objects that implement the `Runnable` interface.

### Creating Threads

#### Extending the `Thread` Class

```java
class MyThread extends Thread {
    public void run() {
        // Code to be executed in the thread
    }
}

// Creating and starting a thread
MyThread myThread = new MyThread();
myThread.start();
```

#### Implementing the `Runnable` Interface

```java
class MyRunnable implements Runnable {
    public void run() {
        // Code to be executed in the thread
    }
}

// Creating and starting a thread
Thread myThread = new Thread(new MyRunnable());
myThread.start();
```

### Thread States

- **New**: The thread is in the new state if it has been created but not yet started.
- **Runnable**: The thread is in the runnable state if it is ready to run.
- **Blocked**: The thread is in the blocked state if it is waiting for a monitor lock.
- **Waiting**: The thread is in the waiting state if it is waiting for another thread to perform a particular action.
- **Timed Waiting**: The thread is in the timed waiting state if it is waiting for another thread to perform a particular action within a stipulated amount of time.
- **Terminated**: The thread is in the terminated state if it has exited.

## Thread Synchronization

Synchronization is important when multiple threads access shared resources to avoid data inconsistencies and conflicts.

### Using the `synchronized` Keyword

```java
class SharedResource {
    private int counter = 0;

    public synchronized void increment() {
        counter++;
    }
}
```

### Using `Lock` Interface

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

class SharedResource {
    private int counter = 0;
    private Lock lock = new ReentrantLock();

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

## Thread Pools

Thread pools manage a pool of worker threads, improving performance and resource management.

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class ThreadPoolExample {
    public static void main(String[] args) {
        ExecutorService executorService = Executors.newFixedThreadPool(5);

        for (int i = 0; i < 10; i++) {
            executorService.execute(new MyRunnable());
        }

        executorService.shutdown();
    }
}
```

## Summary

- Threads in Java are instances of the `Thread` class or objects implementing the `Runnable` interface.
- Thread synchronization is crucial to avoid data inconsistencies when multiple threads access shared resources.
- Thread communication involves methods such as `wait()`, `notify()`, and `notifyAll()`.
- Thread pools manage a pool of worker threads, improving performance and resource management.

For more details on concurrency and threads in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/essential/concurrency/).

