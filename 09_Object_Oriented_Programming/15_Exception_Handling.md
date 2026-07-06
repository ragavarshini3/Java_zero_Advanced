# Exception Handling in Java

While running a Java program, errors may occur because of invalid input, missing files, incorrect calculations, network issues, or unexpected user actions.

For example:

- Dividing a number by zero
- Entering text instead of a number
- Accessing an invalid array index
- Opening a file that does not exist
- Using a null object reference

If these errors are not handled, the program may stop suddenly.

Java provides **Exception Handling** to manage such errors and keep the program running safely.

---

# What is an Exception?

An **Exception** is an unexpected event that occurs while a program is running and interrupts the normal flow of the program.

Example:

```java
int result = 10 / 0;
```

This causes an exception because division by zero is not allowed for integers.

---

# Real-World Example

Imagine an ATM machine.

A user tries to withdraw ₹10,000, but the account balance is only ₹2,000.

Instead of crashing, the ATM should display:

```text
Insufficient balance
```

Similarly, Java programs should handle unexpected situations properly.

---

# Why Do We Need Exception Handling?

Without exception handling:

```text
Error occurs

↓

Program stops suddenly
```

With exception handling:

```text
Error occurs

↓

Program handles the error

↓

Program continues safely
```

Exception handling improves:

- Program reliability
- User experience
- Application security
- Debugging
- Error reporting

---

# Types of Errors in Java

Java errors can be broadly divided into:

```text
1. Compile-Time Errors
2. Run-Time Errors
3. Logical Errors
```

---

## 1. Compile-Time Errors

Compile-time errors happen before the program runs.

Example:

```java
public class Main
{
    public static void main(String[] args)
    {
        System.out.println("Hello")
    }
}
```

The semicolon is missing.

This program will not compile.

---

## 2. Run-Time Errors

Run-time errors happen while the program is running.

Example:

```java
public class Main
{
    public static void main(String[] args)
    {
        int result = 10 / 0;

        System.out.println(result);
    }
}
```

This causes:

```text
ArithmeticException
```

---

## 3. Logical Errors

Logical errors happen when the program runs but produces the wrong output.

Example:

```java
public class Main
{
    public static void main(String[] args)
    {
        int number1 = 10;
        int number2 = 20;

        int result = number1 - number2;

        System.out.println(result);
    }
}
```

The program runs, but subtraction is used instead of addition.

---

# Exception Hierarchy

```text
Throwable
│
├── Error
│
└── Exception
    │
    ├── RuntimeException
    │   ├── ArithmeticException
    │   ├── NullPointerException
    │   ├── ArrayIndexOutOfBoundsException
    │   └── NumberFormatException
    │
    └── Checked Exceptions
        ├── IOException
        └── SQLException
```

---

# Types of Exceptions

Java exceptions are mainly divided into:

```text
1. Checked Exceptions
2. Unchecked Exceptions
```

---

## Checked Exceptions

Checked exceptions are checked by the compiler.

They must be handled using:

- `try-catch`
- `throws`

Example:

```java
IOException
```

---

## Unchecked Exceptions

Unchecked exceptions occur during program execution.

They are usually caused by programming mistakes.

Examples:

```text
ArithmeticException
NullPointerException
ArrayIndexOutOfBoundsException
NumberFormatException
```

---

# Keywords Used in Exception Handling

Java uses these keywords:

```text
try
catch
finally
throw
throws
```

---

# 1. try Block

The `try` block contains code that may cause an exception.

```java
try
{
    int result = 10 / 0;
}
```

---

# 2. catch Block

The `catch` block handles the exception.

```java
catch(ArithmeticException exception)
{
    System.out.println("Cannot divide by zero");
}
```

---

# 3. finally Block

The `finally` block usually executes whether an exception occurs or not.

It is commonly used to close files, database connections, or other resources.

```java
finally
{
    System.out.println("Program finished");
}
```

