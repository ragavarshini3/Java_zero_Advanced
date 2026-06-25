# StringBuilder and StringBuffer in Java

In the previous lessons, we learned that **Strings are immutable**.

This means once a String object is created, it cannot be modified.

Whenever we modify a String, Java creates a **new object** in memory.

Creating multiple objects repeatedly decreases performance and increases memory usage.

To solve this problem, Java provides:

- StringBuilder
- StringBuffer

These classes allow Strings to be modified without creating new objects repeatedly.

---

# Why Do We Need StringBuilder and StringBuffer?

Imagine an online chat application.

A user types:

```
H
He
Hel
Hell
Hello
```

If String is used, Java creates a new object for every modification.

```
"H"
↓

"He"
↓

"Hel"
↓

"Hell"
↓

"Hello"
```

This wastes memory.

Instead, StringBuilder modifies the existing object.

---

# What is StringBuilder?

StringBuilder is a mutable sequence of characters.

Mutable means the contents of the object can be changed without creating a new object.

It is faster than String because it avoids unnecessary object creation.

---

# Syntax

```java
StringBuilder builder = new StringBuilder();
```

Example

```java
StringBuilder name = new StringBuilder("Java");
```

---

# What is StringBuffer?

StringBuffer is also a mutable sequence of characters.

It works almost exactly like StringBuilder.

The main difference is:

**StringBuffer is thread-safe**, while StringBuilder is not.

---

# Syntax

```java
StringBuffer buffer = new StringBuffer();
```

Example

```java
StringBuffer name = new StringBuffer("Java");
```

---

# Difference Between String, StringBuilder and StringBuffer

| Feature | String | StringBuilder | StringBuffer |
|---------|---------|---------------|--------------|
| Mutable | ❌ No | ✅ Yes | ✅ Yes |
| Thread Safe | No | No | Yes |
| Performance | Slow | Fastest | Slightly Slower |
| Memory Usage | High | Low | Low |
| Best For | Fixed Text | Single-thread Applications | Multi-thread Applications |

---

# Memory Comparison

## String

```java
String text = "Java";

text = text + " Programming";
```

Memory

```
"Java"

↓

"Java Programming"
```

Two objects are created.

---

## StringBuilder

```java
StringBuilder text =
new StringBuilder("Java");

text.append(" Programming");
```

Memory

```
Java

↓

Java Programming
```

Only one object is modified.

---

# Creating StringBuilder

```java
public class BuilderExample {

    public static void main(String[] args) {

        StringBuilder builder =
                new StringBuilder("Java");

        System.out.println(builder);

    }

}
```

Output

```text
Java
```

---

# append()

Adds data at the end.

## Syntax

```java
builder.append(value);
```

Example

```java
public class AppendExample {

    public static void main(String[] args) {

        StringBuilder builder =
                new StringBuilder("Java");

        builder.append(" Programming");

        System.out.println(builder);

    }

}
```

Output

```text
Java Programming
```

---

# Real-World Scenario

A chat application continuously appends messages.

```java
StringBuilder chat =
new StringBuilder();

chat.append("Hello ");

chat.append("World");

System.out.println(chat);
```

Output

```text
Hello World
```

---

# insert()

Inserts text at a specified position.

## Syntax

```java
builder.insert(index,value);
```

Example

```java
StringBuilder text =
new StringBuilder("Jva");

text.insert(1,"a");

System.out.println(text);
```

Output

```text
Java
```

---

# Real-World Scenario

Insert a country code into a phone number.

Before

```
9876543210
```

After

```
+91 9876543210
```

---

# delete()

Deletes characters.

## Syntax

```java
builder.delete(start,end);
```

Example

```java
StringBuilder text =
new StringBuilder("Java Programming");

text.delete(4,16);

System.out.println(text);
```

Output

```text
Java
```

---

# deleteCharAt()

Deletes one character.

```java
StringBuilder text =
new StringBuilder("Javva");

text.deleteCharAt(3);

System.out.println(text);
```

Output

```text
Java
```

---

# replace()

Replaces characters.

```java
StringBuilder builder =
new StringBuilder("Hello Java");

builder.replace(6,10,"Python");

System.out.println(builder);
```

Output

```text
Hello Python
```

