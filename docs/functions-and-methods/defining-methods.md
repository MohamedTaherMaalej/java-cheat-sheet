# Defining Methods in Java

Methods in Java are blocks of code that perform a specific task or operation. They are defined within a class and can be called (invoked) to execute the code they contain. Here, we'll cover the basics of defining methods in Java.

## Method Declaration

A method is declared with the following syntax:

```java
returnType methodName(parameter1Type parameter1, parameter2Type parameter2, ...) {
    // Method body
    // Code to be executed
    return returnValue; // If the method has a return type
}
```

- **returnType**: The data type of the value the method returns. If the method does not return a value, use `void`.
- **methodName**: The name of the method.
- **parameter1Type, parameter2Type, ...**: The data types of the method parameters (if any).
- **returnValue**: The value that the method returns (if applicable).

## Example Method

```java
public class Calculator {

    // Method to add two integers
    public int add(int num1, int num2) {
        int sum = num1 + num2;
        return sum;
    }

    // Method to multiply two doubles
    public double multiply(double num1, double num2) {
        double result = num1 * num2;
        return result;
    }

    // Method with no return value
    public void displayMessage(String message) {
        System.out.println(message);
    }
}
```

In this example, the `Calculator` class contains three methods: `add`, `multiply`, and `displayMessage`.

## Calling Methods

Once a method is defined, it can be called from other parts of the program.

```java
public class Main {
    public static void main(String[] args) {
        Calculator calculator = new Calculator();

        // Calling the add method
        int sumResult = calculator.add(5, 3);
        System.out.println("Sum: " + sumResult);

        // Calling the multiply method
        double multiplyResult = calculator.multiply(2.5, 4.0);
        System.out.println("Product: " + multiplyResult);

        // Calling the displayMessage method
        calculator.displayMessage("Hello, Java Methods!");
    }
}
```

In this example, an instance of the `Calculator` class is created, and its methods are called to perform specific operations.

## Method Overloading

Java supports method overloading, which allows you to define multiple methods with the same name but different parameter lists.

```java
public class OverloadedMethods {

    // Method to add two integers
    public int add(int num1, int num2) {
        return num1 + num2;
    }

    // Overloaded method to add three integers
    public int add(int num1, int num2, int num3) {
        return num1 + num2 + num3;
    }

    // Overloaded method to concatenate two strings
    public String concatenate(String str1, String str2) {
        return str1 + str2;
    }
}
```

In this example, the `OverloadedMethods` class demonstrates method overloading with the `add` and `concatenate` methods.

## Summary

- Methods in Java are blocks of code that perform specific tasks.
- A method is defined with a return type, a name, a parameter list, and a method body.
- Methods can be called (invoked) from other parts of the program.
- Java supports method overloading, allowing multiple methods with the same name but different parameter lists.

For more details on methods in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html).

