# JUnit Testing Framework

JUnit is a widely used testing framework for Java that simplifies the process of writing and executing unit tests. It provides annotations to identify test methods, asserts to verify expected results, and various features for test organization. This document covers the fundamental concepts and usage of JUnit.

## Getting Started with JUnit

### Adding JUnit Dependency

To use JUnit in your Java project, you need to include the JUnit dependency in your build configuration. If you are using Maven, add the following dependency to your `pom.xml`:

```xml
<dependencies>
    <dependency>
        <groupId>junit</groupId>
        <artifactId>junit</artifactId>
        <version>4.12</version> <!-- Replace with the latest version -->
        <scope>test</scope>
    </dependency>
</dependencies>
```

If you are using Gradle, add the following to your `build.gradle`:

```groovy
testImplementation 'junit:junit:4.12' // Replace with the latest version
```

### Writing Your First Test

Create a test class with methods annotated with `@Test`. JUnit will recognize these methods as test cases.

```java
import org.junit.Test;
import static org.junit.Assert.assertEquals;

public class MyTestClass {

    @Test
    public void testAddition() {
        int result = 2 + 2;
        assertEquals(4, result);
    }
}
```

### Running Tests

You can run JUnit tests in your IDE or using build tools like Maven or Gradle. Most IDEs provide a built-in test runner, and you can also use the following command with Maven or Gradle:

**Maven:**

```bash
mvn test
```

**Gradle:**

```bash
gradlew test
```

## JUnit Annotations

JUnit uses annotations to identify test methods and to provide additional configuration.

- `@Test`: Marks a method as a test method.
- `@Before`: Executed before each test method.
- `@After`: Executed after each test method.
- `@BeforeClass`: Executed once before all test methods in the class.
- `@AfterClass`: Executed once after all test methods in the class.
- `@Ignore`: Skips a test method.

Example:

```java
import org.junit.*;

public class MyTestClass {

    @BeforeClass
    public static void setUpBeforeClass() {
        // Initialization code before all tests
    }

    @AfterClass
    public static void tearDownAfterClass() {
        // Cleanup code after all tests
    }

    @Before
    public void setUp() {
        // Initialization code before each test
    }

    @After
    public void tearDown() {
        // Cleanup code after each test
    }

    @Test
    public void testExample() {
        // Test method
    }

    @Ignore
    @Test
    public void testIgnored() {
        // This test will be ignored
    }
}
```

## Asserting with JUnit

JUnit provides a set of assert methods in the `org.junit.Assert` class to verify expected results.

- `assertEquals(expected, actual)`: Tests if two values are equal.
- `assertTrue(condition)`: Tests if a condition is true.
- `assertFalse(condition)`: Tests if a condition is false.
- `assertNull(object)`: Tests if an object is null.
- `assertNotNull(object)`: Tests if an object is not null.
- `assertSame(expected, actual)`: Tests if two references point to the same object.
- `assertNotSame(expected, actual)`: Tests if two references do not point to the same object.

Example:

```java
import static org.junit.Assert.*;

public class MyTestClass {

    @Test
    public void testAssertMethods() {
        assertEquals(4, 2 + 2);
        assertTrue(5 > 3);
        assertFalse(2 == 1);
        assertNull(null);
        assertNotNull("Hello");
        assertSame("abc", "abc");
        assertNotSame("abc", new String("abc"));
    }
}
```

## Parameterized Tests

JUnit supports parameterized tests, allowing you to run the same test logic with different sets of parameters.

```java
import org.junit.Test;
import org.junit.runner.RunWith;
import org.junit.runners.Parameterized;
import java.util.Arrays;
import java.util.Collection;
import static org.junit.Assert.assertEquals;

@RunWith(Parameterized.class)
public class ParameterizedTest {

    private final int input;
    private final int expected;

    @Parameterized.Parameters
    public static Collection<Object[]> data() {
        return Arrays.asList(new Object[][]{
                {1, 2},
                {5, 7},
                {10, 12}
        });
    }

    public ParameterizedTest(int input, int expected) {
        this.input = input;
        this.expected = expected;
    }

    @Test
    public void testAddition() {
        assertEquals(expected, input + 1);
    }
}
```

## Conclusion

JUnit is an essential tool for writing and executing unit tests in Java. By following best practices, organizing tests effectively, and utilizing JUnit features, developers can ensure the reliability and correctness of their code.

For more details on JUnit, refer to the [official JUnit documentation](https://junit.org/junit5/docs/current/user-guide/).