---

# reverse()

Reverses the String.

```java
StringBuilder builder =
new StringBuilder("Java");

builder.reverse();

System.out.println(builder);
```

Output

```text
avaJ
```

---

# setCharAt()

Changes a character.

```java
StringBuilder builder =
new StringBuilder("Jovo");

builder.setCharAt(1,'a');

System.out.println(builder);
```

Output

```text
Java
```

---

# capacity()

Returns current capacity.

```java
StringBuilder builder =
new StringBuilder();

System.out.println(builder.capacity());
```

Output

```text
16
```

---

# length()

Returns number of characters.

```java
StringBuilder builder =
new StringBuilder("Programming");

System.out.println(builder.length());
```

Output

```text
11
```

---

# StringBuffer Example

```java
public class BufferExample {

    public static void main(String[] args) {

        StringBuffer buffer =
                new StringBuffer("Java");

        buffer.append(" Programming");

        System.out.println(buffer);

    }

}
```

Output

```text
Java Programming
```

---

# Real-World Scenario 1: Report Generation

Suppose a company generates a monthly report.

```java
public class Report {

    public static void main(String[] args) {

        StringBuilder report =
                new StringBuilder();

        report.append("Sales Report\n");

        report.append("January : ₹10000\n");

        report.append("February : ₹15000\n");

        report.append("March : ₹18000");

        System.out.println(report);

    }

}
```

Output

```text
Sales Report
January : ₹10000
February : ₹15000
March : ₹18000
```

---

# Real-World Scenario 2: Shopping Cart

```java
public class Shopping {

    public static void main(String[] args) {

        StringBuilder cart =
                new StringBuilder();

        cart.append("Laptop\n");
        cart.append("Mouse\n");
        cart.append("Keyboard");

        System.out.println(cart);

    }

}
```

---

# Real-World Scenario 3: Chat Application

```java
public class Chat {

    public static void main(String[] args) {

        StringBuilder message =
                new StringBuilder();

        message.append("Hi");

        message.append(", ");

        message.append("How are you?");

        System.out.println(message);

    }

}
```

Output

```text
Hi, How are you?
```

---

# Performance Comparison

```java
String

↓

Creates New Object

↓

Slower
```

```
StringBuilder

↓

Modifies Existing Object

↓

Faster
```

```
StringBuffer

↓

Modifies Existing Object

↓

Thread Safe
```

---

# When to Use What?

### Use String

- Fixed text
- Constants
- Configuration values

---

### Use StringBuilder

- Frequent modifications
- Report generation
- Text editing
- Data processing

---

### Use StringBuffer

- Multi-threaded applications
- Banking software
- Hospital Management Systems
- Concurrent applications

---

# Common Mistakes

### Forgetting Mutable Nature

```java
StringBuilder builder =
new StringBuilder("Java");

builder.append(" Programming");

System.out.println(builder);
```

No reassignment needed.

Unlike String.

---

# Real-World Applications

StringBuilder and StringBuffer are used in:

- Text Editors
- Chat Applications
- Banking Systems
- Report Generation
- PDF Generation
- XML Processing
- JSON Processing
- Log File Creation
- Web Applications

---

# Challenge Exercises

### Challenge 1

Append your name using StringBuilder.

---

### Challenge 2

Reverse a String.

---

### Challenge 3

Replace one word with another.

---

### Challenge 4

Delete unwanted characters.

---

### Challenge 5

Insert your country code before a phone number.

---

### Challenge 6

Generate a student report using StringBuilder.

---

### Challenge 7

Create a shopping cart using StringBuilder.

---

### Challenge 8

Compare the performance of String and StringBuilder by concatenating text inside a loop.

---

# Summary

- String objects are immutable.
- StringBuilder and StringBuffer are mutable.
- StringBuilder is faster.
- StringBuffer is thread-safe.
- StringBuilder is preferred for single-threaded applications.
- StringBuffer is preferred for multi-threaded applications.

---

# Conclusion

StringBuilder and StringBuffer provide efficient ways to modify text without creating multiple objects. They improve performance, reduce memory usage, and are widely used in real-world applications such as report generation, chat systems, banking software, and data processing. Understanding these classes is essential for writing optimized and scalable Java applications.
