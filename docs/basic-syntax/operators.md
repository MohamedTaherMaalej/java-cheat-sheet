 Operators in Java

Operators in Java are special symbols that perform operations on operands. They are the building blocks of expressions and allow you to manipulate variables and values in your code. Here, we'll cover some of the basic operators in Java.

## Arithmetic Operators

Arithmetic operators perform mathematical operations on numeric values.

- Addition (`+`): Adds two values.
- Subtraction (`-`): Subtracts the right operand from the left operand.
- Multiplication (`*`): Multiplies two values.
- Division (`/`): Divides the left operand by the right operand.
- Modulus (`%`): Returns the remainder of the division.

```java
int a = 10;
int b = 3;

int sum = a + b;      // 13
int difference = a - b; // 7
int product = a * b;   // 30
int quotient = a / b;  // 3
int remainder = a % b; // 1
```

## Relational Operators

Relational operators compare two values and return a boolean result.

- Equal to (`==`): Checks if two values are equal.
- Not equal to (`!=`): Checks if two values are not equal.
- Greater than (`>`): Checks if the left operand is greater than the right operand.
- Less than (`<`): Checks if the left operand is less than the right operand.
- Greater than or equal to (`>=`): Checks if the left operand is greater than or equal to the right operand.
- Less than or equal to (`<=`): Checks if the left operand is less than or equal to the right operand.

```java
int x = 5;
int y = 10;

boolean isEqual = (x == y);     // false
boolean isNotEqual = (x != y);  // true
boolean isGreaterThan = (x > y); // false
boolean isLessThan = (x < y);    // true
```

## Logical Operators

Logical operators perform logical operations on boolean values.

- Logical AND (`&&`): Returns true if both operands are true.
- Logical OR (`||`): Returns true if at least one operand is true.
- Logical NOT (`!`): Returns true if the operand is false and vice versa.

```java
boolean condition1 = true;
boolean condition2 = false;

boolean andResult = (condition1 && condition2); // false
boolean orResult = (condition1 || condition2);  // true
boolean notResult = !condition1;                // false
```

## Assignment Operators

Assignment operators assign values to variables.

- Assignment (`=`): Assigns the value on the right to the variable on the left.
- Addition assignment (`+=`): Adds the right operand to the left operand and assigns the result to the left operand.
- Subtraction assignment (`-=`): Subtracts the right operand from the left operand and assigns the result to the left operand.
- Multiplication assignment (`*=`): Multiplies the left operand by the right operand and assigns the result to the left operand.
- Division assignment (`/=`): Divides the left operand by the right operand and assigns the result to the left operand.
- Modulus assignment (`%=`): Computes the modulus of the left operand with the right operand and assigns the result to the left operand.

```java
int num = 10;

num += 5;  // num is now 15
num -= 3;  // num is now 12
num *= 2;  // num is now 24
num /= 4;  // num is now 6
num %= 3;  // num is now 0
```

## Increment and Decrement Operators

Increment and decrement operators increase or decrease the value of a variable by 1.

- Increment (`++`): Increases the value by 1.
- Decrement (`--`): Decreases the value by 1.

```java
int count = 5;

count++; // count is now 6
count--; // count is now 5
```

## Conditional (Ternary) Operator

The conditional operator (`? :`) is a shorthand for the if-else statement.

```java
int a = 5;
int b = 10;

int result = (a > b) ? a : b; // result is 10
```

These are some of the basic operators in Java. For more details and additional operators, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/operators.html).
