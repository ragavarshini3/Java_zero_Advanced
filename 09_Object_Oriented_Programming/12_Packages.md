# Packages in Java

As Java projects grow, they may contain many classes, interfaces, files, and modules.

For example, a banking application may contain separate classes for:

- Customers
- Accounts
- Transactions
- Loans
- Employees
- Reports

Keeping every class in one folder makes the project difficult to manage.

Java solves this problem using **Packages**.

Packages help organize related classes and interfaces into folders.

---

# What is a Package?

A **Package** is a group of related classes, interfaces, enums, and sub-packages.

It works like a folder on your computer.

For example:

```text
Banking Application
│
├── customers
│   ├── Customer.java
│   └── Account.java
│
├── transactions
│   ├── Deposit.java
│   └── Withdraw.java
│
└── reports
    └── TransactionReport.java
```

Each folder can be a package.

---

# Why Do We Need Packages?

Packages help developers:

- Organize large projects
- Avoid class name conflicts
- Improve code readability
- Control access to classes
- Reuse code easily
- Maintain applications easily

---

# Real-World Example

Imagine a college.

Different departments are separated.

```text
College
│
├── AI & DS Department
├── IT Department
├── ECE Department
└── Mechanical Department
```

Each department contains students, staff, subjects, and labs.

Similarly, packages organize Java classes based on their purpose.

---

# Types of Packages in Java

Java packages are mainly divided into two types.

```text
1. Built-in Packages
2. User-defined Packages
```

---

# 1. Built-in Packages

Java provides many ready-made packages.

Some common built-in packages are:

| Package | Purpose |
|---|---|
| `java.lang` | Basic Java classes such as String, Math, System |
| `java.util` | Collections, Scanner, ArrayList, Date |
| `java.io` | File handling and input/output |
| `java.sql` | Database connectivity |
| `java.net` | Networking |
| `java.time` | Date and time handling |

---

# Example: Using `java.util.Scanner`

```java
import java.util.Scanner;

public class Main
{
    public static void main(String[] args)
    {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your name: ");

        String name = scanner.nextLine();

        System.out.println("Welcome " + name);
    }
}
```

---

# The `java.lang` Package

The `java.lang` package is imported automatically.

For example, you do not need to write:

```java
import java.lang.String;
import java.lang.System;
```

Because Java imports it by default.

---

# 2. User-Defined Packages

A user-defined package is created by the programmer.

For example:

```java
package college;
```

This means the class belongs to the `college` package.

---

# Creating a User-Defined Package

Suppose you want to create a package named `college`.

Create a file named `Student.java`.

```java
package college;

public class Student
{
    public void display()
    {
        System.out.println("Student details displayed");
    }
}
```

The file should be inside a folder named:

```text
college
```

Folder structure:

```text
Project
│
├── college
│   └── Student.java
│
└── Main.java
```

---

# Importing a User-Defined Package

Now create `Main.java`.

```java
import college.Student;

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
Student details displayed
```

---

# Package Naming Convention

Package names should usually be written in lowercase letters.

Examples:

```text
com.company.project

com.bank.accounts

com.college.students

org.example.application
```

Avoid using uppercase letters in package names.

❌ Avoid:

```text
CollegeManagement
```

✅ Better:

```text
collegemanagement
```

---

# Package Naming Using Domain Names

Large companies use reverse domain names to avoid naming conflicts.

For example:

```text
com.google.maps

com.microsoft.office

org.springframework.boot
```

If a company owns:

```text
example.com
```

It may use:

```text
com.example.project
```

---

# Import Statement

The `import` keyword allows a class to use another class from a different package.

Syntax:

```java
import packageName.ClassName;
```

Example:

```java
import java.util.Scanner;
```

---

# Importing All Classes from a Package

```java
import java.util.*;
```

This imports all classes from the `java.util` package.

However, in professional projects, importing only required classes is usually clearer.

Preferred:

```java
import java.util.ArrayList;
import java.util.Scanner;
```

---

# Example: Using Multiple Built-in Classes

```java
import java.util.ArrayList;
import java.util.Scanner;

public class Main
{
    public static void main(String[] args)
    {
        Scanner scanner = new Scanner(System.in);

        ArrayList<String> students = new ArrayList<>();

        System.out.print("Enter student name: ");

        String name = scanner.nextLine();

        students.add(name);

        System.out.println("Student List: " + students);
    }
}
```

