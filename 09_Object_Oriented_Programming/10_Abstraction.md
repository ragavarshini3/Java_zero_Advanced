# Abstraction in Java

In real-world applications, users do not need to know every internal process of a system.

For example:

- In an ATM, users can withdraw money without knowing how the bank server verifies the account.
- In a car, drivers can start the engine without knowing how fuel injection works.
- In an online shopping app, users can place an order without knowing how payment processing happens.
- In a mobile phone, users can make calls without understanding the internal network communication.

Showing only the important features and hiding internal implementation details is called **Abstraction**.

Abstraction is one of the four main pillars of Object-Oriented Programming.

---

# What is Abstraction?

**Abstraction** means hiding unnecessary implementation details and showing only the essential features to the user.

In Java, abstraction can be achieved using:

- Abstract Classes
- Interfaces

This file focuses on **Abstract Classes**. Interfaces are covered separately.

---

# Real-World Example

Think about an ATM machine.

A user sees options such as:

```text
Withdraw Money
Check Balance
Deposit Money
Change PIN
```

But the user does not see:

```text
Database connection
Account verification process
Transaction validation
Server communication
Security checks
```

The internal process is hidden.

This is abstraction.

---

# Why Do We Need Abstraction?

Without abstraction, users and developers may need to deal with unnecessary details.

For example, if every payment method exposes its internal logic, the code becomes difficult to understand.

With abstraction:

```text
Payment

↓

pay()
```

Different payment methods can implement the payment process in their own way.

```text
Card Payment

UPI Payment

Cash Payment
```

---

# Abstract Class

An **abstract class** is a class declared using the `abstract` keyword.

An abstract class can contain:

- Abstract methods
- Normal methods
- Variables
- Constructors

However, we cannot create an object directly from an abstract class.

---

# Syntax of an Abstract Class

```java
abstract class ClassName
{
    abstract void methodName();
}
```

Example:

```java
abstract class Animal
{
    abstract void sound();
}
```

---

# Abstract Method

An **abstract method** is a method without a body.

```java
abstract void sound();
```

The child class must provide the method body.

Example:

```java
class Dog extends Animal
{
    @Override
    void sound()
    {
        System.out.println("Dog barks");
    }
}
```

---

# Basic Example

```java
abstract class Animal
{
    abstract void sound();
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

# Why Can't We Create an Object of an Abstract Class?

❌ Incorrect:

```java
Animal animal = new Animal();
```

An abstract class may contain incomplete methods.

For example:

```java
abstract void sound();
```

Java does not know what sound an `Animal` should make.

A specific child class such as `Dog`, `Cat`, or `Cow` must define the behavior.

---

# Correct Way

```java
Animal animal = new Dog();

animal.sound();
```

### Output

```text
Dog barks
```

---

# Abstract Class with Normal Method

An abstract class can also contain normal methods with a body.

```java
abstract class Animal
{
    abstract void sound();

    void eat()
    {
        System.out.println("Animal is eating");
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

        dog.eat();
    }
}
```

### Output

```text
Dog barks
Animal is eating
```

---

# Real-World Scenario 1: Payment System

Different payment methods follow different processes.

```java
abstract class Payment
{
    abstract void pay(double amount);

    void paymentMessage()
    {
        System.out.println("Payment process started");
    }
}

class CardPayment extends Payment
{
    @Override
    void pay(double amount)
    {
        System.out.println("Paid ₹" + amount + " using Card");
    }
}

class UpiPayment extends Payment
{
    @Override
    void pay(double amount)
    {
        System.out.println("Paid ₹" + amount + " using UPI");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Payment payment1 = new CardPayment();
        Payment payment2 = new UpiPayment();

        payment1.paymentMessage();
        payment1.pay(1500);

        payment2.paymentMessage();
        payment2.pay(2500);
    }
}
```

### Output

```text
Payment process started
Paid ₹1500.0 using Card
Payment process started
Paid ₹2500.0 using UPI
```

---

# Real-World Scenario 2: Vehicle System

Every vehicle can start, but the starting process may differ.

```java
abstract class Vehicle
{
    abstract void start();

    void stop()
    {
        System.out.println("Vehicle stopped");
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
        Vehicle car = new Car();
        Vehicle bike = new Bike();

        car.start();
        car.stop();

        bike.start();
        bike.stop();
    }
}
```

---

# Real-World Scenario 3: Employee Salary System

Different employee types may calculate salary differently.

```java
abstract class Employee
{
    String name;

    Employee(String name)
    {
        this.name = name;
    }

    abstract double calculateSalary();
}

class FullTimeEmployee extends Employee
{
    FullTimeEmployee(String name)
    {
        super(name);
    }

    @Override
    double calculateSalary()
    {
        return 50000;
    }
}

class PartTimeEmployee extends Employee
{
    PartTimeEmployee(String name)
    {
        super(name);
    }

    @Override
    double calculateSalary()
    {
        return 20000;
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Employee employee1 = new FullTimeEmployee("Alice");
        Employee employee2 = new PartTimeEmployee("Bob");

        System.out.println(
                employee1.name + " Salary: ₹" +
                employee1.calculateSalary());

        System.out.println(
                employee2.name + " Salary: ₹" +
                employee2.calculateSalary());
    }
}
```

### Output

```text
Alice Salary: ₹50000.0
Bob Salary: ₹20000.0
```

---

# Real-World Scenario 4: Online Shopping Delivery

Different delivery services can deliver orders differently.

```java
abstract class Delivery
{
    abstract void deliver(String productName);

