# Arrays in Java

Arrays in Java are used to store multiple values of the same type under a single variable name. They provide a way to group elements and access them using an index. Here, we'll cover the basics of working with arrays in Java.

## Declaration and Initialization

### 1. **Declaration**

To declare an array, you specify the data type of the elements followed by square brackets `[]` and the array name.

```java
int[] numbers;
```

### 2. **Initialization**

You can initialize an array using the `new` keyword and specifying the size of the array.

```java
numbers = new int[5]; // Creates an array with a size of 5
```

### 3. **Declaration and Initialization in One Line**

You can combine declaration and initialization in one line.

```java
int[] numbers = new int[5];
```

### 4. **Array Literal (Shortcut Initialization)**

Alternatively, you can use an array literal to initialize the array with values.

```java
int[] numbers = {1, 2, 3, 4, 5};
```

## Accessing Array Elements

Array elements are accessed using an index, starting from 0.

```java
int firstNumber = numbers[0]; // Access the first element
int thirdNumber = numbers[2]; // Access the third element
```

## Array Length

You can find the length of an array using the `length` property.

```java
int arrayLength = numbers.length;
```

## Iterating Over Arrays

You can use loops to iterate over the elements of an array.

### 1. **for Loop**

```java
for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

### 2. **Enhanced for Loop (for-each)**

```java
for (int num : numbers) {
    System.out.println(num);
}
```

## Multidimensional Arrays

Java supports multidimensional arrays, such as 2D arrays.

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

Accessing elements in a 2D array:

```java
int element = matrix[1][2]; // Access the element in the second row, third column
```

## Array Methods

Java provides several utility methods for working with arrays, such as sorting and searching.

```java
// Sorting
Arrays.sort(numbers);

// Searching
int index = Arrays.binarySearch(numbers, 3);
```

## Summary

- Arrays in Java are used to store multiple values of the same type.
- Declaration and initialization can be separate or combined.
- Array elements are accessed using an index, starting from 0.
- The length of an array is obtained using the `length` property.
- Loops are used to iterate over the elements of an array.
- Java supports multidimensional arrays.

For more details on Java arrays, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html).
