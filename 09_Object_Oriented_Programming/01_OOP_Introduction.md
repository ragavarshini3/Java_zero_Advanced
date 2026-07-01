# Introduction to Object-Oriented Programming (OOP) in Java

As software applications become larger and more complex, writing all the code in a single file becomes difficult to understand, maintain, and expand.

To solve this problem, Java follows the **Object-Oriented Programming (OOP)** paradigm.

OOP helps developers organize programs into reusable objects and classes, making software modular, secure, scalable, and easier to maintain.

Today, almost every enterprise application, mobile application, banking software, hospital management system, and game is developed using Object-Oriented Programming.

---

# What is Object-Oriented Programming?

**Object-Oriented Programming (OOP)** is a programming approach in which programs are designed using **Objects** and **Classes**.

Instead of focusing only on functions, OOP focuses on real-world entities.

Examples include:

* Student
* Employee
* Car
* Bank Account
* Mobile Phone
* Laptop
* Robot

Each object has:

* Properties (Data)
* Behaviors (Methods)

---

# Real-World Example

Imagine a Car.

A car has:

### Properties (Data)

* Brand
* Model
* Color
* Speed
* Fuel Type

### Behaviors (Actions)

* Start()
* Stop()
* Accelerate()
* Brake()
* Turn()

Similarly, Java represents real-world entities as objects.

---

# Why Do We Need OOP?

Without OOP:

* Programs become lengthy.
* Code duplication increases.
* Maintenance becomes difficult.
* Reusability is low.

With OOP:

* Programs become modular.
* Code is reusable.
* Easy maintenance.
* Better security.
* Easier teamwork.

---

# Procedural Programming vs Object-Oriented Programming

| Procedural Programming | Object-Oriented Programming |
| ---------------------- | --------------------------- |
| Function-based         | Object-based                |
| Focuses on procedures  | Focuses on objects          |
| Less secure            | More secure                 |
| Difficult to maintain  | Easy to maintain            |
| Less reusable          | Highly reusable             |

---

# Basic Concepts of OOP

Object-Oriented Programming is based on four main principles.

```
Object-Oriented Programming

↓

Class

↓

Object

↓

Encapsulation

↓

Inheritance

↓

Polymorphism

↓

Abstraction
```

These are called the **Four Pillars of OOP**.

---

# What is a Class?

A **Class** is a blueprint or template used to create objects.

It defines:

* Variables (Properties)
* Methods (Behaviors)

Example

```
Class

↓

Car
```

---

# What is an Object?

An **Object** is an instance of a class.

Example

```
Class

↓

Car

↓

Object

↓

My Car
```

You can create many objects from one class.

---

# Example

Suppose we have a class:

```
Student
```

Objects

```
Student 1

Student 2

Student 3
```

All belong to the same class but contain different data.

---

# Four Pillars of OOP

## 1. Encapsulation

Combining data and methods into a single unit.

Example

```
Bank Account

↓

Balance

Withdraw()

Deposit()
```

---

## 2. Inheritance

One class acquires properties of another class.

Example

```
Vehicle

↓

Car

Bike

Bus
```

---

## 3. Polymorphism

One method behaves differently in different situations.

Example

```
Shape

↓

Area()

↓

Circle

Rectangle

Triangle
```

---

## 4. Abstraction

Showing only essential details while hiding implementation.

Example

```
ATM Machine

↓

Withdraw Money

↓

Internal Processing Hidden
```

---

# Real-World Scenario 1: Student Management System

Class

```
Student
```

Properties

* Name
* Roll Number
* Department

Methods

* study()
* attendClass()
* writeExam()

Objects

```
Ragavarshini

Rahul

Alice
```

---

# Real-World Scenario 2: Banking System

Class

```
BankAccount
```

Properties

* Account Number
* Balance
* Customer Name

Methods

* Deposit()
* Withdraw()
* CheckBalance()

---

# Real-World Scenario 3: Hospital Management

Class

```
Patient
```

Properties

* Name
* Age
* Disease

Methods

* Admit()
* Discharge()
* GenerateBill()

---

# Real-World Scenario 4: Online Shopping

Class

```
Product
```

Properties

* Product Name
* Price
* Quantity

Methods

* AddToCart()
* BuyNow()
* CalculateDiscount()

---

# Advantages of OOP

* Reusable Code
* Better Security
* Easy Maintenance
* Easy Debugging
* Better Scalability
* Modular Design
* Real-World Modeling
* Faster Development
* Easy Team Collaboration
* Supports Large Projects

---

# Applications of OOP

Object-Oriented Programming is used in:

* Banking Software
* Hospital Management Systems
* School Management Systems
* E-Commerce Applications
* Robotics
* Artificial Intelligence
* Android Applications
* Desktop Applications
* Game Development
* Enterprise Software

---

# Common Mistakes

### Confusing Class and Object

A **Class** is a blueprint.

An **Object** is the actual thing created from the blueprint.

Example

Blueprint → House Plan

Object → Constructed House

---

### Thinking Every Variable is an Object

Primitive data types such as:

```java
int

double

char
```

are not objects.

---

# Interview Questions

### What is OOP?

Object-Oriented Programming is a programming paradigm based on classes and objects.

---

### What are the four pillars of OOP?

* Encapsulation
* Inheritance
* Polymorphism
* Abstraction

---

### What is the difference between a Class and an Object?

A Class is a blueprint.

An Object is an instance of a class.

---

### Why is Java called an Object-Oriented Language?

Because Java organizes programs using classes and objects and supports the four OOP principles.

---

# Challenge Exercises

### Challenge 1

List five real-world objects and identify their properties and behaviors.

---

### Challenge 2

Create a table showing the difference between a Class and an Object.

---

### Challenge 3

Identify the four pillars of OOP in a Banking System.

---

### Challenge 4

Explain how inheritance can be used in a Vehicle Management System.

---

### Challenge 5

Explain abstraction using an ATM Machine.

---

# Summary

* OOP is based on Classes and Objects.
* It models real-world entities in software.
* The four pillars are Encapsulation, Inheritance, Polymorphism, and Abstraction.
* OOP improves reusability, maintainability, and security.
* Java is one of the most widely used Object-Oriented Programming languages.

---

# Conclusion

Object-Oriented Programming is the foundation of modern Java development. By organizing software into classes and objects, developers can create reusable, scalable, and maintainable applications. Understanding OOP is essential before learning advanced Java topics such as inheritance, polymorphism, interfaces, collections, frameworks, and enterprise application development.
