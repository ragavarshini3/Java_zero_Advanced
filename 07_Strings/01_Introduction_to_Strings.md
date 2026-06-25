# Introduction to Strings in Java

In our daily lives, we use text everywhere.

Examples include:

- Your Name
- Email Address
- Mobile Number
- Password 
- Address
- Messages
- Search Keywords
- Product Names

In Java, text is stored using **Strings**.

A String is one of the most commonly used data types in Java because almost every application works with text.

---

# What is a String?

A **String** is a sequence of characters enclosed inside double quotation marks (`"`).

Unlike primitive data types such as `int`, `double`, or `char`, a String is an object in Java.

---

# Real-World Examples

A banking application stores:

```text
Customer Name
Account Number
Branch Name
```

An online shopping application stores:

```text
Product Name
Category
Brand
```

A social media application stores:

```text
Username
Bio
Messages
Comments
```

All these are Strings.

---

# Why Do We Need Strings?

Imagine storing your name using characters.

```java
char c1 = 'J';
char c2 = 'o';
char c3 = 'h';
char c4 = 'n';
```

This is difficult.

Instead, Java provides String.

```java
String name = "John";
```

Advantages:

- Easy to store text
- Easy to manipulate
- Rich built-in methods
- Memory efficient using String Pool

---

# String Declaration

## Syntax

```java
String variableName;
```

Example

```java
String name;
```

---

# String Initialization

```java
String name = "Alice";
```

---

# Creating Strings

There are two ways to create Strings.

---

## Method 1: Using String Literal

```java
String city = "Chennai";
```

This is the most commonly used method.

The String is stored in the **String Constant Pool**.

---

## Method 2: Using new Keyword

```java
String city = new String("Chennai");
```

This creates a new object in Heap Memory.

---

# Example 1

```java
public class StringExample {

    public static void main(String[] args) {

        String name = "Ragavarshini";

        System.out.println(name);

    }

}
```

### Output

```text
Ragavarshini
```

---

# Memory Representation

Using Literal

```java
String s1 = "Java";
String s2 = "Java";
```

Memory

```text
String Pool

+---------+
| "Java"  |
+---------+
   ↑    ↑
  s1    s2
```

Both variables point to the same object.

---

Using new Keyword

```java
String s1 = new String("Java");
String s2 = new String("Java");
```

Memory

```text
Heap Memory

+---------+
| "Java"  | ← s1
+---------+

+---------+
| "Java"  | ← s2
+---------+
```

Two different objects are created.

---

# String Constant Pool

Java stores String literals in a special memory area called the **String Constant Pool (SCP)**.

Purpose:

- Saves memory
- Avoids duplicate objects
- Improves performance

Example

```java
String a = "Hello";
String b = "Hello";
```

Only one object is created.

---

# String is Immutable

One of the most important properties of String is:

**Strings are Immutable.**

Immutable means:

Once a String object is created, it cannot be changed.

---

## Example

```java
String language = "Java";

language = "Python";

System.out.println(language);
```

Output

```text
Python
```

Did Java modify the original object?

No.

Memory

```text
Before

language
   ↓
"Java"

After

language
   ↓
"Python"

"Java" still exists.
```

A new object is created.

---

# Example 2

```java
public class ImmutableExample {

    public static void main(String[] args) {

        String text = "Hello";

        text = text + " World";

        System.out.println(text);

    }

}
```

Output

```text
Hello World
```

The original `"Hello"` object remains unchanged.

---

# String Concatenation

Strings can be combined using the `+` operator.

```java
String firstName = "John";
String lastName = "Doe";

String fullName = firstName + " " + lastName;

System.out.println(fullName);
```

Output

```text
John Doe
```

---

# String Length

The `length()` method returns the number of characters.

```java
String language = "Java";

System.out.println(language.length());
```

Output

```text
4
```

---

# Accessing Characters

Use `charAt()`.

```java
String language = "Java";

System.out.println(language.charAt(2));
```

Output

```text
v
```

---

# User Input Example

```java
import java.util.Scanner;

public class UserInputString {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Your Name : ");

        String name = sc.nextLine();

        System.out.println("Welcome " + name);

        sc.close();

    }

}
```

### Sample Output

```text
Enter Your Name : Ragavarshini

Welcome Ragavarshini
```

---

# Real-World Scenario 1: Student Management System

```java
public class Student {

    public static void main(String[] args) {

        String studentName = "Ragavarshini";
        String department = "Artificial Intelligence";

        System.out.println("Student : " + studentName);
        System.out.println("Department : " + department);

    }

}
```

Output

```text
Student : Ragavarshini
Department : Artificial Intelligence
```

---

# Real-World Scenario 2: Banking Application

```java
public class Bank {

    public static void main(String[] args) {

        String customerName = "Rahul";
        String accountType = "Savings";

        System.out.println(customerName);
        System.out.println(accountType);

    }

}
```

---

# Real-World Scenario 3: Online Shopping

```java
public class Shopping {

    public static void main(String[] args) {

        String product = "Laptop";
        String brand = "Dell";

        System.out.println("Product : " + product);
        System.out.println("Brand : " + brand);

    }

}
```

---

# Common Mistakes

## Using Single Quotes

❌ Incorrect

```java
String name = 'John';
```

Error:

```text
Type mismatch
```

---

## Correct

```java
String name = "John";
```

---

## Forgetting Double Quotes

❌ Incorrect

```java
String city = Chennai;
```

---

## Correct

```java
String city = "Chennai";
```

---

# Difference Between char and String

| char | String |
|------|---------|
| Stores one character | Stores multiple characters |
| Uses single quotes | Uses double quotes |
| Primitive data type | Class (Object) |
| Example: 'A' | Example: "Apple" |

---

# Advantages of Strings

- Easy to store text
- Built-in methods
- Supports concatenation
- Memory optimized using String Pool
- Immutable and secure
- Widely used in every Java application

---

# Real-World Applications

Strings are used in:

- Login Systems
- Search Engines
- Banking Applications
- Chat Applications
- Email Systems
- E-Commerce Websites
- Social Media Platforms
- Hospital Management Systems
- Library Management Systems
- Student Management Systems

---

# Challenge Exercises

### Challenge 1

Create a program to store your name and display it.

---

### Challenge 2

Store your college name in a String.

Display it.

---

### Challenge 3

Accept a user's city name using Scanner.

Display:

```
Welcome to <City>
```

---

### Challenge 4

Store first name and last name separately.

Combine them into a full name.

---

### Challenge 5

Find the length of your name.

---

# Summary

- A String is a sequence of characters.
- Strings are objects in Java.
- Strings can be created using literals or the `new` keyword.
- String literals are stored in the String Constant Pool.
- Strings are immutable.
- Java provides many built-in methods for String manipulation.

---

# Conclusion

Strings are one of the most important concepts in Java because almost every real-world application works with textual data. Understanding how Strings are created, stored, and manipulated forms the foundation for advanced topics such as String methods, StringBuilder, StringBuffer, regular expressions, file handling, and web development.
