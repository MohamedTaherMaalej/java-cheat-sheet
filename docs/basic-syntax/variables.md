# Variables in Java

In Java, variables are containers for storing data values. They play a crucial role in programming by allowing developers to store and manipulate data in their programs. Here, we'll cover the basics of declaring and using variables in Java.

## Declaration and Initialization

In Java, you declare a variable by specifying its data type and name. You can also initialize the variable with a value at the time of declaration or later in your code.

```java
// Declaration without initialization
int age;

// Declaration with initialization
double salary = 50000.50;
```

## Data Types

Java has several built-in data types for variables. Some common ones include:

- **Primitive Data Types:**
  - `int`: Integer type
  - `double`: Double-precision floating-point type
  - `char`: Character type
  - `boolean`: Boolean type

- **Reference Data Types:**
  - `String`: Represents a sequence of characters
  - `Object`: The base class for all Java classes

## Naming Conventions

Follow these naming conventions when naming your variables:

- Variable names are case-sensitive (`age` and `Age` are different).
- Start variable names with a letter, dollar sign ($), or underscore (_).
- Subsequent characters may be letters, digits, dollar signs, or underscores.
- Avoid using Java reserved words.

```java
// Good variable names
int studentAge;
double accountBalance;

// Avoid using Java reserved words
// int class; // Incorrect
```

## Variable Scope

The scope of a variable defines where it is accessible. In Java, variables can have one of three scopes:

1. **Local Variables:** Declared inside a method or a block, and their scope is limited to that block.

```java
void exampleMethod() {
    int localVar = 10; // Local variable
    // ...
}
```

2. **Instance Variables (Fields):** Declared within a class but outside any method. They belong to an instance of the class.

```java
public class MyClass {
    int instanceVar; // Instance variable
    // ...
}
```

3. **Class Variables (Static Fields):** Shared among all instances of a class. Declared with the `static` keyword.

```java
public class MyClass {
    static int classVar; // Class variable
    // ...
}
```

## Final Keyword

The `final` keyword can be used to make a variable a constant, meaning its value cannot be changed once assigned.

```java
final int MAX_SIZE = 100;
```

## Summary

- Variables are containers for storing data values.
- Declare a variable by specifying its data type and name.
- Initialize a variable with a value at the time of declaration or later.
- Java has primitive and reference data types.
- Follow naming conventions for variable names.
- Variables have scope (local, instance, or class).
- Use the `final` keyword to create constants.

For more details on Java variables, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/variables.html).

