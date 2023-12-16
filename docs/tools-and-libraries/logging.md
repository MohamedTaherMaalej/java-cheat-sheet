# Logging in Java

Logging is an essential aspect of software development, providing a mechanism to record and analyze information about a running application. In Java, the `java.util.logging` framework is a built-in logging solution that simplifies the process of capturing and managing log information. This document covers the fundamentals of logging in Java using the `java.util.logging` framework.

## Basics of Logging

### Configuration

Java's logging system can be configured through a `logging.properties` file or programmatically. The configuration includes settings such as log levels, log file locations, and log formatting.

Example `logging.properties`:

```properties
# Set the default logging level to INFO
.level=INFO

# Configure a FileHandler to write logs to a file
handlers=java.util.logging.FileHandler
java.util.logging.FileHandler.pattern=%h/java.log
java.util.logging.FileHandler.limit=50000
java.util.logging.FileHandler.count=1
java.util.logging.FileHandler.formatter=java.util.logging.SimpleFormatter
```

### Log Levels

Java's logging framework supports different log levels to categorize log messages based on their severity. Common log levels include:

- `SEVERE`: The highest severity; indicates a severe error that will prevent the application from continuing.
- `WARNING`: Indicates potential issues that do not prevent the application from continuing.
- `INFO`: Provides informational messages about the application's operation.
- `CONFIG`: Configuration-related messages.
- `FINE`, `FINER`, `FINEST`: Lower-severity levels for debugging purposes.

## Logging in Java Code

### Getting a Logger

To log messages in Java code, you need to obtain a logger instance. Typically, each class has its own logger.

```java
import java.util.logging.Logger;

public class MyClass {
    private static final Logger LOGGER = Logger.getLogger(MyClass.class.getName());

    public void doSomething() {
        LOGGER.info("Doing something...");
    }
}
```

### Logging Messages

Once you have a logger, you can use its methods to log messages.

```java
import java.util.logging.Logger;

public class MyClass {
    private static final Logger LOGGER = Logger.getLogger(MyClass.class.getName());

    public void doSomething() {
        LOGGER.info("Doing something...");
        LOGGER.warning("A warning message...");
        LOGGER.severe("A severe error occurred!");
    }
}
```

### Formatting Log Messages

You can customize the format of log messages by providing a custom `Formatter`. Java provides built-in formatters like `SimpleFormatter` and `XMLFormatter`, or you can create a custom formatter.

```java
import java.util.logging.ConsoleHandler;
import java.util.logging.Formatter;
import java.util.logging.LogRecord;
import java.util.logging.Logger;

public class CustomFormatterExample {
    private static final Logger LOGGER = Logger.getLogger(CustomFormatterExample.class.getName());

    public static void main(String[] args) {
        ConsoleHandler consoleHandler = new ConsoleHandler();
        consoleHandler.setFormatter(new CustomFormatter());

        LOGGER.addHandler(consoleHandler);

        LOGGER.info("Custom log message");
    }

    static class CustomFormatter extends Formatter {
        @Override
        public String format(LogRecord record) {
            return "[" + record.getLevel() + "] " + record.getMessage() + "\n";
        }
    }
}
```

## Handling Exceptions

Java's logging framework can also handle exceptions, allowing you to log stack traces.

```java
import java.util.logging.Level;
import java.util.logging.Logger;

public class ExceptionLoggingExample {
    private static final Logger LOGGER = Logger.getLogger(ExceptionLoggingExample.class.getName());

    public static void main(String[] args) {
        try {
            // Some code that may throw an exception
            throw new RuntimeException("An example exception");
        } catch (RuntimeException e) {
            LOGGER.log(Level.SEVERE, "Exception occurred", e);
        }
    }
}
```

## Conclusion

Logging is a critical aspect of software development for tracking and debugging applications. Java's built-in `java.util.logging` framework provides a straightforward solution for incorporating logging into your Java projects.

For more details on Java logging, refer to the [official Java Logging Overview](https://docs.oracle.com/en/java/javase/14/core/java-logging-overview.html).

