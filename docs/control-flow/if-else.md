# if-else Statement in Java

The `if-else` statement in Java is used to make decisions in your code. It allows you to execute a block of code if a specified condition is true and another block of code if the condition is false. Here, we'll cover the basics of using the `if-else` statement.

## Syntax

The general syntax of the `if-else` statement is as follows:

```java
if (condition) {
    // Code to be executed if the condition is true
} else {
    // Code to be executed if the condition is false
}
```

## Example

```java
int x = 10;

if (x > 5) {
    System.out.println("x is greater than 5");
} else {
    System.out.println("x is not greater than 5");
}
```

In this example, if the value of `x` is greater than 5, the message "x is greater than 5" will be printed. Otherwise, the message "x is not greater than 5" will be printed.

## Multiple Conditions with else-if

You can use the `else-if` statement to check multiple conditions in a sequence.

```java
int grade = 75;

if (grade >= 90) {
    System.out.println("A");
} else if (grade >= 80) {
    System.out.println("B");
} else if (grade >= 70) {
    System.out.println("C");
} else {
    System.out.println("F");
}
```

In this example, the program checks the value of `grade` and prints the corresponding letter grade based on the conditions.

## Nested if-else Statements

You can also nest `if-else` statements inside each other for more complex decision-making.

```java
int num = 10;

if (num > 0) {
    if (num % 2 == 0) {
        System.out.println("Positive and even");
    } else {
        System.out.println("Positive and odd");
    }
} else if (num < 0) {
    System.out.println("Negative");
} else {
    System.out.println("Zero");
}
```

In this example, the program checks whether a number is positive, negative, or zero and whether it's even or odd.

## Summary

- The `if-else` statement is used for decision-making in Java.
- It executes a block of code if a specified condition is true and another block if the condition is false.
- You can use `else-if` for multiple conditions, and you can nest `if-else` statements for more complex scenarios.

For more details on the `if-else` statement and control flow in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/if.html).
