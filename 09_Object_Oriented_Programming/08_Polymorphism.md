# Polymorphism in Java

In real-world applications, the same action can behave differently depending on the object performing it.

For example:

- A person can make a payment using cash, card, or UPI.
- Different vehicles start in different ways.
- Different animals make different sounds.
- Different employees may calculate salary differently.

Java supports this flexibility through **Polymorphism**.

Polymorphism is one of the four main pillars of Object-Oriented Programming.

---

# What is Polymorphism?

The word **Polymorphism** comes from two words:

```text
Poly = Many

Morphism = Forms
```

So, polymorphism means:

```text
One Name

↓

Many Forms
```

In Java, the same method name can perform different actions depending on the situation.

---

# Real-World Example

Consider the action:

```text
Payment
```

A payment can happen through:

```text
Cash Payment

Card Payment

UPI Payment

Net Banking Payment
```

The action is the same: payment.

But the implementation is different.

This is similar to polymorphism in Java.

---

# Types of Polymorphism in Java

Java supports two main types of polymorphism.

```text
1. Compile-Time Polymorphism

2. Run-Time Polymorphism
```

---

# 1. Compile-Time Polymorphism

Compile-time polymorphism is achieved using:

```text
Method Overloading
```

The compiler decides which method to call based on the number, type, or order of arguments.

---

# Example: Method Overloading

```java
public class Calculator
{
    static int add(int a, int b)
    {
        return a + b;
    }

    static int add(int a, int b, int c)
    {
        return a + b + c;
    }

    public static void main(String[] args)
    {
        System.out.println(add(10, 20));

        System.out.println(add(10, 20, 30));
    }
}
```

### Output

```text
30
60
```

---

# Explanation

The method name is the same:

```text
add()
```

But the parameters are different.

```text
add(int, int)

add(int, int, int)
```

The compiler selects the correct method before the program runs.

---

# 2. Run-Time Polymorphism

Run-time polymorphism is achieved using:

```text
Method Overriding
```

The method that runs is decided while the program is running.

It usually happens when a parent class reference points to a child class object.

---

# Basic Example of Run-Time Polymorphism

```java
class Animal
{
    void sound()
    {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal
{
    void sound()
    {
        System.out.println("Dog barks");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Animal animal = new Dog();

        animal.sound();
    }
}
```

### Output

```text
Dog barks
```

---

# Explanation

```java
Animal animal = new Dog();
```

Here:

```text
Reference Type = Animal

Object Type = Dog
```

Even though the reference is `Animal`, Java runs the `Dog` version of `sound()` because the actual object is a `Dog`.

This is called **Dynamic Method Dispatch**.

---

# Method Overloading vs Method Overriding

| Method Overloading | Method Overriding |
|---|---|
| Same class | Parent and child classes |
| Same method name | Same method name |
| Different parameters | Same parameters |
| Compile-time polymorphism | Run-time polymorphism |
| Decided by compiler | Decided during execution |

---

# Real-World Scenario 1: Vehicle Start System

Different vehicles start differently.

```java
class Vehicle
{
    void start()
    {
        System.out.println("Vehicle is starting");
    }
}

class Car extends Vehicle
{
    void start()
    {
        System.out.println("Car starts using a key or button");
    }
}

class Bike extends Vehicle
{
    void start()
    {
        System.out.println("Bike starts using a self-start button");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Vehicle vehicle1 = new Car();
        Vehicle vehicle2 = new Bike();

        vehicle1.start();
        vehicle2.start();
    }
}
```

### Output

```text
Car starts using a key or button
Bike starts using a self-start button
```

---

# Real-World Scenario 2: Payment System

An e-commerce application can support different payment methods.

```java
class Payment
{
    void pay()
    {
        System.out.println("Processing payment");
    }
}

class CardPayment extends Payment
{
    void pay()
    {
        System.out.println("Payment completed using card");
    }
}

class UpiPayment extends Payment
{
    void pay()
    {
        System.out.println("Payment completed using UPI");
    }
}

class CashPayment extends Payment
{
    void pay()
    {
        System.out.println("Payment completed using cash");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Payment payment1 = new CardPayment();
        Payment payment2 = new UpiPayment();
        Payment payment3 = new CashPayment();

        payment1.pay();
        payment2.pay();
        payment3.pay();
    }
}
```

### Output

```text
Payment completed using card
Payment completed using UPI
Payment completed using cash
```

---

# Real-World Scenario 3: Employee Salary

Different employee types may calculate salary differently.

```java
class Employee
{
    void calculateSalary()
    {
        System.out.println("Calculating employee salary");
    }
}

class FullTimeEmployee extends Employee
{
    void calculateSalary()
    {
        System.out.println("Full-time employee salary: ₹50,000");
    }
}

class PartTimeEmployee extends Employee
{
    void calculateSalary()
    {
        System.out.println("Part-time employee salary: ₹20,000");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Employee employee1 = new FullTimeEmployee();
        Employee employee2 = new PartTimeEmployee();

        employee1.calculateSalary();
        employee2.calculateSalary();
    }
}
```