    void orderConfirmed()
    {
        System.out.println("Order confirmed");
    }
}

class StandardDelivery extends Delivery
{
    @Override
    void deliver(String productName)
    {
        System.out.println(productName + " will arrive in 5 days");
    }
}

class ExpressDelivery extends Delivery
{
    @Override
    void deliver(String productName)
    {
        System.out.println(productName + " will arrive tomorrow");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Delivery delivery1 = new StandardDelivery();
        Delivery delivery2 = new ExpressDelivery();

        delivery1.orderConfirmed();
        delivery1.deliver("Laptop");

        delivery2.orderConfirmed();
        delivery2.deliver("Mobile Phone");
    }
}
```

---

# Rules of Abstract Classes

- An abstract class is declared using the `abstract` keyword.
- An abstract class cannot be instantiated directly.
- An abstract class can have abstract and normal methods.
- A child class must implement all abstract methods.
- If a child class does not implement all abstract methods, it must also be declared `abstract`.
- Abstract classes can have constructors.
- Abstract classes can have variables.
- Abstract methods cannot have a body.
- Abstract methods cannot be `private`, `final`, or `static`.

---

# Abstract Class with Constructor

Abstract classes can have constructors.

The constructor runs when a child object is created.

```java
abstract class Person
{
    Person()
    {
        System.out.println("Person constructor called");
    }

    abstract void display();
}

class Student extends Person
{
    @Override
    void display()
    {
        System.out.println("Student details displayed");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Student student = new Student();

        student.display();
    }
}
```

### Output

```text
Person constructor called
Student details displayed
```

---

# Abstract Class vs Normal Class

| Abstract Class | Normal Class |
|---|---|
| Can contain abstract methods | Cannot contain abstract methods |
| Cannot create object directly | Can create objects directly |
| May contain incomplete behavior | Contains complete behavior |
| Used as a base class | Used for normal object creation |

---

# Abstraction vs Encapsulation

| Abstraction | Encapsulation |
|---|---|
| Hides implementation details | Hides and protects data |
| Focuses on what an object does | Focuses on how data is accessed |
| Achieved using abstract classes and interfaces | Achieved using private variables and getter/setter methods |
| Example: ATM operations | Example: private bank balance |

---

# Common Mistakes

## Creating an Object of an Abstract Class

❌ Incorrect:

```java
Vehicle vehicle = new Vehicle();
```

Abstract classes cannot be instantiated.

---

## Forgetting to Implement an Abstract Method

```java
abstract class Animal
{
    abstract void sound();
}

class Dog extends Animal
{
    // Error because sound() is not implemented
}
```

Correct:

```java
class Dog extends Animal
{
    @Override
    void sound()
    {
        System.out.println("Dog barks");
    }
}
```

---

## Adding a Body to an Abstract Method

❌ Incorrect:

```java
abstract void display()
{
    System.out.println("Hello");
}
```

Correct:

```java
abstract void display();
```

---

# Advantages of Abstraction

- Hides unnecessary implementation details
- Reduces complexity
- Improves security
- Makes code easier to maintain
- Supports flexible design
- Encourages reusable code
- Helps build large-scale applications

---

# Real-World Applications

Abstraction is used in:

- ATM Systems
- Payment Gateways
- Banking Applications
- E-Commerce Applications
- Hospital Management Systems
- Vehicle Management Systems
- Android Development
- Spring Boot Applications
- AI Applications
- Enterprise Software

---

# Interview Questions

### What is abstraction?

Abstraction is the process of hiding implementation details and showing only essential features.

---

### How is abstraction achieved in Java?

Using abstract classes and interfaces.

---

### Can we create an object of an abstract class?

No.

---

### Can an abstract class have normal methods?

Yes.

---

### Can an abstract class have constructors?

Yes.

---

### Can an abstract method have a body?

No.

---

### Can an abstract class have variables?

Yes.

---

### What is the difference between abstraction and encapsulation?

Abstraction hides implementation details, while encapsulation protects data by controlling access.

---

# Challenge Exercises

### Challenge 1

Create an abstract `Animal` class with an abstract `sound()` method.

Create `Dog`, `Cat`, and `Cow` classes that implement it.

---

### Challenge 2

Create an abstract `Shape` class with an `area()` method.

Create `Circle` and `Rectangle` classes that calculate area differently.

---

### Challenge 3

Create an abstract `Payment` class with a `pay()` method.

Create Card, UPI, and Cash payment classes.

---

### Challenge 4

Create an abstract `Employee` class with a `calculateSalary()` method.

Create full-time and part-time employee classes.

---

### Challenge 5

Create an abstract `Vehicle` class with `start()` and `stop()` methods.

Create `Car` and `Bike` classes.

---

# Summary

- Abstraction hides unnecessary implementation details.
- It shows only essential features to users.
- Abstract classes are declared using the `abstract` keyword.
- Abstract classes cannot be instantiated directly.
- Abstract methods have no body.
- Child classes must implement abstract methods.
- Abstract classes can also contain normal methods, variables, and constructors.

---

# Conclusion

Abstraction is a key Java OOP concept used to reduce complexity and hide internal implementation details. It allows developers to create clean, flexible, and maintainable applications. Abstract classes are widely used in payment systems, banking applications, vehicle systems, employee management, and enterprise software.
