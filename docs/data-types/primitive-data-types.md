# Primitive Data Types in Java

Java has several built-in primitive data types that represent basic values. These data types are the foundation for working with variables and storing information. Here, we'll cover the commonly used primitive data types in Java.

## Numeric Data Types

### 1. **int (Integer)**

The `int` data type is used to represent whole numbers (integers).

```java
int age = 25;
```

### 2. **double (Double-precision Floating Point)**

The `double` data type is used to represent decimal numbers.

```java
double price = 19.99;
```

### 3. **float (Single-precision Floating Point)**

The `float` data type is also used to represent decimal numbers but with less precision than `double`.

```java
float temperature = 98.6f;
```

### 4. **short (Short Integer)**

The `short` data type is used to represent smaller whole numbers.

```java
short quantity = 100;
```

### 5. **long (Long Integer)**

The `long` data type is used to represent larger whole numbers.

```java
long population = 7000000000L;
```

### 6. **byte (Byte)**

The `byte` data type is used to represent small integers.

```java
byte data = 42;
```

## Character Data Type

### 7. **char (Character)**

The `char` data type is used to represent a single character.

```java
char grade = 'A';
```

## Boolean Data Type

### 8. **boolean (Boolean)**

The `boolean` data type is used to represent true or false values.

```java
boolean isJavaFun = true;
```

## Default Values

When you declare a variable but do not initialize it, Java assigns a default value based on its data type.

- `0` for numeric types (`int`, `double`, `float`, `short`, `long`, `byte`).
- `\u0000` for the `char` type.
- `false` for the `boolean` type.

## Range of Values

Each primitive data type has a specific range of values it can hold, which is determined by the number of bits used to represent it.

- `int`: 32 bits, range from -2^31 to 2^31 - 1.
- `double`: 64 bits, precision for floating-point numbers.
- `char`: 16 bits, Unicode character.
- `boolean`: Represents true or false.

## Summary

- Java has several primitive data types for representing different kinds of values.
- Numeric data types include `int`, `double`, `float`, `short`, `long`, and `byte`.
- The `char` data type represents a single character.
- The `boolean` data type represents true or false values.
- Each data type has a default value if not explicitly initialized.

For more details on Java data types, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html).
