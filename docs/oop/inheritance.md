# Inheritance in Java

Inheritance is a fundamental concept in object-oriented programming (OOP) that allows a class to inherit properties and behaviors from another class. In Java, it promotes code reusability and establishes a relationship between classes. Here, we'll cover the basics of inheritance and provide examples.

## Basics of Inheritance

Inheritance involves creating a new class, called the **subclass** or **derived class**, that inherits attributes and methods from an existing class, called the **superclass** or **base class**. The subclass can extend the functionality of the superclass or override its methods.

### Syntax

```java
// Superclass
class Animal {
    void eat() {
        System.out.println("Animal is eating");
    }
}

// Subclass inheriting from Animal
class Dog extends Animal {
    void bark() {
        System.out.println("Dog is barking");
    }
}
```

In this example, the `Dog` class is the subclass, and it inherits the `eat` method from the `Animal` superclass.

## Types of Inheritance

### Single Inheritance

In single inheritance, a class inherits from only one superclass.

```java
class A {
    // Class A members
}

class B extends A {
    // Class B members
}
```

### Multiple Inheritance (Interface-based)

Java supports multiple inheritance through interfaces. A class can implement multiple interfaces.

```java
interface A {
    // Interface A members
}

interface B {
    // Interface B members
}

class C implements A, B {
    // Class C members
}
```

### Multilevel Inheritance

In multilevel inheritance, a class extends another class, creating a chain of inheritance.

```java
class A {
    // Class A members
}

class B extends A {
    // Class B members
}

class C extends B {
    // Class C members
}
```

## Overriding Methods

Subclasses can override (provide a new implementation for) methods defined in the superclass.

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

## `super` Keyword

The `super` keyword is used to refer to the superclass members (fields or methods) from within the subclass.

```java
class Animal {
    String color = "Brown";
}

class Dog extends Animal {
    String color = "White";

    void displayColors() {
        System.out.println("Dog color: " + color);          // Color from Dog class
        System.out.println("Animal color: " + super.color); // Color from Animal class
    }
}
```

In this example, the `super.color` refers to the `color` field in the `Animal` superclass.

## Summary

- Inheritance is a mechanism in Java that allows a class to inherit properties and behaviors from another class.
- A subclass inherits from a superclass, promoting code reusability and establishing a relationship between classes.
- Types of inheritance include single, multiple (interface-based), and multilevel inheritance.
- Subclasses can override methods from the superclass using the `@Override` annotation.
- The `super` keyword is used to refer to the superclass members from within the subclass.

For more details on inheritance in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/java/IandI/subclasses.html).
