# String Comparison in Java

Comparing Strings is one of the most common tasks in Java programming.

For example:

- Login Authentication
- Password Verification
- Email Validation
- Search Systems
- Student Name Matching
- Product Search
- File Name Comparison

Java provides multiple ways to compare Strings.

Understanding the difference between these comparison methods is one of the most frequently asked Java interview topics.

---

# Why Do We Need String Comparison?

Imagine a Login System.

Stored Username

```
Ragavarshini
```

User Input

```
ragavarshini
```

The program should determine whether both Strings are equal.

Java provides several methods for comparing Strings depending on the requirement.

---

# Ways to Compare Strings

Java supports the following comparison methods.

```
==
equals()

equalsIgnoreCase()

compareTo()

compareToIgnoreCase()
```

Each method behaves differently.

---

# 1. Using == Operator

The **== operator** compares the memory addresses (references) of two String objects.

It does **not compare the actual text** stored inside the Strings.

---

## Example 1

```java
public class StringComparison {

    public static void main(String[] args) {

        String s1 = "Java";
        String s2 = "Java";

        System.out.println(s1 == s2);

    }

}
```

### Output

```text
true
```

---

# Why is the Output True?

Both String literals are stored in the **String Constant Pool**.

Only one object is created.

```
String Pool

+---------+
| "Java"  |
+---------+
 ↑       ↑
s1      s2
```

Both variables point to the same object.

---

# Example 2

```java
public class StringComparison {

    public static void main(String[] args) {

        String s1 = new String("Java");

        String s2 = new String("Java");

        System.out.println(s1 == s2);

    }

}
```

### Output

```text
false
```

---

# Why?

Using **new** creates separate objects.

```
Heap

+---------+
| "Java"  | ← s1
+---------+

+---------+
| "Java"  | ← s2
+---------+
```

Different memory locations.

Therefore,

```
==
```

returns false.

---

# Real-World Scenario

Two different customers may have the same name.

Memory locations differ.

Using

```
==
```

is incorrect.

---

# 2. equals()

The equals() method compares the actual contents of Strings.

It ignores memory locations.

---

## Syntax

```java
string1.equals(string2);
```

---

## Example

```java
public class EqualsExample {

    public static void main(String[] args) {

        String s1 =
                new String("Java");

        String s2 =
                new String("Java");

        System.out.println(s1.equals(s2));

    }

}
```

### Output

```text
true
```

---

# Real-World Scenario

Login Authentication

```java
String username = "admin";

String entered = "admin";

if(username.equals(entered))
{
    System.out.println("Login Successful");
}
```

Output

```text
Login Successful
```

---

# 3. equalsIgnoreCase()

This method ignores uppercase and lowercase differences.

---

## Example

```java
public class IgnoreCase {

    public static void main(String[] args) {

        String s1 = "JAVA";

        String s2 = "java";

        System.out.println(
                s1.equalsIgnoreCase(s2));

    }

}
```

### Output

```text
true
```

---

# Real-World Scenario

Email Login

```java
String email =
"RAGAVARSHINI@gmail.com";

String entered =
"ragavarshini@gmail.com";

if(email.equalsIgnoreCase(entered))
{
    System.out.println("Email Matched");
}
```

---

# 4. compareTo()

Compares Strings alphabetically.

Returns

```
0

Positive Value

Negative Value
```

---

# Example

```java
String a = "Apple";

String b = "Apple";

System.out.println(a.compareTo(b));
```

Output

```text
0
```

---

Example

```java
String a = "Apple";

String b = "Banana";

System.out.println(a.compareTo(b));
```

Output

```text
Negative Value
```

---

Example

```java
String a = "Orange";

String b = "Apple";

System.out.println(a.compareTo(b));
```

Output

```text
Positive Value
```

---

# Real-World Scenario

Sorting student names alphabetically.

---

# 5. compareToIgnoreCase()