---

# Basic Syntax

```java
try
{
    // risky code
}
catch(Exception exception)
{
    // exception handling code
}
finally
{
    // always executed code
}
```

---

# Example 1: Division by Zero

```java
public class Main
{
    public static void main(String[] args)
    {
        try
        {
            int result = 10 / 0;

            System.out.println(result);
        }
        catch(ArithmeticException exception)
        {
            System.out.println("Cannot divide by zero");
        }

        System.out.println("Program continues");
    }
}
```

### Output

```text
Cannot divide by zero
Program continues
```

---

# Example 2: Array Index Exception

```java
public class Main
{
    public static void main(String[] args)
    {
        int[] numbers = {10, 20, 30};

        try
        {
            System.out.println(numbers[5]);
        }
        catch(ArrayIndexOutOfBoundsException exception)
        {
            System.out.println("Invalid array index");
        }
    }
}
```

### Output

```text
Invalid array index
```

---

# Example 3: Number Format Exception

```java
public class Main
{
    public static void main(String[] args)
    {
        String value = "Hello";

        try
        {
            int number = Integer.parseInt(value);

            System.out.println(number);
        }
        catch(NumberFormatException exception)
        {
            System.out.println("Please enter a valid number");
        }
    }
}
```

### Output

```text
Please enter a valid number
```

---

# Example 4: Null Pointer Exception

```java
public class Main
{
    public static void main(String[] args)
    {
        String name = null;

        try
        {
            System.out.println(name.length());
        }
        catch(NullPointerException exception)
        {
            System.out.println("Name cannot be null");
        }
    }
}
```

### Output

```text
Name cannot be null
```

---

# Multiple catch Blocks

A program can handle different exceptions using multiple `catch` blocks.

```java
public class Main
{
    public static void main(String[] args)
    {
        try
        {
            int[] numbers = {10, 20, 30};

            int result = numbers[5] / 0;

            System.out.println(result);
        }
        catch(ArithmeticException exception)
        {
            System.out.println("Cannot divide by zero");
        }
        catch(ArrayIndexOutOfBoundsException exception)
        {
            System.out.println("Invalid array index");
        }
        catch(Exception exception)
        {
            System.out.println("Some error occurred");
        }
    }
}
```

### Output

```text
Invalid array index
```

The first exception occurs when trying to access `numbers[5]`, so Java handles `ArrayIndexOutOfBoundsException`.

---

# Important Rule for Multiple catch Blocks

Always write specific exceptions first and general exceptions last.

Correct:

```java
catch(ArithmeticException exception)
{
}
catch(Exception exception)
{
}
```

Incorrect:

```java
catch(Exception exception)
{
}
catch(ArithmeticException exception)
{
}
```

The second catch block becomes unreachable.

---

# finally Block Example

```java
public class Main
{
    public static void main(String[] args)
    {
        try
        {
            int result = 10 / 0;

            System.out.println(result);
        }
        catch(ArithmeticException exception)
        {
            System.out.println("Cannot divide by zero");
        }
        finally
        {
            System.out.println("Finally block executed");
        }
    }
}
```

### Output

```text
Cannot divide by zero
Finally block executed
```

---

# Real-World Scenario 1: ATM Withdrawal System

```java
class BankAccount
{
    private double balance = 5000;

    public void withdraw(double amount)
    {
        try
        {
            if(amount <= 0)
            {
                throw new IllegalArgumentException(
                        "Withdrawal amount must be greater than zero");
            }

            if(amount > balance)
            {
                throw new IllegalArgumentException(
                        "Insufficient balance");
            }

            balance = balance - amount;

            System.out.println("Withdrawal successful");

            System.out.println("Remaining Balance: ₹" + balance);
        }
        catch(IllegalArgumentException exception)
        {
            System.out.println("Transaction Failed: " + exception.getMessage());
        }
    }
}

public class Main
{
    public static void main(String[] args)
    {
        BankAccount account = new BankAccount();

        account.withdraw(7000);

        account.withdraw(2000);
    }
}
```

