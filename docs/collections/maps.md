# Maps in Java Collections

In Java, the `Map` interface is part of the Java Collections Framework and represents a collection of key-value pairs. Implementations of the `Map` interface include `HashMap`, `LinkedHashMap`, and `TreeMap`. Here, we'll cover the basics of using maps in Java Collections.

## Introduction to Maps

A map is a collection that associates unique keys with values. Each key in a map is associated with exactly one value. Maps provide methods for adding, removing, and retrieving values based on their keys.

### Common Map Implementations

1. **HashMap**: Implements a hash table for storing key-value pairs. Provides constant-time performance for basic operations.

2. **LinkedHashMap**: Extends `HashMap` and maintains the order of key-value pairs. Elements are ordered by the order in which they were inserted.

3. **TreeMap**: Implements a red-black tree for storing key-value pairs. Provides ordered access based on the natural order of keys or a custom comparator.

## Creating a Map

### Using HashMap

```java
import java.util.HashMap;
import java.util.Map;

public class MapExample {
    public static void main(String[] args) {
        // Creating a HashMap
        Map<String, Integer> ageMap = new HashMap<>();

        // Adding key-value pairs to the map
        ageMap.put("Alice", 25);
        ageMap.put("Bob", 30);
        ageMap.put("Charlie", 22);
    }
}
```

### Using TreeMap

```java
import java.util.Map;
import java.util.TreeMap;

public class MapExample {
    public static void main(String[] args) {
        // Creating a TreeMap
        Map<String, String> capitalMap = new TreeMap<>();

        // Adding key-value pairs to the map
        capitalMap.put("USA", "Washington, D.C.");
        capitalMap.put("France", "Paris");
        capitalMap.put("Japan", "Tokyo");
    }
}
```

## Common Operations on Maps

### Adding Key-Value Pairs

```java
Map<Integer, String> studentMap = new HashMap<>();
studentMap.put(101, "John");
studentMap.put(102, "Alice");
studentMap.put(103, "Bob");
```

### Removing Key-Value Pairs

```java
Map<String, Double> priceMap = new TreeMap<>();
priceMap.put("Apple", 2.5);
priceMap.put("Banana", 1.0);
priceMap.put("Orange", 3.0);

priceMap.remove("Banana"); // Removes the entry with key "Banana"
```

### Retrieving Values

```java
int age = ageMap.get("Alice"); // Retrieves the age of "Alice"
```

## Summary

- Maps in Java Collections represent collections of key-value pairs.
- Common implementations include `HashMap`, `LinkedHashMap`, and `TreeMap`.
- Maps provide efficient methods for adding, removing, and retrieving values based on their keys.
- Choose the appropriate implementation based on performance and ordering requirements.

For more details on Maps and Java Collections, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/collections/interfaces/map.html).
