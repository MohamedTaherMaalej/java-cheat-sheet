# Socket Programming in Java

Socket programming in Java allows communication between two computers over a network using sockets. Sockets provide a standard mechanism for processes on different devices to communicate.

## Basics of Socket Programming

### Socket Overview

A socket is an endpoint for sending or receiving data across a computer network. In Java, the `Socket` and `ServerSocket` classes are commonly used for socket programming.

#### Client Socket

```java
import java.io.*;
import java.net.*;

public class ClientExample {
    public static void main(String[] args) {
        try (Socket socket = new Socket("hostname", portNumber);
             PrintWriter out = new PrintWriter(socket.getOutputStream(), true);
             BufferedReader in = new BufferedReader(new InputStreamReader(socket.getInputStream()))) {

            // Use the socket for communication
            // ...

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### Server Socket

```java
import java.io.*;
import java.net.*;

public class ServerExample {
    public static void main(String[] args) {
        try (ServerSocket serverSocket = new ServerSocket(portNumber);
             Socket clientSocket = serverSocket.accept();
             PrintWriter out = new PrintWriter(clientSocket.getOutputStream(), true);
             BufferedReader in = new BufferedReader(new InputStreamReader(clientSocket.getInputStream()))) {

            // Use the clientSocket for communication
            // ...

        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Data Exchange

Communication between the client and server involves sending and receiving data streams.

```java
// Client sending data
out.println("Hello, Server!");

// Server receiving data
String clientMessage = in.readLine();
```

## Advanced Socket Programming

### Handling Multiple Clients

To handle multiple clients, use multithreading or asynchronous programming.

```java
// Multithreaded Server
public class MultiThreadedServerExample {
    public static void main(String[] args) {
        // Create a new thread for each client
        // ...
    }
}
```

### Non-blocking Sockets

Java provides `java.nio` for non-blocking I/O, allowing for asynchronous communication.

```java
// Non-blocking Socket Channel
import java.nio.channels.*;
import java.nio.ByteBuffer;

SocketChannel socketChannel = SocketChannel.open();
socketChannel.connect(new InetSocketAddress("hostname", portNumber));

ByteBuffer buffer = ByteBuffer.allocate(1024);
int bytesRead = socketChannel.read(buffer);
```

## Summary

- Socket programming in Java involves communication between client and server using sockets.
- Use `Socket` and `ServerSocket` classes for basic socket communication.
- Exchange data using input and output streams.
- For advanced scenarios, consider multithreading for handling multiple clients or using non-blocking sockets with `java.nio`.

For more details on socket programming in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/networking/sockets/index.html).
