# Encapsulation in Java

Encapsulation is one of the four fundamental Object-Oriented Programming (OOP) concepts, alongside inheritance, polymorphism, and abstraction. It refers to the bundling of data (attributes) and the methods (functions) that operate on the data into a single unit, known as a class. Encapsulation helps in data hiding, protecting the internal state of an object from external access. Here, we'll cover the basics of encapsulation in Java.

## Basics of Encapsulation

### Access Modifiers

In Java, access modifiers control the visibility of classes, fields, and methods. There are four access modifiers:

- **Public**: Accessible from anywhere.
- **Private**: Accessible only within the same class.
- **Protected**: Accessible within the same class and its subclasses.
- **Default (Package-Private)**: Accessible only within the same package.

### Example of Encapsulation

```java
public class Car {

    // Private data members
    private String make;
    private String model;
    private int year;

    // Public constructor
    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Public getter methods
    public String getMake() {
        return make;
    }

    public String getModel() {
        return model;
    }

    public int getYear() {
        return year;
    }

    // Public setter methods
    public void setMake(String make) {
        this.make = make;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public void setYear(int year) {
        this.year = year;
    }
}
```

In this example, the `Car` class encapsulates the data members (`make`, `model`, `year`) by making them private and provides public getter and setter methods to access and modify the data.

## Benefits of Encapsulation

1. **Data Hiding**: Encapsulation hides the internal details of the object and restricts direct access to its state. This helps in preventing unauthorized modifications.

2. **Flexibility**: Encapsulation provides flexibility in modifying the internal implementation of the class without affecting the external code that uses the class.

3. **Code Organization**: Encapsulation organizes code by grouping related attributes and methods within a class.

4. **Maintenance**: Encapsulation makes it easier to maintain and evolve the codebase over time.

## Encapsulation Best Practices

1. **Keep Data Private**: Make data members private to control access and modification.

2. **Provide Public Accessors and Mutators**: Use public methods (getters and setters) to access and modify the private data.

3. **Validate Inputs**: Include validation logic in setter methods to ensure data integrity.

## Summary

- Encapsulation is the bundling of data and methods that operate on the data within a single unit, known as a class.
- Access modifiers (public, private, protected, default) control the visibility of classes, fields, and methods.
- Encapsulation provides benefits such as data hiding, flexibility, code organization, and ease of maintenance.
- Best practices for encapsulation include keeping data private, providing public accessors and mutators, and validating inputs.

For more details on encapsulation in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/concepts/index.html).