---

# Real-World Scenario 1: Banking Application

A banking project can be organized like this:

```text
BankingApplication
│
├── accounts
│   ├── SavingsAccount.java
│   └── CurrentAccount.java
│
├── customers
│   └── Customer.java
│
├── transactions
│   ├── Deposit.java
│   └── Withdraw.java
│
└── reports
    └── AccountReport.java
```

Example:

```java
package accounts;

public class SavingsAccount
{
    public void showAccountType()
    {
        System.out.println("Savings Account");
    }
}
```

```java
import accounts.SavingsAccount;

public class Main
{
    public static void main(String[] args)
    {
        SavingsAccount account = new SavingsAccount();

        account.showAccountType();
    }
}
```

---

# Real-World Scenario 2: E-Commerce Application

```text
ECommerceApplication
│
├── products
│   └── Product.java
│
├── users
│   └── Customer.java
│
├── payments
│   └── Payment.java
│
└── orders
    └── Order.java
```

This structure makes the project easier to understand and maintain.

---

# Real-World Scenario 3: Student Management System

```text
StudentManagementSystem
│
├── students
│   └── Student.java
│
├── teachers
│   └── Teacher.java
│
├── courses
│   └── Course.java
│
└── exams
    └── Result.java
```

---

# Package Access

Classes in the same package can access package-private members.

Example:

```java
class Student
{
    String name = "Ragavarshini";
}
```

Since `name` has no access modifier, it can be accessed only inside the same package.

---

# Important Rules for Packages

- The `package` statement must be the first line in the Java file.
- A Java file can belong to only one package.
- Folder structure should match the package name.
- Package names should use lowercase letters.
- Use `import` to access classes from other packages.
- `java.lang` is imported automatically.

---

# Common Mistakes

## Writing Package Statement After Import

❌ Incorrect:

```java
import java.util.Scanner;

package college;
```

✅ Correct:

```java
package college;

import java.util.Scanner;
```

---

## Wrong Folder Structure

If the package is:

```java
package college.students;
```

The folder structure should be:

```text
college
└── students
    └── Student.java
```

---

## Forgetting `public`

If a class needs to be accessed from another package, it should be declared `public`.

```java
public class Student
{
}
```

---

# Package vs Folder

| Package | Folder |
|---|---|
| Java concept for organizing classes | Operating system directory |
| Declared using `package` keyword | Created in file system |
| Helps manage namespaces | Stores files |
| Usually matches folder structure | May contain any files |

---

# Advantages of Packages

- Organizes classes properly
- Avoids naming conflicts
- Improves code readability
- Makes large projects easier to manage
- Supports access control
- Encourages modular programming
- Makes teamwork easier

---

# Interview Questions

### What is a package in Java?

A package is a group of related classes and interfaces.

---

### Which keyword is used to create a package?

```java
package
```

---

### Which keyword is used to use a class from another package?

```java
import
```

---

### What are built-in packages?

Packages already provided by Java, such as `java.util` and `java.io`.

---

### What is a user-defined package?

A package created by the programmer.

---

### Is `java.lang` imported automatically?

Yes.

---

### Can one Java file belong to multiple packages?

No.

---

# Challenge Exercises

### Challenge 1

Create a package named `college`.

Create a `Student` class inside it.

Import the class into `Main.java`.

---

### Challenge 2

Create packages for:

```text
employees
products
orders
```

Create one class inside each package.

---

### Challenge 3

Create a banking project structure with packages for:

- customers
- accounts
- transactions

---

### Challenge 4

Use the `java.util` package to create an `ArrayList` of student names.

---

### Challenge 5

Create a package named `calculator` with a class containing addition and subtraction methods.

---

# Summary

- A package is a group of related Java classes and interfaces.
- Packages organize large Java projects.
- Java has built-in and user-defined packages.
- Use `package` to create a package.
- Use `import` to access classes from another package.
- Package names should usually be lowercase.
- Packages help avoid class name conflicts and improve project structure.

---

# Conclusion

Packages are essential for organizing Java applications, especially large projects with many classes. They improve readability, maintainability, security, and teamwork. Real-world Java applications such as banking systems, e-commerce platforms, Android apps, Spring Boot projects, and enterprise software use packages extensively to keep code clean and modular.