### Output

```text
Transaction Failed: Insufficient balance
Withdrawal successful
Remaining Balance: ₹3000.0
```

---

# Real-World Scenario 2: Student Marks Validation

```java
class Student
{
    public void setMarks(int marks)
    {
        try
        {
            if(marks < 0 || marks > 100)
            {
                throw new IllegalArgumentException(
                        "Marks must be between 0 and 100");
            }

            System.out.println("Marks saved successfully: " + marks);
        }
        catch(IllegalArgumentException exception)
        {
            System.out.println("Invalid Marks: " + exception.getMessage());
        }
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Student student = new Student();

        student.setMarks(120);

        student.setMarks(85);
    }
}
```

### Output

```text
Invalid Marks: Marks must be between 0 and 100
Marks saved successfully: 85
```

---

# Real-World Scenario 3: Login System

```java
class LoginSystem
{
    public void login(String username, String password)
    {
        try
        {
            if(username == null || username.isEmpty())
            {
                throw new IllegalArgumentException(
                        "Username cannot be empty");
            }

            if(password == null || password.length() < 8)
            {
                throw new IllegalArgumentException(
                        "Password must contain at least 8 characters");
            }

            System.out.println("Login request accepted for: " + username);
        }
        catch(IllegalArgumentException exception)
        {
            System.out.println("Login Failed: " + exception.getMessage());
        }
    }
}

public class Main
{
    public static void main(String[] args)
    {
        LoginSystem loginSystem = new LoginSystem();

        loginSystem.login("", "Java1234");

        loginSystem.login("ragavarshini", "Java1234");
    }
}
```

### Output

```text
Login Failed: Username cannot be empty
Login request accepted for: ragavarshini
```

---

# throw Keyword

The `throw` keyword is used to manually create an exception.

```java
throw new IllegalArgumentException("Invalid value");
```

Example:

```java
public class Main
{
    public static void main(String[] args)
    {
        int age = 15;

        if(age < 18)
        {
            throw new IllegalArgumentException(
                    "Age must be 18 or above");
        }

        System.out.println("Eligible");
    }
}
```

This program stops because the exception is not handled.

---

# Handling throw Example

```java
public class Main
{
    public static void main(String[] args)
    {
        try
        {
            int age = 15;

            if(age < 18)
            {
                throw new IllegalArgumentException(
                        "Age must be 18 or above");
            }

            System.out.println("Eligible");
        }
        catch(IllegalArgumentException exception)
        {
            System.out.println("Not Eligible: " + exception.getMessage());
        }
    }
}
```

### Output

```text
Not Eligible: Age must be 18 or above
```

---

# throws Keyword

The `throws` keyword is used in a method declaration to indicate that the method may throw an exception.

```java
void readFile() throws IOException
{
}
```

Example:

```java
import java.io.FileReader;
import java.io.IOException;

public class Main
{
    public static void readFile() throws IOException
    {
        FileReader fileReader = new FileReader("data.txt");

        fileReader.close();
    }

    public static void main(String[] args)
    {
        try
        {
            readFile();

            System.out.println("File read successfully");
        }
        catch(IOException exception)
        {
            System.out.println("File not found or cannot be read");
        }
    }
}
```

---

# throw vs throws

| `throw` | `throws` |
|---|---|
| Used to create an exception manually | Used to declare possible exceptions |
| Used inside a method | Used in method declaration |
| Throws one exception object | Can declare multiple exception types |
| Example: `throw new Exception()` | Example: `void test() throws IOException` |

---

# Custom Exception

You can create your own exception class.

```java
class InvalidAgeException extends Exception
{
    InvalidAgeException(String message)
    {
        super(message);
    }
}
```

Example:

