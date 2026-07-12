# Constructors in Java

In the previous lesson, we learned how to create Classes and Objects.

Whenever we create an object, we usually want to initialize its data immediately.

For example:

- Set a student's name
- Set an employee's salary
- Set a bank account numbers
- Set a car's brand

Instead of assigning values one by one after creating the object, Java provides **Constructors**.

Constructors automatically initialize objects when they are created.

---

# What is a Constructor?

A **Constructor** is a special method that is automatically called when an object is created.

Its primary purpose is to initialize object data.

Unlike normal methods, constructors do not have a return type.

---

# Real-World Example

Imagine buying a new mobile phone.

As soon as you switch it on, it already has:

- Default settings
- Language
- Date and Time
- Basic applications

These settings are initialized automatically.

Similarly, constructors initialize objects automatically.

---

# Why Do We Need Constructors?

Without Constructor

```java
Student student = new Student();

student.name = "Ragavarshini";
student.age = 20;
student.department = "AI & DS";
```

Every object needs separate assignments.

With Constructor

```java
Student student = new Student(
        "Ragavarshini",
        20,
        "AI & DS");
```

Everything is initialized in one step.

---

# Characteristics of Constructors

- Constructor name must be the same as the class name.
- Constructors do not have a return type.
- Constructors are automatically called.
- Constructors are used for object initialization.
- Constructors can be overloaded.

---

# Syntax

```java
class Student
{

    Student()
    {

    }

}
```

---

# Example 1: Default Constructor

```java
class Student
{

    Student()
    {
        System.out.println("Constructor Called");
    }

}

public class Main
{

    public static void main(String[] args)
    {

        Student student = new Student();

    }

}
```

### Output

```text
Constructor Called
```

---

# Explanation

When the object is created,

```java
new Student();
```

Java automatically calls

```java
Student()
```

---

# Default Constructor

If we don't create any constructor,

Java automatically creates one.

Example

```java
class Student
{

}
```

Java internally creates

```java
Student()
{

}
```

This is called the **Default Constructor**.

---

# Example 2: Parameterized Constructor

```java
class Student
{

    String name;
    int age;

    Student(String name, int age)
    {
        this.name = name;
        this.age = age;
    }

}

public class Main
{

    public static void main(String[] args)
    {

        Student student =
                new Student("Ragavarshini",20);

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

# Real-World Scenario 1: Student Management System

```java
class Student
{

    String name;
    int rollNumber;

    Student(String name,
            int rollNumber)
    {

        this.name = name;

        this.rollNumber = rollNumber;

    }

}

public class Main
{

    public static void main(String[] args)
    {

        Student student =
                new Student("Rahul",101);

        System.out.println(student.name);

        System.out.println(student.rollNumber);

    }

}
```

---

# Real-World Scenario 2: Banking Application

```java
class BankAccount
{

    String customerName;
    double balance;

    BankAccount(String customerName,
                double balance)
    {

        this.customerName = customerName;

        this.balance = balance;

    }

}

public class Main
{

    public static void main(String[] args)
    {

        BankAccount account =
                new BankAccount("Alice",50000);

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

    Car(String brand,
        String color)
    {

        this.brand = brand;

        this.color = color;

    }

}

public class Main
{

    public static void main(String[] args)
    {

        Car car =
                new Car("Tesla","White");

        System.out.println(car.brand);

        System.out.println(car.color);

    }

}
```

---

# Constructor Overloading

A class can have multiple constructors.

Example

```java
class Student
{

    Student()
    {
        System.out.println("Default Constructor");
    }

    Student(String name)
    {
        System.out.println(name);
    }

}
```

---

# Example

```java
public class Main
{

    public static void main(String[] args)
    {

        Student s1 = new Student();

        Student s2 = new Student("Ragavarshini");

    }

}
```

### Output

```text
Default Constructor

Ragavarshini
```

---

# Constructor vs Method

| Constructor | Method |
|-------------|--------|
| Same name as class | Any valid name |
| No return type | Has return type |
| Called automatically | Called explicitly |
| Initializes objects | Performs tasks |

---

# Common Mistakes

## Giving Return Type

❌ Incorrect

```java
void Student()
{

}
```

This becomes a method, not a constructor.

---

## Wrong Constructor Name

❌ Incorrect

```java
class Student
{

    StudentDetails()
    {

    }

}
```

Constructor name must match the class name.

---

# Advantages of Constructors

- Automatic object initialization
- Cleaner code
- Reduces repetitive assignments
- Improves readability
- Supports constructor overloading

---

# Real-World Applications

Constructors are used in:

- Banking Systems
- Student Management Systems
- Hospital Management Systems
- E-Commerce Applications
- Robotics
- Artificial Intelligence
- Android Applications
- Desktop Applications
- Enterprise Software
- Game Development

---

# Interview Questions

### What is a Constructor?

A special method used to initialize objects.

---

### Can Constructors have a return type?

No.

---

### When is a Constructor called?

Automatically when an object is created.

---

### Can Constructors be overloaded?

Yes.

---

### What is a Default Constructor?

A constructor automatically provided by Java when no constructor is defined.

---

# Challenge Exercises

### Challenge 1

Create a Student class with a parameterized constructor.

---

### Challenge 2

Create an Employee class with:

- employeeId
- employeeName
- salary

Initialize values using a constructor.

---

### Challenge 3

Create a Book class with constructor overloading.

---

### Challenge 4

Create a BankAccount class with a constructor that initializes account details.

---

### Challenge 5

Create a Car class with two constructors:

- Default Constructor
- Parameterized Constructor

---

# Summary

- Constructors initialize objects.
- Constructors have the same name as the class.
- Constructors do not have a return type.
- Constructors are automatically called when objects are created.
- Constructors can be overloaded.

---

# Conclusion

Constructors are an essential feature of Java that simplify object initialization. They ensure that every object starts with meaningful values, making programs cleaner, safer, and easier to maintain. Constructors are used extensively in real-world Java applications, from banking systems to enterprise software and Android development.
