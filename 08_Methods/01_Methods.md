# Methods in Java

As programs become larger and more complex, writing all the code inside the `main()` method makes it difficult to read, understand, and maintain.

To solve this problem, Java provides **Methods**.

Methods help developers divide a large program into smaller, reusable blocks of code.

Methods improve code readability, reduce duplication, and make programs easier to maintain.

---

# What is a Method?

A **Method** is a block of code that performs a specific task.

Instead of writing the same code multiple times, we can write it once inside a method and call it whenever needed.

Think of a method as a machine that accepts some input, performs a task, and returns an output.

---

# Real-World Example

Imagine a calculator.

It performs operations like:

- Addition
- Subtraction
- Multiplication
- Division

Each operation can be written as a separate method.

Similarly,

An ATM has methods such as:

- Check Balance
- Deposit Money
- Withdraw Money
- Print Receipt

---

# Why Do We Need Methods?

Without methods:

```java
System.out.println("Welcome");

System.out.println("Welcome");

System.out.println("Welcome");

System.out.println("Welcome");
```

This repeats the same code.

Using a method:

```java
displayMessage();

displayMessage();

displayMessage();
```

The code becomes cleaner and reusable.

---

# Advantages of Methods

- Code Reusability
- Reduces Duplicate Code
- Easy Maintenance
- Improves Readability
- Easier Debugging
- Modular Programming

---

# Syntax of a Method

```java
accessModifier returnType methodName()
{
    // code
}
```

---

# Parts of a Method

```java
public static void display()
{
    System.out.println("Hello Java");
}
```

| Part | Description |
|------|-------------|
| public | Access Modifier |
| static | Belongs to the class |
| void | No return value |
| display | Method Name |
| () | Parameters |
| {} | Method Body |

---

# How Methods Work

```text
Program Starts
      ↓
main() Method
      ↓
Calls display()
      ↓
display() Executes
      ↓
Returns to main()
      ↓
Program Ends
```

---

# Example 1: Simple Method

```java
public class MethodExample {

    static void display()
    {
        System.out.println("Welcome to Java");
    }

    public static void main(String[] args)
    {
        display();
    }

}
```

### Output

```text
Welcome to Java
```

---

# Explanation

The `main()` method calls the `display()` method.

The `display()` method executes and prints the message.

Control returns back to the `main()` method.

---

# Example 2: Calling a Method Multiple Times

```java
public class Welcome {

    static void welcome()
    {
        System.out.println("Welcome Student");
    }

    public static void main(String[] args)
    {

        welcome();

        welcome();

        welcome();

    }

}
```

### Output

```text
Welcome Student

Welcome Student

Welcome Student
```

---

# Real-World Scenario 1: ATM Machine

An ATM has different operations.

```java
public class ATM {

    static void checkBalance()
    {
        System.out.println("Available Balance : ₹50,000");
    }

    public static void main(String[] args)
    {

        checkBalance();

    }

}
```

### Output

```text
Available Balance : ₹50,000
```

---

# Real-World Scenario 2: Student Management System

```java
public class Student {

    static void studentDetails()
    {
        System.out.println("Name : Ragavarshini");
        System.out.println("Department : AI & DS");
    }

    public static void main(String[] args)
    {

        studentDetails();

    }

}
```

### Output

```text
Name : Ragavarshini

Department : AI & DS
```

---

# Real-World Scenario 3: Banking Application

```java
public class Banking {

    static void displayAccount()
    {
        System.out.println("Savings Account");
    }

    public static void main(String[] args)
    {

        displayAccount();

    }

}
```

---

# Real-World Scenario 4: Online Shopping

```java
public class Shopping {

    static void displayProduct()
    {
        System.out.println("Product : Laptop");
        System.out.println("Price : ₹65,000");
    }

    public static void main(String[] args)
    {

        displayProduct();

    }

}
```

---

# Calling Multiple Methods

```java
public class Demo {

    static void welcome()
    {
        System.out.println("Welcome");
    }

    static void goodbye()
    {
        System.out.println("Thank You");
    }

    public static void main(String[] args)
    {

        welcome();

        goodbye();

    }

}
```

### Output

```text
Welcome

Thank You
```

---

# Method Naming Rules

✔ Use meaningful names.

Examples:

```text
calculateSalary()

displayStudent()

withdrawMoney()

loginUser()

printInvoice()
```

Avoid names like:

```text
abc()

xyz()

test()
```

---

# Common Mistakes

## Mistake 1

Calling a method that doesn't exist.

❌ Incorrect

```java
display();
```

without creating

```java
display()
```

---

## Mistake 2

Incorrect spelling.

```java
display();

Display();
```

Java is case-sensitive.

---

# Difference Between Method Call and Method Definition

Method Definition

```java
static void display()
{
    System.out.println("Hello");
}
```

Method Call

```java
display();
```

---

# Real-World Applications

Methods are used in:

- Banking Systems
- Hospital Management
- ATM Software
- Inventory Systems
- Student Management
- Payroll Systems
- Robotics Applications
- Web Development
- Android Applications
- AI and Machine Learning Projects

---

# Mini Project

## Employee Information

```java
public class Employee {

    static void employeeDetails()
    {
        System.out.println("Employee ID : 101");
        System.out.println("Employee Name : Alice");
        System.out.println("Department : HR");
    }

    public static void main(String[] args)
    {

        employeeDetails();

    }

}
```

### Output

```text
Employee ID : 101

Employee Name : Alice

Department : HR
```

---

# Challenge Exercises

### Challenge 1

Create a method to display your name.

---

### Challenge 2

Create a method to display your college details.

---

### Challenge 3

Create a method to display today's date.

---

### Challenge 4

Create separate methods for:

- Login
- Logout
- Registration

---

### Challenge 5

Create methods for:

- Addition
- Subtraction
- Multiplication
- Division

---

# Summary

- A method is a reusable block of code.
- Methods improve readability and reduce code duplication.
- A method is defined once and can be called multiple times.
- Java programs become modular and maintainable using methods.

---

# Conclusion

Methods are one of the most fundamental concepts in Java programming. They allow developers to organize code into reusable and manageable units. Every real-world Java application—from banking software and web applications to robotics and AI systems—relies heavily on methods to build scalable and maintainable software.
