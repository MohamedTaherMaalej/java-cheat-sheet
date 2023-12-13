# File I/O Operations in Java

File I/O (Input/Output) operations in Java involve reading from and writing to files. Java provides various classes in the `java.nio.file` and `java.io` packages for handling file I/O. Here, we'll cover common file I/O operations in Java.

## Checking if a File Exists

You can use the `Files.exists()` method to check if a file exists.

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class FileExistsExample {
    public static void main(String[] args) {
        Path filePath = Paths.get("path/to/your/file.txt");

        if (Files.exists(filePath)) {
            System.out.println("File exists.");
        } else {
            System.out.println("File does not exist.");
        }
    }
}
```

## Creating a New File

To create a new file, you can use the `Files.createFile()` method.

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.io.IOException;

public class CreateFileExample {
    public static void main(String[] args) {
        Path filePath = Paths.get("path/to/your/newfile.txt");

        try {
            Files.createFile(filePath);
            System.out.println("File created successfully.");
        } catch (IOException e) {
            System.err.println("Error creating the file: " + e.getMessage());
        }
    }
}
```

## Deleting a File

To delete a file, you can use the `Files.delete()` method.

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.io.IOException;

public class DeleteFileExample {
    public static void main(String[] args) {
        Path filePath = Paths.get("path/to/your/file.txt");

        try {
            Files.delete(filePath);
            System.out.println("File deleted successfully.");
        } catch (IOException e) {
            System.err.println("Error deleting the file: " + e.getMessage());
        }
    }
}
```

## Copying a File

To copy a file, you can use the `Files.copy()` method.

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.io.IOException;

public class CopyFileExample {
    public static void main(String[] args) {
        Path sourcePath = Paths.get("path/to/your/source.txt");
        Path targetPath = Paths.get("path/to/your/target.txt");

        try {
            Files.copy(sourcePath, targetPath);
            System.out.println("File copied successfully.");
        } catch (IOException e) {
            System.err.println("Error copying the file: " + e.getMessage());
        }
    }
}
```

## Moving a File

To move or rename a file, you can use the `Files.move()` method.

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.io.IOException;

public class MoveFileExample {
    public static void main(String[] args) {
        Path sourcePath = Paths.get("path/to/your/source.txt");
        Path targetPath = Paths.get("path/to/your/target.txt");

        try {
            Files.move(sourcePath, targetPath);
            System.out.println("File moved successfully.");
        } catch (IOException e) {
            System.err.println("Error moving the file: " + e.getMessage());
        }
    }
}
```

## Summary

- File I/O operations in Java involve reading from and writing to files.
- Common file operations include checking if a file exists, creating a new file, deleting a file, copying a file, and moving a file.
- Handle exceptions that may occur during file I/O to ensure robustness.

For more details on file I/O in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/essential/io/index.html).
