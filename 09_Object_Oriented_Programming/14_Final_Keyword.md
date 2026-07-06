# Final Keyword in Java

The `final` keyword in Java is used to restrict changes.

It can be used with:

- Variables
- Methods
- Classes

Using `final` helps protect important values, methods, and class behavior.

---

# Why Do We Need the `final` Keyword?

In real-world applications, some values should never change.

For example:

- PI value
- College code
- Government ID
- Maximum login attempts
- Fixed tax percentage
- Application version

Similarly, some methods should not be overridden, and some classes should not be inherited.

Java uses the `final` keyword for these restrictions.

---

# Types of `final` in Java

```text
1. final Variable
2. final Method
3. final Class
```

---

# 1. final Variable

A `final` variable cannot be changed after assigning a value.

It becomes a constant.

---

# Syntax

```java
final dataType variableName = value;
```

Example:

```java
final double PI = 3.14159;
```

---

# Example 1: final Variable

```java
public class Main
{
    public static void main(String[] args)
    {
        final int age = 20;

        System.out.println("Age: " + age);

        // age = 21;
        // Error because age is final
    }
}
```

### Output

```text
Age: 20
```

---

# Real-World Example: College Code

A college code should not change after it is assigned.

```java
class College
{
    final String collegeCode = "KGISL2026";

    void displayCollegeCode()
    {
        System.out.println("College Code: " + collegeCode);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        College college = new College();

        college.displayCollegeCode();
    }
}
```

### Output

```text
College Code: KGISL2026
```

---

# Example 2: Constant Value

```java
public class Main
{
    public static void main(String[] args)
    {
        final double PI = 3.14159;

        double radius = 5;

        double area = PI * radius * radius;

        System.out.println("Area of Circle: " + area);
    }
}
```

### Output

```text
Area of Circle: 78.53975
```

---

# Naming Convention for Constants

Final constant variable names are usually written in uppercase.

```java
final int MAX_LOGIN_ATTEMPTS = 3;

final double GST_RATE = 18.0;

final String COLLEGE_NAME = "KGISL Institute of Technology";
```

---

# `static final` Constants

When a constant belongs to the entire class and should be shared by all objects, use `static final`.

```java
class Constants
{
    static final double PI = 3.14159;

    static final int MAX_STUDENTS = 60;
}

public class Main
{
    public static void main(String[] args)
    {
        System.out.println("PI: " + Constants.PI);

        System.out.println("Maximum Students: " + Constants.MAX_STUDENTS);
    }
}
```

### Output

```text
PI: 3.14159
Maximum Students: 60
```

---

# 2. final Method

A `final` method cannot be overridden by a child class.

This is useful when a method contains important logic that should not be changed.

---

# Example: final Method

```java
class BankAccount
{
    final void displayBankName()
    {
        System.out.println("Bank Name: State Bank");
    }
}

class SavingsAccount extends BankAccount
{
    void calculateInterest()
    {
        System.out.println("Interest calculated");
    }

    // displayBankName() cannot be overridden here
}

public class Main
{
    public static void main(String[] args)
    {
        SavingsAccount account = new SavingsAccount();

        account.displayBankName();

        account.calculateInterest();
    }
}
```

### Output

```text
Bank Name: State Bank
Interest calculated
```

---

# Invalid Example: Overriding a final Method

```java
class Parent
{
    final void display()
    {
        System.out.println("Parent method");
    }
}

class Child extends Parent
{
    // Error
    // void display()
    // {
    //     System.out.println("Child method");
    // }
}
```

A `final` method cannot be overridden.

---

# 3. final Class

A `final` class cannot be inherited.

This means no other class can extend it.

---

# Example: final Class

```java
final class SecuritySystem
{
    void checkSecurity()
    {
        System.out.println("Security verification completed");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        SecuritySystem security = new SecuritySystem();

        security.checkSecurity();
    }
}
```

### Output

```text
Security verification completed
```

---

# Invalid Example: Inheriting a final Class

```java
final class Vehicle
{
}

// Error
// class Car extends Vehicle
// {
// }
```

A `final` class cannot be extended.

---

# Real-World Scenario 1: Banking Application

In a banking system, the bank name should remain fixed.

```java
class Bank
{
    static final String BANK_NAME = "State Bank of India";

    void displayBankName()
    {
        System.out.println("Bank Name: " + BANK_NAME);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Bank bank = new Bank();

        bank.displayBankName();
    }
}
```

### Output

```text
Bank Name: State Bank of India
```

---

# Real-World Scenario 2: Student Management System

The maximum marks for an exam should remain fixed.

```java
class Exam
{
    static final int MAX_MARKS = 100;

    void displayMaxMarks()
    {
        System.out.println("Maximum Marks: " + MAX_MARKS);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Exam exam = new Exam();

        exam.displayMaxMarks();
    }
}
```

### Output

