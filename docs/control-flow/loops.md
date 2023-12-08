# Loops in Java

Loops in Java are used to execute a block of code repeatedly. They provide a way to perform iterative tasks and automate repetitive actions. Here, we'll cover the basics of the `for`, `while`, and `do-while` loops in Java.

## for Loop

The `for` loop is commonly used when the number of iterations is known in advance.

```java
for (int i = 0; i < 5; i++) {
    System.out.println("Iteration " + i);
}
```

In this example, the loop initializes a variable `i` to 0, executes the loop as long as `i` is less than 5, increments `i` after each iteration, and prints the iteration number.

## while Loop

The `while` loop is used when the number of iterations is not known in advance, and the loop continues as long as a specified condition is true.

```java
int count = 0;

while (count < 3) {
    System.out.println("Count: " + count);
    count++;
}
```

This example prints the value of `count` as long as it is less than 3.

## do-while Loop

The `do-while` loop is similar to the `while` loop but guarantees that the loop's body is executed at least once, as the condition is checked after the loop body.

```java
int i = 1;

do {
    System.out.println("i: " + i);
    i++;
} while (i <= 3);
```

This example prints the value of `i` and increments it as long as `i` is less than or equal to 3.

## Breaking and Continuing

### break Statement

The `break` statement is used to exit a loop prematurely.

```java
for (int j = 1; j <= 5; j++) {
    if (j == 3) {
        break; // Exit the loop when j is 3
    }
    System.out.println("Iteration " + j);
}
```

### continue Statement

The `continue` statement is used to skip the rest of the loop and move to the next iteration.

```java
for (int k = 1; k <= 5; k++) {
    if (k == 3) {
        continue; // Skip iteration when k is 3
    }
    System.out.println("Iteration " + k);
}
```

## Nested Loops

Loops can be nested inside each other to create more complex patterns.

```java
for (int row = 1; row <= 3; row++) {
    for (int col = 1; col <= 3; col++) {
        System.out.print(row * col + " ");
    }
    System.out.println();
}
```

This example demonstrates a nested `for` loop to create a multiplication table.

## Summary

- The `for` loop is used for a known number of iterations.
- The `while` loop is used for an unknown number of iterations based on a condition.
- The `do-while` loop guarantees at least one execution of the loop body.
- The `break` statement is used to exit a loop prematurely.
- The `continue` statement skips the rest of the loop and moves to the next iteration.
- Loops can be nested to create more complex patterns.

For more details on loops in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/while.html).
