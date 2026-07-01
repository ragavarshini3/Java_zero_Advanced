# Classes and Objects in Java

In the previous lesson, we learned that **Object-Oriented Programming (OOP)** is based on **Classes** and **Objects**.

Every Java program is built around classes, and objects are created from those classes.

Understanding Classes and Objects is the foundation of Object-Oriented Programming.

---

# What is a Class?

A **Class** is a blueprint or template used to create objects.

It defines:

- Properties (Variables)
- Behaviors (Methods)

Think of a class as a design or plan for creating real-world objects.

---

# Real-World Example

Imagine a blueprint of a house.

The blueprint contains:

- Number of rooms
- Kitchen
- Hall
- Bathroom

Using the same blueprint, many houses can be built.

Similarly,

```
Class

↓

Car
```

Many car objects can be created.

---

# What is an Object?

An **Object** is an instance of a class.

An object contains actual values for the variables defined in the class.

Example

```
Class

↓

Car

↓

Objects

↓

BMW

Audi

Tesla
```

Each object has different values but belongs to the same class.

---

# Why Do We Need Classes and Objects?

Without Classes

```
Variables

↓

Methods

↓

No Organization
```

With Classes

```
Student

↓

Name

Roll Number

Department

↓

Methods

Study()

AttendClass()
```

Everything related to a student is stored in one place.

---

# Syntax of a Class

```java
class ClassName
{

}
```

Example

```java
class Student
{

}
```

---

# Syntax of an Object

```java
ClassName objectName = new ClassName();
```

Example

```java
Student student = new Student();
```

---

# Understanding the new Keyword

The **new** keyword creates an object in memory.

Example

```java
Student student = new Student();
```

Memory Representation

```
Heap Memory

+----------------------+
| Student Object       |
| name = null          |
| rollNumber = 0       |
+----------------------+

student

↓

Reference Variable
```

---

# Example 1: Simple Class

```java
class Student
{
    String name;
    int age;
}

public class Main
{

    public static void main(String[] args)
    {

        Student student = new Student();

        student.name = "Ragavarshini";

        student.age = 20;

        System.out.println(student.name);

        System.out.println(student.age);

    }

}
```

### Output

```text
Ragavarshini
20
```

---

# Explanation

Class

```
Student
```

Object

```
student
```

Variables

```
name

age
```

Values

```
Ragavarshini

20
```

---

# Example 2: Multiple Objects

```java
class Student
{
    String name;
    int age;
}

public class Main
{

    public static void main(String[] args)
    {

        Student s1 = new Student();

        Student s2 = new Student();

        s1.name = "Alice";
        s1.age = 20;

        s2.name = "Bob";
        s2.age = 22;

        System.out.println(s1.name);
        System.out.println(s2.name);

    }

}
```

### Output

```text
Alice
Bob
```

---

# Real-World Scenario 1: Student Management System

```java
class Student
{
    String name;
    int rollNumber;
    String department;
}

public class Main
{

    public static void main(String[] args)
    {

        Student student = new Student();

        student.name = "Ragavarshini";

        student.rollNumber = 101;

        student.department = "AI & DS";

        System.out.println(student.name);

        System.out.println(student.department);

    }

}
```

---

# Real-World Scenario 2: Banking System

```java
class BankAccount
{
    String customerName;
    double balance;
}

public class Main
{

    public static void main(String[] args)
    {

        BankAccount account = new BankAccount();

        account.customerName = "Rahul";

        account.balance = 50000;

        System.out.println(account.customerName);

        System.out.println(account.balance);

    }

}
```

---

# Real-World Scenario 3: Car

```java
class Car
{
    String brand;
    String color;
    int speed;
}

public class Main
{

    public static void main(String[] args)
    {

        Car car = new Car();

        car.brand = "Tesla";

        car.color = "White";

        car.speed = 180;

        System.out.println(car.brand);

        System.out.println(car.color);

    }

}
```

---

# Real-World Scenario 4: Mobile Phone

```java
class Mobile
{
    String brand;
    String model;
    double price;
}

public class Main
{

    public static void main(String[] args)
    {

        Mobile phone = new Mobile();

        phone.brand = "Samsung";

        phone.model = "Galaxy S24";

        phone.price = 79999;

        System.out.println(phone.brand);

        System.out.println(phone.model);

        System.out.println(phone.price);

    }

}
```

---

# Object Memory Representation

Suppose

```java
Student s1 = new Student();

Student s2 = new Student();
```

Memory

```
Heap

+----------------+
| Student Object |
+----------------+
↑
s1

+----------------+
| Student Object |
+----------------+
↑
s2
```

Each object occupies separate memory.

---

# Class vs Object

| Class | Object |
|--------|--------|
| Blueprint | Instance |
| Logical entity | Physical entity |
| No memory allocated | Memory allocated |
| Created once | Created many times |

---

# Advantages of Classes and Objects

- Better organization
- Code reusability
- Easy maintenance
- Real-world modeling
- Supports OOP concepts
- Improves scalability

---

# Common Mistakes

## Forgetting the new Keyword

❌ Incorrect

```java
Student student;
```

No object is created.

---

## Correct

```java
Student student = new Student();
```

---

## Accessing Variables Without an Object

❌ Incorrect

```java
Student.name = "John";
```

---

## Correct

```java
student.name = "John";
```

---

# Real-World Applications

Classes and Objects are used in:

- Banking Systems
- Hospital Management Systems
- School Management Systems
- E-Commerce Applications
- Airline Reservation Systems
- Robotics
- Artificial Intelligence
- Android Apps
- Desktop Applications
- Enterprise Software

---

# Interview Questions

### What is a Class?

A blueprint used to create objects.

---

### What is an Object?

An instance of a class.

---

### Which keyword creates an object?

```java
new
```

---

### Where are objects stored?

Heap Memory.

---

### Can one class create multiple objects?

Yes.

---

# Challenge Exercises

### Challenge 1

Create a class called Employee with:

- employeeId
- employeeName
- salary

Create two objects and display their details.

---

### Challenge 2

Create a class called Book with:

- title
- author
- price

Create three book objects.

---

### Challenge 3

Create a class called Laptop with:

- brand
- processor
- RAM

Display the specifications.

---

### Challenge 4

Create a class called BankAccount with:

- accountNumber
- customerName
- balance

Display account details.

---

### Challenge 5

Create a class called Car and create five different car objects.

---

# Summary

- A Class is a blueprint.
- An Object is an instance of a class.
- Objects are created using the `new` keyword.
- Each object has its own data.
- Classes and Objects form the foundation of Object-Oriented Programming.

---

# Conclusion

Classes and Objects are the core building blocks of Java. They allow developers to represent real-world entities in software by combining data and behavior into a single unit. Mastering Classes and Objects is essential before learning constructors, inheritance, polymorphism, encapsulation, and other advanced OOP concepts.