```java
class VotingSystem
{
    public void checkEligibility(int age)
            throws InvalidAgeException
    {
        if(age < 18)
        {
            throw new InvalidAgeException(
                    "Age must be 18 or above to vote");
        }

        System.out.println("Eligible to vote");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        VotingSystem votingSystem = new VotingSystem();

        try
        {
            votingSystem.checkEligibility(16);
        }
        catch(InvalidAgeException exception)
        {
            System.out.println(exception.getMessage());
        }
    }
}
```

### Output

```text
Age must be 18 or above to vote
```

---

# Common Exceptions in Java

| Exception | When It Happens |
|---|---|
| `ArithmeticException` | Dividing a number by zero |
| `NullPointerException` | Using a null object |
| `ArrayIndexOutOfBoundsException` | Accessing an invalid array index |
| `NumberFormatException` | Converting invalid text into a number |
| `IllegalArgumentException` | Passing an invalid argument to a method |
| `IOException` | File or input/output error |
| `ClassNotFoundException` | Class is not found at runtime |

---

# Common Mistakes

## Catching Exception Before Specific Exceptions

❌ Incorrect:

```java
try
{
    int result = 10 / 0;
}
catch(Exception exception)
{
    System.out.println("Error");
}
catch(ArithmeticException exception)
{
    System.out.println("Cannot divide by zero");
}
```

The `ArithmeticException` block becomes unreachable.

---

## Ignoring Exceptions

❌ Avoid empty catch blocks:

```java
try
{
    int result = 10 / 0;
}
catch(Exception exception)
{
}
```

Always display, log, or handle the exception properly.

---

## Using Exceptions for Normal Program Flow

Do not use exceptions for ordinary conditions.

For example, instead of using an exception to check whether a number is positive, use an `if` condition when it is a normal validation case.

Use exceptions for unexpected or exceptional situations.

---

# Advantages of Exception Handling

- Prevents sudden program termination
- Improves user experience
- Makes programs more reliable
- Helps identify errors
- Supports safe recovery from failures
- Improves application stability
- Useful in file handling, database operations, and network communication

---

# Interview Questions

### What is an exception?

An exception is an unexpected event that occurs during program execution and interrupts the normal flow.

---

### What is the difference between an error and an exception?

Errors are serious problems that applications usually cannot handle, while exceptions are conditions that programs can often handle.

---

### What are checked exceptions?

Exceptions checked by the compiler that must be handled or declared.

---

### What are unchecked exceptions?

Exceptions that occur at runtime, usually because of programming mistakes.

---

### What is the purpose of `try`?

It contains code that may cause an exception.

---

### What is the purpose of `catch`?

It handles an exception.

---

### What is the purpose of `finally`?

It contains code that usually executes whether an exception occurs or not.

---

### What is the difference between `throw` and `throws`?

`throw` creates an exception manually, while `throws` declares that a method may throw an exception.

---

# Challenge Exercises

### Challenge 1

Write a program that handles division by zero using `try-catch`.

---

### Challenge 2

Create an array and handle invalid index access.

---

### Challenge 3

Create a student marks program that throws an exception when marks are below 0 or above 100.

---

### Challenge 4

Create a bank withdrawal program that handles insufficient balance.

---

### Challenge 5

Create a custom exception called `InvalidPasswordException`.

Throw it when a password has fewer than 8 characters.

---

# Summary

- Exceptions are unexpected events that occur during program execution.
- Java uses `try`, `catch`, `finally`, `throw`, and `throws` for exception handling.
- Checked exceptions are checked by the compiler.
- Unchecked exceptions occur at runtime.
- `throw` manually creates an exception.
- `throws` declares possible exceptions.
- Exception handling prevents sudden program termination and improves reliability.

---

# Conclusion

Exception handling is essential for building reliable Java applications. It allows programs to handle unexpected situations such as invalid input, division by zero, file errors, insufficient balance, and login failures. Proper exception handling improves user experience, application stability, and code quality.
