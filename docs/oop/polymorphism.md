# Polymorphism in Java

Polymorphism is a fundamental concept in object-oriented programming (OOP) that allows objects of different types to be treated as objects of a common type. In Java, polymorphism is achieved through method overriding and interfaces. Here, we'll cover the basics of polymorphism and provide examples.

## Types of Polymorphism

### Compile-Time Polymorphism (Method Overloading)

Compile-time polymorphism, also known as method overloading, occurs when a class has multiple methods with the same name but different parameter lists.

```java
public class Calculator {

    // Method to add two integers
    public int add(int num1, int num2) {
        return num1 + num2;
    }

    // Overloaded method to add three integers
    public int add(int num1, int num2, int num3) {
        return num1 + num2 + num3;
    }

    // Overloaded method to add two doubles
    public double add(double num1, double num2) {
        return num1 + num2;
    }
}
```

In this example, the `add` method is overloaded with different parameter lists.

### Runtime Polymorphism (Method Overriding)

Runtime polymorphism, also known as method overriding, occurs when a subclass provides a specific implementation for a method that is already defined in its superclass.

```java
class Animal {
    void makeSound() {
        System.out.println("Some generic sound");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Woof! Woof!");
    }
}
```

In this example, the `Dog` class overrides the `makeSound` method from the `Animal` class.

### Polymorphism through Interfaces

Java supports polymorphism through interfaces. Multiple classes can implement the same interface, and objects of these classes can be treated as objects of the interface type.

```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing a circle");
    }
}

class Square implements Shape {
    public void draw() {
        System.out.println("Drawing a square");
    }
}
```

In this example, both `Circle` and `Square` implement the `Shape` interface, and objects of these classes can be treated as `Shape` objects.

## Benefits of Polymorphism

1. **Code Reusability**: Polymorphism promotes code reusability by allowing different objects to be treated uniformly.

2. **Flexibility**: Polymorphism provides flexibility in designing and modifying the structure of the code.

3. **Ease of Maintenance**: Polymorphic code tends to be easier to maintain, as changes can be made more efficiently.

## Summary

- Polymorphism is a concept in Java that allows objects of different types to be treated as objects of a common type.
- Method overloading is a form of compile-time polymorphism, achieved by having multiple methods with the same name but different parameter lists.
- Method overriding is a form of runtime polymorphism, achieved by providing a specific implementation for a method in a subclass.
- Polymorphism through interfaces allows objects of different classes to be treated uniformly if they implement the same interface.
- Polymorphism promotes code reusability, flexibility, and ease of maintenance.

For more details on polymorphism in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/IandI/polymorphism.html).
