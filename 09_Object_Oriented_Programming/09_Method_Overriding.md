# Method Overriding in Java

In the previous lesson, we learned that polymorphism allows the same method name to behave differently.

One of the most important ways to achieve run-time polymorphism is **Method Overriding**.

Method overriding happens when a child class provides its own version of a method that already exists in the parent class.

---

# What is Method Overriding?

**Method Overriding** occurs when a child class defines a method with the same name, same parameters, and same return type as a method in its parent class.

The child class changes the behavior of the inherited method.

---

# Real-World Example

Consider a payment system.

All payment methods perform payment, but the process differs.

```text
Payment
│
├── Card Payment
├── UPI Payment
└── Cash Payment
```

Each payment method can have its own `pay()` implementation.

---

# Basic Syntax

```java
class Parent
{
    void display()
    {
        System.out.println("Parent Method");
    }
}

class Child extends Parent
{
    @Override
    void display()
    {
        System.out.println("Child Method");
    }
}
```

---

# Example 1: Basic Method Overriding

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
    @Override
    void sound()
    {
        System.out.println("Dog barks");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Dog dog = new Dog();

        dog.sound();
    }
}
```

### Output

```text
Dog barks
```

---

# Explanation

The `Dog` class inherits the `sound()` method from `Animal`.

But `Dog` provides its own version of `sound()`.

Therefore, when `dog.sound()` is called, Java executes:

```text
Dog barks
```

instead of:

```text
Animal makes a sound
```

---

# Using Parent Reference and Child Object

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
    @Override
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

This is called **Run-Time Polymorphism**.

Java decides which method to run based on the actual object created.

---

# Why Use `@Override`?

The `@Override` annotation tells Java that the child method is intended to override a parent method.

```java
@Override
void sound()
{
    System.out.println("Dog barks");
}
```

It helps detect mistakes.

For example, if the method name or parameters are incorrect, Java shows an error.

---

# Example 2: Vehicle System

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
    @Override
    void start()
    {
        System.out.println("Car starts using a button");
    }
}

class Bike extends Vehicle
{
    @Override
    void start()
    {
        System.out.println("Bike starts using self-start");
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
Car starts using a button
Bike starts using self-start
```

---

# Rules for Method Overriding

For a method to be overridden:

- The method name must be the same.
- The parameter list must be the same.
- The return type must be the same or compatible.
- The child class must inherit from the parent class.
- The access level cannot be more restrictive in the child class.
- The method cannot be `private`.
- The method cannot be `final`.
- Constructors cannot be overridden.
- Static methods are hidden, not overridden.

---

# Example: Access Modifier Rule

```java
class Parent
{
    protected void display()
    {
        System.out.println("Parent");
    }
}

class Child extends Parent
{
    @Override
    public void display()
    {
        System.out.println("Child");
    }
}
```

This is valid because `public` is not more restrictive than `protected`.

---

# Invalid Example: Reducing Access Level

```java
class Parent
{
    public void display()
    {
        System.out.println("Parent");
    }
}

class Child extends Parent
{
    // Invalid
    // private void display()
    // {
    //     System.out.println("Child");
    // }
}
```

A child method cannot reduce access from `public` to `private`.

---

# Method Overriding vs Method Overloading

| Method Overriding | Method Overloading |
|---|---|
| Happens between parent and child classes | Happens in the same class |
| Same method name | Same method name |
| Same parameters | Different parameters |
| Run-time polymorphism | Compile-time polymorphism |
| Requires inheritance | Does not require inheritance |

---

# Real-World Scenario 1: Payment System

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
    @Override
    void pay()
    {
        System.out.println("Payment completed using card");
    }
}

class UpiPayment extends Payment
{
    @Override
    void pay()
    {
        System.out.println("Payment completed using UPI");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Payment payment1 = new CardPayment();
        Payment payment2 = new UpiPayment();

        payment1.pay();
        payment2.pay();
    }
}
```

### Output

```text
Payment completed using card
Payment completed using UPI
```

---

# Real-World Scenario 2: Employee Salary System

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
    @Override
    void calculateSalary()
    {
        System.out.println("Full-time employee salary: ₹50,000");
    }
}

class PartTimeEmployee extends Employee
{
    @Override
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

# Real-World Scenario 3: Notification System

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
    @Override
    void send()
    {
        System.out.println("Notification sent through Email");
    }
}

class SmsNotification extends Notification
{
    @Override
    void send()
    {
        System.out.println("Notification sent through SMS");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Notification notification1 = new EmailNotification();
        Notification notification2 = new SmsNotification();

        notification1.send();
        notification2.send();
    }
}
```

---

# Calling Parent Method Using `super`

The `super` keyword can call the parent class version of an overridden method.

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
    @Override
    void sound()
    {
        super.sound();

        System.out.println("Dog barks");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Dog dog = new Dog();

        dog.sound();
    }
}
```

### Output

```text
Animal makes a sound
Dog barks
```

---

# Common Mistakes

## Different Parameters

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

It is method overloading because the parameters are different.

---

## Overriding a Final Method

```java
class Parent
{
    final void display()
    {
        System.out.println("Parent");
    }
}

class Child extends Parent
{
    // Invalid
    // void display()
    // {
    //     System.out.println("Child");
    // }
}
```

A `final` method cannot be overridden.

---

## Overriding a Private Method

```java
class Parent
{
    private void display()
    {
        System.out.println("Parent");
    }
}

class Child extends Parent
{
    void display()
    {
        System.out.println("Child");
    }
}
```

This is not overriding because private methods are not inherited.

---

# Advantages of Method Overriding

- Supports run-time polymorphism
- Makes programs flexible
- Allows child classes to provide specialized behavior
- Reduces complex conditional logic
- Improves code reusability
- Helps build scalable applications

---

# Interview Questions

### What is method overriding?

Method overriding occurs when a child class provides its own version of an inherited parent method.

---

### Which annotation is commonly used for overriding?

```java
@Override
```

---

### Can static methods be overridden?

No. Static methods are hidden, not overridden.

---

### Can constructors be overridden?

No.

---

### Can private methods be overridden?

No.

---

### Can final methods be overridden?

No.

---

### What type of polymorphism does method overriding support?

Run-time polymorphism.

---

# Challenge Exercises

### Challenge 1

Create an `Animal` class with a `sound()` method.

Create `Dog`, `Cat`, and `Cow` classes that override the method.

---

### Challenge 2

Create a `Vehicle` class with a `start()` method.

Create `Car`, `Bike`, and `Bus` classes that override it.

---

### Challenge 3

Create a `Payment` class with a `pay()` method.

Create Card, UPI, and Cash payment classes.

---

### Challenge 4

Create an `Employee` class with a `calculateSalary()` method.

Create full-time and part-time employee classes.

---

### Challenge 5

Create a notification system with Email, SMS, and Push Notification classes using method overriding.

---

# Summary

- Method overriding happens when a child class changes an inherited method.
- The method name and parameters must remain the same.
- Method overriding supports run-time polymorphism.
- Use `@Override` to avoid mistakes.
- Static, private, final methods, and constructors cannot be overridden.
- The `super` keyword can call the parent version of an overridden method.

---

# Conclusion

Method overriding is an essential Java OOP concept used to provide specialized behavior in child classes. It is widely used in payment systems, vehicle systems, employee management, notifications, banking applications, and enterprise software. Understanding method overriding is necessary for mastering run-time polymorphism and building flexible Java applications.
