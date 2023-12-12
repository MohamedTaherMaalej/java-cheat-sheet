# Reading and Writing Files in Java

In Java, reading and writing files is a common task for handling data persistence. Java provides several classes in the `java.nio.file` package for file operations, and `java.io` package is also commonly used for this purpose. Here, we'll cover the basics of reading and writing files in Java.

## Reading Files

### Using `Files` class (Java NIO)

The `Files` class in the `java.nio.file` package provides static methods for reading files.

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.io.IOException;
import java.util.List;

public class FileReadingExample {
    public static void main(String[] args) {
        Path filePath = Paths.get("path/to/your/file.txt");

        try {
            List<String> lines = Files.readAllLines(filePath);
            for (String line : lines) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.err.println("Error reading the file: " + e.getMessage());
        }
    }
}
```

### Using `BufferedReader` (Java IO)

The `BufferedReader` class in the `java.io` package can be used to read files.

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class BufferedReaderExample {
    public static void main(String[] args) {
        String filePath = "path/to/your/file.txt";

        try (BufferedReader reader = new BufferedReader(new FileReader(filePath))) {
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.err.println("Error reading the file: " + e.getMessage());
        }
    }
}
```

## Writing Files

### Using `Files` class (Java NIO)

The `Files` class can also be used for writing content to files.

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.io.IOException;
import java.util.List;

public class FileWritingExample {
    public static void main(String[] args) {
        Path filePath = Paths.get("path/to/your/output.txt");

        List<String> content = List.of("Line 1", "Line 2", "Line 3");

        try {
            Files.write(filePath, content);
            System.out.println("File written successfully.");
        } catch (IOException e) {
            System.err.println("Error writing to the file: " + e.getMessage());
        }
    }
}
```

### Using `BufferedWriter` (Java IO)

The `BufferedWriter` class in the `java.io` package can be used for writing content to files.

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;
import java.util.List;

public class BufferedWriterExample {
    public static void main(String[] args) {
        String filePath = "path/to/your/output.txt";

        List<String> content = List.of("Line 1", "Line 2", "Line 3");

        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filePath))) {
            for (String line : content) {
                writer.write(line);
                writer.newLine();
            }
            System.out.println("File written successfully.");
        } catch (IOException e) {
            System.err.println("Error writing to the file: " + e.getMessage());
        }
    }
}
```

## Summary

- Reading files in Java can be done using classes like `Files` (Java NIO) or `BufferedReader` (Java IO).
- Writing files in Java can be done using classes like `Files` (Java NIO) or `BufferedWriter` (Java IO).
- Always handle exceptions that may occur during file operations to ensure robustness.

For more details on file I/O in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/essential/io/index.html).
