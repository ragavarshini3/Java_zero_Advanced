# Access Modifiers in Java

In Java, access modifiers control where a class, variable, method, or constructor can be accessed.

They are important for protecting data and organizing code properly.

For example:

- A bank account balance should not be changed directly.
- A password should not be visible outside the class.
- A student department may be accessible to child classes.
- A college name can be accessed from anywhere.

Java provides four access modifiers:

```text
1. public
2. private
3. protected
4. default
```

---

# Why Do We Need Access Modifiers?

Without access modifiers, every variable and method can be accessed and changed by any class.

For example:

```java
class BankAccount
{
    public double balance;
}
```

Now anyone can write:

```java
account.balance = -50000;
```

This is unsafe.

Using `private`, we can protect the balance.

```java
class BankAccount
{
    private double balance;
}
```

Now the balance can be updated only through controlled methods.

---

# Access Modifier Table

| Access Modifier | Same Class | Same Package | Child Class in Different Package | Different Package |
|---|---|---|---|---|
| `public` | Yes | Yes | Yes | Yes |
| `protected` | Yes | Yes | Yes | No |
| `default` | Yes | Yes | No | No |
| `private` | Yes | No | No | No |

---

# 1. public Access Modifier

The `public` access modifier makes a class member accessible from anywhere.

It can be accessed:

- Inside the same class
- Inside the same package
- From another package
- From child classes
- From any Java file

---

# Example 1: public Variable

```java
class Student
{
    public String name = "Ragavarshini";
}

public class Main
{
    public static void main(String[] args)
    {
        Student student = new Student();

        System.out.println(student.name);
    }
}
```

### Output

```text
Ragavarshini
```

---

# Example 2: public Method

```java
class Calculator
{
    public void add(int number1, int number2)
    {
        int result = number1 + number2;

        System.out.println("Sum: " + result);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Calculator calculator = new Calculator();

        calculator.add(10, 20);
    }
}
```

### Output

```text
Sum: 30
```

---

# Real-World Example: College Information

College name is common information and can be public.

```java
class College
{
    public String collegeName = "KGISL Institute of Technology";
}

public class Main
{
    public static void main(String[] args)
    {
        College college = new College();

        System.out.println("College Name: " + college.collegeName);
    }
}
```

### Output

```text
College Name: KGISL Institute of Technology
```

---

# 2. private Access Modifier

The `private` access modifier allows access only inside the same class.

Private variables cannot be accessed directly outside the class.

It is mainly used for:

- Passwords
- Bank balances
- Employee salaries
- Personal details
- Internal application data

---

# Example 1: private Variable

```java
class BankAccount
{
    private double balance = 50000;

    public void displayBalance()
    {
        System.out.println("Balance: ₹" + balance);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        BankAccount account = new BankAccount();

        account.displayBalance();

        // System.out.println(account.balance);
        // Error because balance is private
    }
}
```

### Output

```text
Balance: ₹50000.0
```

---

# Example 2: private Variable with Getter and Setter

```java
class Student
{
    private String name;

    public void setName(String name)
    {
        this.name = name;
    }

    public String getName()
    {
        return name;
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Student student = new Student();

        student.setName("Ragavarshini");

        System.out.println("Student Name: " + student.getName());
    }
}
```

### Output

```text
Student Name: Ragavarshini
```

---

# Real-World Example: Bank Account

A bank should not allow a negative balance.

```java
class BankAccount
{
    private String customerName;
    private double balance;

    public void setCustomerName(String customerName)
    {
        this.customerName = customerName;
    }

    public String getCustomerName()
    {
        return customerName;
    }

    public void deposit(double amount)
    {
        if(amount > 0)
        {
            balance = balance + amount;

            System.out.println("Amount deposited successfully");
        }
        else
        {
            System.out.println("Invalid deposit amount");
        }
    }

    public void withdraw(double amount)
    {
        if(amount > 0 && amount <= balance)
        {
            balance = balance - amount;

            System.out.println("Amount withdrawn successfully");
        }
        else
        {
            System.out.println("Insufficient balance or invalid amount");
        }
    }

    public double getBalance()
    {
        return balance;
    }
}

public class Main
{
    public static void main(String[] args)
    {
        BankAccount account = new BankAccount();

        account.setCustomerName("Rahul");

        account.deposit(10000);

        account.withdraw(2500);

        System.out.println("Customer: " + account.getCustomerName());

        System.out.println("Current Balance: ₹" + account.getBalance());
    }
}
```