---

# Real-World Scenario 4: Notification System

A system can send notifications through different channels.

```java
class Notification
{
    void send()
    {
        System.out.println("Sending notification");
    }
}

class EmailNotification extends Notification
{
    void send()
    {
        System.out.println("Sending notification through email");
    }
}

class SmsNotification extends Notification
{
    void send()
    {
        System.out.println("Sending notification through SMS");
    }
}

class PushNotification extends Notification
{
    void send()
    {
        System.out.println("Sending push notification");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Notification notification1 = new EmailNotification();
        Notification notification2 = new SmsNotification();
        Notification notification3 = new PushNotification();

        notification1.send();
        notification2.send();
        notification3.send();
    }
}
```

---

# Why Use Polymorphism?

Polymorphism makes programs more flexible.

Without polymorphism, you may need many `if-else` conditions.

Example without polymorphism:

```java
String paymentType = "UPI";

if(paymentType.equals("UPI"))
{
    System.out.println("UPI payment");
}
else if(paymentType.equals("CARD"))
{
    System.out.println("Card payment");
}
else if(paymentType.equals("CASH"))
{
    System.out.println("Cash payment");
}
```

With polymorphism:

```java
Payment payment = new UpiPayment();

payment.pay();
```

This makes code easier to extend and maintain.

---

# Advantages of Polymorphism

- Improves flexibility
- Reduces complex `if-else` conditions
- Makes code reusable
- Supports loose coupling
- Makes applications easier to maintain
- Helps add new features easily
- Supports scalable software design

---

# Important Rules

- Run-time polymorphism requires inheritance.
- The child method must have the same name and parameters as the parent method.
- The child method cannot reduce the access level of the parent method.
- Static methods are not overridden; they are hidden.
- Constructors cannot be overridden.
- Private methods cannot be overridden.

---

# Parent Reference and Child Object

This is an important concept.

```java
Animal animal = new Dog();
```

The parent reference can access only methods available in the parent class.

```java
animal.sound();
```

This is valid because `sound()` exists in `Animal`.

But this is invalid:

```java
animal.bark();
```

Even though the actual object is `Dog`, the reference type is `Animal`.

---

# Example

```java
class Animal
{
    void eat()
    {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal
{
    void bark()
    {
        System.out.println("Dog is barking");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Animal animal = new Dog();

        animal.eat();

        // animal.bark();
        // Compilation error
    }
}
```

---

# Common Mistakes

## Mistake 1: Different Parameters in Child Method

```java
class Parent
{
    void display()
    {
        System.out.println("Parent");
    }
}

class Child extends Parent
{
    void display(String name)
    {
        System.out.println(name);
    }
}
```

This is not overriding.

It is method overloading.

---

## Mistake 2: Using `==` for Object Type Logic

Avoid writing complex type checks when polymorphism can handle the behavior.

```java
if(payment instanceof UpiPayment)
{
    // ...
}
```

Prefer calling the common method:

```java
payment.pay();
```

---

# Interview Questions

### What is polymorphism?

Polymorphism means one method or object reference can take many forms.

---

### What are the types of polymorphism in Java?

- Compile-time polymorphism
- Run-time polymorphism

---

### Which feature supports compile-time polymorphism?

Method overloading.

---

### Which feature supports run-time polymorphism?

Method overriding.

---

### What is dynamic method dispatch?

It is the process where Java decides which overridden method to execute at run time.

---

### Can constructors be overridden?

No.

---

### Can static methods be overridden?

No. Static methods are hidden, not overridden.

---

# Challenge Exercises

### Challenge 1

Create an `Animal` class with a `sound()` method.

Create `Dog`, `Cat`, and `Cow` classes that override `sound()`.

---

### Challenge 2

Create a `Payment` class with a `pay()` method.

Create child classes for Card, UPI, and Cash payment.

---

### Challenge 3

Create a `Shape` class with an `area()` method.

Create `Circle` and `Rectangle` classes with different implementations.

---

### Challenge 4

Create an `Employee` class with a `calculateSalary()` method.

Create full-time and part-time employee classes.

---

### Challenge 5

Create a notification system using Email, SMS, and Push Notification classes.

---

# Summary

- Polymorphism means one name can have many forms.
- Method overloading provides compile-time polymorphism.
- Method overriding provides run-time polymorphism.
- Run-time polymorphism uses parent references and child objects.
- Polymorphism makes Java programs flexible, reusable, and easier to maintain.

---

# Conclusion

Polymorphism is a powerful OOP concept that allows Java programs to perform the same operation in different ways. It is widely used in real-world applications such as payment systems, notification systems, employee management, vehicle management, and enterprise software. Understanding polymorphism is essential for building scalable and maintainable Java applications.
