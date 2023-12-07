# Strings in Java

Strings in Java are objects that represent sequences of characters. They are widely used for storing and manipulating text in Java programs. Here, we'll cover the basics of working with strings in Java.

## Declaration and Initialization

### 1. **Declaration**

To declare a string, you can use the `String` class.

```java
String greeting;
```

### 2. **Initialization**

You can initialize a string using the assignment operator (`=`).

```java
greeting = "Hello, World!";
```

### 3. **Concatenation**

Strings can be concatenated using the `+` operator.

```java
String firstName = "John";
String lastName = "Doe";
String fullName = firstName + " " + lastName; // Result: "John Doe"
```

## Common String Methods

### 1. **length()**

The `length()` method returns the number of characters in a string.

```java
String message = "Hello";
int length = message.length(); // Result: 5
```

### 2. **charAt()**

The `charAt(index)` method returns the character at the specified index.

```java
char firstChar = message.charAt(0); // Result: 'H'
```

### 3. **substring()**

The `substring(startIndex, endIndex)` method extracts a substring from the original string.

```java
String subString = message.substring(1, 4); // Result: "ell"
```

### 4. **toLowerCase() and toUpperCase()**

These methods convert the string to lowercase or uppercase.

```java
String lowercase = message.toLowerCase(); // Result: "hello"
String uppercase = message.toUpperCase(); // Result: "HELLO"
```

### 5. **equals() and equalsIgnoreCase()**

The `equals()` method compares two strings for equality, while `equalsIgnoreCase()` ignores case differences.

```java
String str1 = "hello";
String str2 = "HELLO";

boolean isEqual = str1.equals(str2); // Result: false
boolean isEqualIgnoreCase = str1.equalsIgnoreCase(str2); // Result: true
```

### 6. **startsWith() and endsWith()**

These methods check if a string starts or ends with a specified prefix or suffix.

```java
boolean startsWithHello = message.startsWith("Hello"); // Result: true
boolean endsWithWorld = message.endsWith("World"); // Result: false
```

## String Concatenation

You can use the `+` operator or the `concat()` method for string concatenation.

```java
String str1 = "Hello";
String str2 = "World";

String result1 = str1 + " " + str2; // Result: "Hello World"
String result2 = str1.concat(" ").concat(str2); // Result: "Hello World"
```

## String Formatting

You can use the `printf()` method for formatted string output.

```java
String name = "John";
int age = 25;

String formattedString = String.format("Name: %s, Age: %d", name, age);
System.out.println(formattedString); // Result: "Name: John, Age: 25"
```

## Summary

- Strings in Java are objects that represent sequences of characters.
- Strings can be declared and initialized using the `String` class.
- Common string methods include `length()`, `charAt()`, `substring()`, `toLowerCase()`, `toUpperCase()`, `equals()`, and more.
- String concatenation can be done using the `+` operator or the `concat()` method.
- String formatting can be achieved using the `printf()` method.

For more details on working with strings in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/data/strings.html).