### Output

```text
Amount deposited successfully
Amount withdrawn successfully
Customer: Rahul
Current Balance: ₹7500.0
```

---

# 3. default Access Modifier

When no access modifier is written, Java uses the `default` access modifier.

It is also called package-private access.

Default members can be accessed only inside the same package.

---

# Example 1: default Variable

```java
class Student
{
    String department = "AI & DS";
}

public class Main
{
    public static void main(String[] args)
    {
        Student student = new Student();

        System.out.println("Department: " + student.department);
    }
}
```

### Output

```text
Department: AI & DS
```

Here, `department` has default access because no modifier is written.

---

# Example 2: default Method

```java
class Employee
{
    void displayEmployee()
    {
        System.out.println("Employee details displayed");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Employee employee = new Employee();

        employee.displayEmployee();
    }
}
```

### Output

```text
Employee details displayed
```

---

# Real-World Example: Same Package Classes

Suppose both classes are inside the same package.

```java
class Student
{
    String name = "Alice";

    void displayName()
    {
        System.out.println("Student Name: " + name);
    }
}

class StudentDetails
{
    public static void main(String[] args)
    {
        Student student = new Student();

        student.displayName();
    }
}
```

### Output

```text
Student Name: Alice
```

Both classes can access default members because they are in the same package.

---

# 4. protected Access Modifier

The `protected` access modifier allows access:

- Inside the same class
- Inside the same package
- Inside child classes
- Inside child classes in different packages

Protected is mostly used with inheritance.

---

# Example 1: protected Variable

```java
class Person
{
    protected String name = "Ragavarshini";
}

class Student extends Person
{
    void displayName()
    {
        System.out.println("Name: " + name);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Student student = new Student();

        student.displayName();
    }
}
```

### Output

```text
Name: Ragavarshini
```

The `Student` class can access `name` because it inherits from `Person`.

---

# Example 2: protected Method

```java
class Vehicle
{
    protected void start()
    {
        System.out.println("Vehicle started");
    }
}

class Car extends Vehicle
{
    void drive()
    {
        start();

        System.out.println("Car is driving");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Car car = new Car();

        car.drive();
    }
}
```

### Output

```text
Vehicle started
Car is driving
```

---

# Real-World Example: Employee and Manager

A manager is an employee, so the manager can access protected employee details.

```java
class Employee
{
    protected String employeeName;
    protected String department;

    Employee(String employeeName, String department)
    {
        this.employeeName = employeeName;
        this.department = department;
    }
}

class Manager extends Employee
{
    Manager(String employeeName, String department)
    {
        super(employeeName, department);
    }

    void displayManagerDetails()
    {
        System.out.println("Manager Name: " + employeeName);

        System.out.println("Department: " + department);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Manager manager = new Manager(
                "Alice",
                "Software Development");

        manager.displayManagerDetails();
    }
}
```

### Output

```text
Manager Name: Alice
Department: Software Development
```

---

# Complete Real-World Program: Student Management System

This program uses all four access modifiers.

```java
class Student
{
    public String collegeName = "KGISL Institute of Technology";

    private int marks;

    protected String department;

    String rollNumber;

    public Student(String rollNumber, String department)
    {
        this.rollNumber = rollNumber;

        this.department = department;
    }

    public void setMarks(int marks)
    {
        if(marks >= 0 && marks <= 100)
        {
            this.marks = marks;
        }
        else
        {
            System.out.println("Marks must be between 0 and 100");
        }
    }

    public int getMarks()
    {
        return marks;
    }
}

class AIStudent extends Student
{
    AIStudent(String rollNumber, String department)
    {
        super(rollNumber, department);
    }

    void displayDetails()
    {
        System.out.println("College: " + collegeName);

        System.out.println("Roll Number: " + rollNumber);

        System.out.println("Department: " + department);

        System.out.println("Marks: " + getMarks());
    }
}

public class Main
{
    public static void main(String[] args)
    {
        AIStudent student = new AIStudent(
                "23AIB101",
                "AI & DS");

        student.setMarks(92);

        student.displayDetails();
    }
}
```

