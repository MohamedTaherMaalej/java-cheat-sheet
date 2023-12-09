# Classes and Objects in Java

In Java, classes and objects are fundamental concepts of object-oriented programming (OOP). Classes serve as blueprints for creating objects, and objects are instances of classes that encapsulate data and behavior. Here, we'll cover the basics of classes and objects in Java.

## Classes

A class is a template or blueprint that defines the structure and behavior of objects. It encapsulates data members (fields or attributes) and methods (functions) that operate on the data.

### Declaring a Class

```java
// Class declaration
public class Car {

    // Data members (fields)
    String make;
    String model;
    int year;

    // Constructor
    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Method to display information about the car
    public void displayInfo() {
        System.out.println("Make: " + make + ", Model: " + model + ", Year: " + year);
    }
}
```

In this example, the `Car` class has data members (`make`, `model`, `year`), a constructor, and a method (`displayInfo`).

## Objects

An object is an instance of a class. It represents a real-world entity and can be created based on the blueprint provided by the class.

### Creating Objects

```java
public class Main {
    public static void main(String[] args) {
        // Creating objects of the Car class
        Car car1 = new Car("Toyota", "Camry", 2022);
        Car car2 = new Car("Honda", "Accord", 2021);

        // Calling methods on objects
        car1.displayInfo();
        car2.displayInfo();
    }
}
```

In this example, two `Car` objects (`car1` and `car2`) are created using the `new` keyword. Methods of the `Car` class are then called on these objects.

## Constructors

A constructor is a special method used for initializing objects. It is called when an object is created.

### Types of Constructors

- **Default Constructor**: Takes no parameters.
- **Parameterized Constructor**: Takes parameters to initialize the object.

```java
public class Book {

    // Default constructor
    public Book() {
        // Initialization code
    }

    // Parameterized constructor
    public Book(String title, String author) {
        // Initialization code using parameters
    }
}
```

## Encapsulation

Encapsulation is the bundling of data and methods that operate on the data within a single unit (class). It helps in controlling access to the data.

```java
public class Student {

    // Private data members
    private String name;
    private int age;

    // Public getter and setter methods
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age > 0) {
            this.age = age;
        }
    }
}
```

In this example, the `name` and `age` data members are private, and access to them is controlled through getter and setter methods.

## Inheritance

Inheritance is a mechanism in OOP that allows a class to inherit properties and behaviors from another class.

```java
// Parent class
class Animal {
    void eat() {
        System.out.println("Animal is eating");
    }
}

// Child class inheriting from Animal
class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking");
    }
}
```

In this example, the `Dog` class inherits the `eat` method from the `Animal` class.

## Summary

- A class is a blueprint for creating objects, encapsulating data and behavior.
- Objects are instances of classes that represent real-world entities.
- Constructors are special methods for initializing objects.
- Encapsulation involves bundling data and methods within a class and controlling access to the data.
- Inheritance allows a class to inherit properties and behaviors from another class.

For more details on classes and objects in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/concepts/index.html).
