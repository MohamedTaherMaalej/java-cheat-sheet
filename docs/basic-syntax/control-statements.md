# Control Statements in Java

Control statements in Java allow you to control the flow of your program's execution. They include decision-making statements and looping statements. Here, we'll cover some of the basic control statements in Java.

## Decision-Making Statements

### 1. **if Statement**

The `if` statement is used to execute a block of code only if a specified condition is true.

```java
int x = 10;

if (x > 5) {
    System.out.println("x is greater than 5");
}
```

### 2. **if-else Statement**

The `if-else` statement allows you to execute one block of code if the condition is true and another block if the condition is false.

```java
int y = 3;

if (y % 2 == 0) {
    System.out.println("y is even");
} else {
    System.out.println("y is odd");
}
```

### 3. **else-if Statement**

The `else-if` statement allows you to check multiple conditions.

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

## Looping Statements

### 1. **for Loop**

The `for` loop is used to iterate over a range of values.

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Iteration " + i);
}
```

### 2. **while Loop**

The `while` loop repeats a block of code as long as a specified condition is true.

```java
int count = 0;

while (count < 3) {
    System.out.println("Count: " + count);
    count++;
}
```

### 3. **do-while Loop**

The `do-while` loop is similar to the `while` loop but guarantees that the code inside the loop is executed at least once.

```java
int i = 1;

do {
    System.out.println("i: " + i);
    i++;
} while (i <= 3);
```

### 4. **break and continue Statements**

The `break` statement is used to exit a loop prematurely, and the `continue` statement is used to skip the rest of the loop and move to the next iteration.

```java
for (int j = 1; j <= 5; j++) {
    if (j == 3) {
        break; // exit the loop when j is 3
    }
    System.out.println("Iteration " + j);
}

for (int k = 1; k <= 5; k++) {
    if (k == 3) {
        continue; // skip iteration when k is 3
    }
    System.out.println("Iteration " + k);
}
```

These are some of the basic control statements in Java. For more details and advanced control flow structures, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/flow.html).