### Output

```text
College: KGISL Institute of Technology
Roll Number: 23AIB101
Department: AI & DS
Marks: 92
```

---

# Explanation of the Complete Program

| Variable | Access Modifier | Why It Is Used |
|---|---|---|
| `collegeName` | `public` | It can be accessed from anywhere. |
| `marks` | `private` | Marks should be protected and validated. |
| `department` | `protected` | Child classes can access it. |
| `rollNumber` | `default` | It can be accessed inside the same package. |

---

# Access Modifiers for Classes

Top-level classes can use only:

```text
public
default
```

Example:

```java
public class Student
{
}
```

Or:

```java
class Student
{
}
```

Top-level classes cannot use:

```java
private class Student
{
}
```

or:

```java
protected class Student
{
}
```

---

# Access Modifiers for Constructors

Constructors can also use access modifiers.

```java
class Demo
{
    private Demo()
    {
        System.out.println("Private Constructor Called");
    }

    public static void createObject()
    {
        Demo demo = new Demo();
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Demo.createObject();
    }
}
```

### Output

```text
Private Constructor Called
```

A private constructor prevents object creation directly from outside the class.

---

# Common Mistakes

## Mistake 1: Accessing a private Variable Directly

❌ Incorrect:

```java
class User
{
    private String password = "Java123";
}

public class Main
{
    public static void main(String[] args)
    {
        User user = new User();

        // System.out.println(user.password);
    }
}
```

Use a method inside the class instead.

---

## Mistake 2: Making Sensitive Data public

❌ Avoid this:

```java
public String password;
public double balance;
public double salary;
```

Use `private` for sensitive data.

---

## Mistake 3: Thinking protected Means Public

`protected` is not accessible everywhere.

It is accessible:

- Inside the same package
- Inside child classes

---

# public vs private vs protected vs default

| Modifier | Best Use |
|---|---|
| `public` | Data or methods that should be accessible everywhere |
| `private` | Sensitive data such as passwords, salary, and balance |
| `protected` | Data that child classes should access |
| `default` | Data or methods used only inside the same package |

---

# Advantages of Access Modifiers

- Protect sensitive data
- Improve security
- Support encapsulation
- Control access to class members
- Prevent accidental changes
- Improve code organization
- Make large projects easier to maintain

---

# Interview Questions

### What are access modifiers in Java?

Access modifiers control the visibility of classes, variables, methods, and constructors.

---

### What are the four access modifiers in Java?

- `public`
- `private`
- `protected`
- `default`

---

### Which access modifier is the most restrictive?

```java
private
```

---

### Which access modifier is the least restrictive?

```java
public
```

---

### What is default access?

When no access modifier is written, Java provides package-private access.

---

### Can a top-level class be private?

No.

---

### Can a top-level class be protected?

No.

---

### What is protected access?

Protected members can be accessed in the same package and by child classes.

---

# Challenge Exercises

### Challenge 1

Create a `BankAccount` class with a private `balance` variable.

Add methods for:

- Deposit
- Withdraw
- Display Balance

---

### Challenge 2

Create an `Employee` class with:

- Public company name
- Private salary
- Protected department
- Default employee ID

Create a child class called `Manager`.

---

### Challenge 3

Create a `Student` class with private marks.

Allow marks only between 0 and 100.

---

### Challenge 4

Create a `Vehicle` class with a protected `brand` variable.

Create a `Car` class that inherits from `Vehicle` and displays the brand.

---

### Challenge 5

Create a class with a private constructor.

Explain why an object cannot be created directly outside the class.

---

# Summary

- Access modifiers control visibility in Java.
- `public` members can be accessed from anywhere.
- `private` members can be accessed only inside the same class.
- `default` members can be accessed only inside the same package.
- `protected` members can be accessed in the same package and child classes.
- Access modifiers improve security, encapsulation, and code organization.

---

# Conclusion

Access modifiers are important for writing secure and well-organized Java programs. They help developers control how variables, methods, constructors, and classes are accessed. By using `public`, `private`, `protected`, and default access correctly, Java applications become safer, cleaner, and easier to maintain.
