# The `this` Keyword in Java

In the previous lesson, we learned about constructors.

Sometimes, the constructor parameters and instance variables have the same name.

For example:

- Student Name
- Employee Salary
- Bank Balance
- Product Price

In such situations, Java cannot distinguish between the local variable (parameter) and the instance variable.

To solve this problem, Java provides the **`this` keyword**.

---

# What is the `this` Keyword?

The **`this` keyword** is a reference variable that refers to the **current object**.

It is used to access the current object's variables, methods, and constructors.

---

# Why Do We Need the `this` Keyword?

Consider the following example.

```java
class Student
{
    String name;

    Student(String name)
    {
        name = name;
    }
}
```

Here,

Both variables are named **name**.

The constructor parameter hides the instance variable.

Therefore,

```java
name = name;
```

does nothing.

To solve this,

```java
this.name = name;
```

---

# Syntax

```java
this.variableName
```

Example

```java
this.name = name;
```

---

# How `this` Works

```
Current Object

↓

this

↓

Instance Variables

↓

Instance Methods

↓

Constructors
```

---

# Example 1: Accessing Instance Variable

```java
class Student
{

    String name;

    Student(String name)
    {
        this.name = name;
    }

    void display()
    {
        System.out.println(name);
    }

}

public class Main
{

    public static void main(String[] args)
    {

        Student student =
                new Student("Ragavarshini");

        student.display();

    }

}
```

### Output

```text
Ragavarshini
```

---

# Explanation

```
Constructor Parameter

↓

name

Instance Variable

↓

this.name

Assignment

↓

this.name = name
```

---

# Example 2: Employee Details

```java
class Employee
{

    String employeeName;
    double salary;

    Employee(String employeeName,
             double salary)
    {

        this.employeeName = employeeName;

        this.salary = salary;

    }

    void display()
    {

        System.out.println(employeeName);

        System.out.println(salary);

    }

}

public class Main
{

    public static void main(String[] args)
    {

        Employee employee =
                new Employee("Alice",45000);

        employee.display();

    }

}
```

### Output

```text
Alice
45000.0
```

---

# Using `this` to Call a Method

The current object's method can also be called using `this`.

Example

```java
class Demo
{

    void display()
    {
        System.out.println("Hello Java");
    }

    void show()
    {
        this.display();
    }

}

public class Main
{

    public static void main(String[] args)
    {

        Demo demo = new Demo();

        demo.show();

    }

}
```

### Output

```text
Hello Java
```

---

# Using `this()` to Call Another Constructor

One constructor can call another constructor using `this()`.

This is called **Constructor Chaining**.

---

# Example

```java
class Student
{

    Student()
    {
        this("Ragavarshini");
    }

    Student(String name)
    {
        System.out.println(name);
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
Ragavarshini
```

---

# Rules for Constructor Chaining

- `this()` must be the first statement.
- Only one constructor can be called.
- Avoid infinite constructor calls.

Correct

```java
Student()
{
    this("Java");
}
```

Incorrect

```java
Student()
{
    System.out.println("Hello");

    this("Java");
}
```

Compilation Error

---

# Returning the Current Object

Methods can return the current object using `this`.

Example

```java
class Student
{

    Student display()
    {
        return this;
    }

}
```

---

# Method Chaining Using `this`

```java
class Student
{

    Student show()
    {
        System.out.println("Show");

        return this;
    }

    Student display()
    {
        System.out.println("Display");

        return this;
    }

}

public class Main
{

    public static void main(String[] args)
    {

        Student student = new Student();

        student.show().display();

    }

}
```

### Output

```text
Show
Display
```

---

# Real-World Scenario 1: Banking System

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

    void display()
    {

        System.out.println(customerName);

        System.out.println(balance);

    }

}

public class Main
{

    public static void main(String[] args)
    {

        BankAccount account =
                new BankAccount("Rahul",75000);

        account.display();

    }

}
```

---

# Real-World Scenario 2: Online Shopping

```java
class Product
{

    String productName;
    double price;

    Product(String productName,
            double price)
    {

        this.productName = productName;

        this.price = price;

    }

    void display()
    {

        System.out.println(productName);

        System.out.println(price);

    }

}

public class Main
{

    public static void main(String[] args)
    {

        Product product =
                new Product("Laptop",65000);

        product.display();

    }

}
```

---

# Real-World Scenario 3: Hospital Management

```java
class Patient
{

    String patientName;
    int age;

    Patient(String patientName,
            int age)
    {

        this.patientName = patientName;

        this.age = age;

    }

    void display()
    {

        System.out.println(patientName);

        System.out.println(age);

    }

}

public class Main
{

    public static void main(String[] args)
    {

        Patient patient =
                new Patient("John",32);

        patient.display();

    }

}
```

---

# Uses of `this`

The `this` keyword is commonly used to:

- Refer to the current object's instance variables.
- Call another method of the current object.
- Call another constructor in the same class.
- Return the current object.
- Enable method chaining.

---

# `this` vs Local Variable

| Local Variable | `this` Keyword |
|---------------|----------------|
| Belongs to the method | Refers to the current object |
| Exists only during method execution | Exists as long as the object exists |
| Cannot access object members directly | Can access instance variables and methods |

---

# Common Mistakes

## Forgetting `this`

❌ Incorrect

```java
Student(String name)
{
    name = name;
}
```

The instance variable is not initialized.

---

## Correct

```java
Student(String name)
{
    this.name = name;
}
```

---

## Calling `this()` Incorrectly

❌ Incorrect

```java
Student()
{
    System.out.println("Hello");

    this("Java");
}
```

---

## Correct

```java
Student()
{
    this("Java");
}
```

---

# Real-World Applications

The `this` keyword is widely used in:

- Banking Applications
- Student Management Systems
- Hospital Management Systems
- E-Commerce Applications
- Android Development
- Spring Boot Applications
- Enterprise Software
- Robotics
- Artificial Intelligence Projects
- Desktop Applications

---

# Interview Questions

### What is the `this` keyword?

It is a reference variable that refers to the current object.

---

### Why is `this` used?

To distinguish instance variables from local variables.

---

### Can `this` call another constructor?

Yes.

Using

```java
this();
```

---

### Can `this` be returned from a method?

Yes.

```java
return this;
```

---

### Can `this` be used inside static methods?

No.

Static methods belong to the class, not to an object.

---

# Challenge Exercises

### Challenge 1

Create a Student class using the `this` keyword.

---

### Challenge 2

Create an Employee class and initialize all variables using `this`.

---

### Challenge 3

Create constructor chaining using `this()`.

---

### Challenge 4

Create a Product class and return the current object.

---

### Challenge 5

Create a program demonstrating method chaining using `this`.

---

# Summary

- `this` refers to the current object.
- It resolves naming conflicts between instance variables and parameters.
- `this()` is used for constructor chaining.
- `this` can call methods and return the current object.
- It is one of the most frequently used keywords in Java OOP.

---

# Conclusion

The `this` keyword is an essential part of Java Object-Oriented Programming. It helps access the current object's members, supports constructor chaining, enables method chaining, and improves code readability. Mastering the `this` keyword is crucial for writing clean, maintainable, and professional Java applications.