```text
Maximum Marks: 100
```

---

# Real-World Scenario 3: Login System

The maximum login attempts should remain fixed.

```java
class LoginSystem
{
    static final int MAX_LOGIN_ATTEMPTS = 3;

    void displayLoginLimit()
    {
        System.out.println(
                "Maximum Login Attempts: " +
                MAX_LOGIN_ATTEMPTS);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        LoginSystem login = new LoginSystem();

        login.displayLoginLimit();
    }
}
```

### Output

```text
Maximum Login Attempts: 3
```

---

# Real-World Scenario 4: Employee Salary System

A company can prevent changes to its salary calculation rule.

```java
class Employee
{
    final void calculateBaseSalary()
    {
        System.out.println("Base salary is calculated using company policy");
    }
}

class Developer extends Employee
{
    void calculateBonus()
    {
        System.out.println("Developer bonus calculated");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Developer developer = new Developer();

        developer.calculateBaseSalary();

        developer.calculateBonus();
    }
}
```

### Output

```text
Base salary is calculated using company policy
Developer bonus calculated
```

---

# final Variable vs Normal Variable

| Normal Variable | final Variable |
|---|---|
| Value can be changed | Value cannot be changed |
| Used for normal data | Used for constant data |
| Example: `int age = 20;` | Example: `final int MAX = 100;` |

---

# final Method vs Normal Method

| Normal Method | final Method |
|---|---|
| Can be overridden | Cannot be overridden |
| Child class can change behavior | Child class cannot change behavior |
| Used for flexible behavior | Used for fixed behavior |

---

# final Class vs Normal Class

| Normal Class | final Class |
|---|---|
| Can be inherited | Cannot be inherited |
| Can have child classes | Cannot have child classes |
| Used for extensible design | Used for restricted design |

---

# Important Rules

- A `final` variable must be initialized only once.
- A `final` method cannot be overridden.
- A `final` class cannot be inherited.
- Constructors cannot be `final`.
- Abstract methods cannot be `final`.
- A class cannot be both `abstract` and `final`.

---

# Why Cannot an Abstract Method Be final?

An abstract method must be overridden by a child class.

A final method cannot be overridden.

Therefore, this is invalid:

```java
abstract final void display();
```

---

# Common Mistakes

## Changing a final Variable

❌ Incorrect:

```java
final int marks = 90;

marks = 95;
```

This causes a compilation error.

---

## Overriding a final Method

❌ Incorrect:

```java
class Parent
{
    final void show()
    {
        System.out.println("Hello");
    }
}

class Child extends Parent
{
    // void show()
    // {
    //     System.out.println("Hi");
    // }
}
```

---

## Extending a final Class

❌ Incorrect:

```java
final class Parent
{
}

// class Child extends Parent
// {
// }
```

---

# Advantages of final Keyword

- Protects constant values
- Prevents accidental changes
- Protects important methods
- Prevents unwanted inheritance
- Improves code safety
- Makes application rules clear
- Helps create secure applications

---

# Interview Questions

### What is the `final` keyword in Java?

The `final` keyword is used to restrict changes to variables, methods, and classes.

---

### Can a final variable be changed?

No.

---

### Can a final method be overridden?

No.

---

### Can a final class be inherited?

No.

---

### Can a constructor be final?

No.

---

### Can an abstract method be final?

No.

---

### What is the difference between `final`, `finally`, and `finalize()`?

| Keyword / Method | Purpose |
|---|---|
| `final` | Restricts changes to variables, methods, or classes |
| `finally` | Used in exception handling and usually executes whether an exception occurs or not |
| `finalize()` | A method historically associated with garbage collection; it should not be relied on in modern Java |

---

# Challenge Exercises

### Challenge 1

Create a class with a `final` variable named `COLLEGE_NAME`.

Display the value.

---

### Challenge 2

Create a `BankAccount` class with a `final` method called `displayBankName()`.

Create a child class and verify that the method cannot be overridden.

---

### Challenge 3

Create a `final` class called `SecuritySystem`.

Try to create a child class and observe the error.

---

### Challenge 4

Create a class called `Exam` with:

```java
static final int MAX_MARKS = 100;
```

Display the maximum marks.

---

### Challenge 5

Create a login program with:

```java
static final int MAX_LOGIN_ATTEMPTS = 3;
```

Display the maximum allowed attempts.

---

# Summary

- `final` restricts changes in Java.
- A `final` variable cannot be changed.
- A `final` method cannot be overridden.
- A `final` class cannot be inherited.
- `static final` is commonly used for shared constants.
- `final` improves security, readability, and code safety.

---

# Conclusion

The `final` keyword is used to protect important values, methods, and classes in Java. It is commonly used for constants such as maximum marks, tax rates, company names, login limits, and configuration values. It also prevents unwanted method overriding and inheritance, helping developers create safer and more reliable Java applications.