Ignores uppercase/lowercase while comparing.

---

## Example

```java
String a = "JAVA";

String b = "java";

System.out.println(
a.compareToIgnoreCase(b));
```

Output

```text
0
```

---

# String Pool vs Heap Comparison

### String Literal

```java
String s1 = "Hello";

String s2 = "Hello";
```

Memory

```
String Pool

Hello

↑     ↑

s1    s2
```

```
==
```

returns

```
true
```

---

### new Keyword

```java
String s1 =
new String("Hello");

String s2 =
new String("Hello");
```

Memory

```
Heap

Hello ← s1

Hello ← s2
```

```
==
```

returns

```
false
```

---

equals()

returns

```
true
```

---

# Mini Project

## Login System

```java
public class Login {

    public static void main(String[] args) {

        String storedUsername =
                "Ragavarshini";

        String enteredUsername =
                "ragavarshini";

        if(storedUsername.equalsIgnoreCase(
                enteredUsername))
        {
            System.out.println(
                    "Login Successful");
        }
        else
        {
            System.out.println(
                    "Invalid Username");
        }

    }

}
```

Output

```text
Login Successful
```

---

# Mini Project

## Product Search

```java
public class ProductSearch {

    public static void main(String[] args) {

        String product =
                "Laptop";

        String search =
                "Laptop";

        if(product.equals(search))
        {
            System.out.println(
                    "Product Found");
        }

    }

}
```

Output

```text
Product Found
```

---

# Common Mistakes

## Mistake 1

Using

```
==
```

for content comparison.

❌ Incorrect

```java
String a =
new String("Java");

String b =
new String("Java");

if(a == b)
{
    System.out.println("Equal");
}
```

Output

```text
No Output
```

---

✅ Correct

```java
if(a.equals(b))
{
    System.out.println("Equal");
}
```

Output

```text
Equal
```

---

## Mistake 2

Case-sensitive comparison.

```java
String username = "Admin";

String input = "admin";

System.out.println(
username.equals(input));
```

Output

```text
false
```

---

Correct

```java
username.equalsIgnoreCase(input);
```

Output

```text
true
```

---

# Comparison Table

| Method | Compares | Case Sensitive | Returns |
|----------|-----------|---------------|----------|
| == | Memory Address | Yes | true/false |
| equals() | Content | Yes | true/false |
| equalsIgnoreCase() | Content | No | true/false |
| compareTo() | Alphabetical Order | Yes | int |
| compareToIgnoreCase() | Alphabetical Order | No | int |

---

# Real-World Applications

String comparison is used in

- Login Systems
- Password Verification
- Banking Applications
- Search Engines
- Email Validation
- Student Records
- Product Search
- Hospital Management
- Online Shopping
- File Validation

---

# Interview Questions

### Why should we avoid == for Strings?

Because it compares references instead of contents.

---

### Which method compares actual String contents?

```
equals()
```

---

### Which method ignores uppercase and lowercase?

```
equalsIgnoreCase()
```

---

### Which method is used for alphabetical sorting?

```
compareTo()
```

---

### Which method returns an integer?

```
compareTo()
```

---

# Challenge Exercises

### Challenge 1

Compare two usernames.

---

### Challenge 2

Compare two email addresses ignoring case.

---

### Challenge 3

Sort three names alphabetically.

---

### Challenge 4

Compare two passwords.

---

### Challenge 5

Check whether two product names are identical.

---

# Summary

- == compares memory references.
- equals() compares String contents.
- equalsIgnoreCase() ignores letter case.
- compareTo() compares alphabetically.
- compareToIgnoreCase() ignores case while comparing.
- String comparison is one of the most important Java interview topics.

---

# Conclusion

String comparison is a fundamental concept in Java programming. Choosing the correct comparison method ensures accurate validation, searching, sorting, and authentication in real-world applications. Mastering these techniques is essential for writing reliable and secure Java programs.
