# Introduction to Arrays in Java

Imagine a school management system that stores marks for 100 students.

Without arrays:

```java
int mark1 = 85;
int mark2 = 90;
int mark3 = 78;
int mark4 = 88;
...
```

Managing hundreds of variables becomes difficult.

To solve this problem, Java provides **Arrays**.

Arrays allow us to store multiple values of the same data type using a single variable.

---

# What is an Array?

An Array is a collection of similar data elements stored in contiguous memory locations.

All elements in an array must have the same data type.

---

# Real-World Examples

Arrays are used everywhere:

### Student Marks

```text
85 90 78 88 92
```

---

### Monthly Sales

```text
12000 15000 18000 17000 22000
```

---

### Temperature Records

```text
32 34 30 28 35
```

---

### Employee IDs

```text
101 102 103 104 105
```

Instead of creating separate variables, all values can be stored in an array.

---

# Why Do We Need Arrays?

Without Arrays:

```java
int mark1 = 85;
int mark2 = 90;
int mark3 = 78;
int mark4 = 88;
int mark5 = 92;
```

With Arrays:

```java
int[] marks = {85, 90, 78, 88, 92};
```

Advantages:

* Less code
* Easy data management
* Easy looping
* Better memory organization

---

# Array Declaration

## Syntax

```java
dataType[] arrayName;
```

### Example

```java
int[] marks;
```

This only declares the array.

Memory is not allocated yet.

---

# Array Creation

## Syntax

```java
arrayName = new dataType[size];
```

### Example

```java
marks = new int[5];
```

This creates an array capable of storing 5 integers.

---

# Declaration and Creation Together

```java
int[] marks = new int[5];
```

---

# Memory Representation

```text
Index      0    1    2    3    4
          ------------------------
Marks      0    0    0    0    0
```

Default values:

```text
int      → 0
double   → 0.0
boolean  → false
String   → null
```

---

# Initializing an Array

Values can be assigned individually.

```java
int[] marks = new int[5];

marks[0] = 85;
marks[1] = 90;
marks[2] = 78;
marks[3] = 88;
marks[4] = 92;
```

---

# Shortcut Initialization

```java
int[] marks = {85, 90, 78, 88, 92};
```

---

# Accessing Array Elements

Array elements are accessed using indexes.

```java
arrayName[index]
```

Example:

```java
int[] marks = {85, 90, 78, 88, 92};

System.out.println(marks[0]);
```

### Output

```text
85
```

---

# Important Rule

Array indexing starts from **0**.

```text
Index      0    1    2    3    4
Value     85   90   78   88   92
```

---

# Example 1: Student Marks

```java
public class StudentMarks {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        System.out.println("First Student: "
                           + marks[0]);

        System.out.println("Second Student: "
                           + marks[1]);

        System.out.println("Third Student: "
                           + marks[2]);
    }
}
```

### Output

```text
First Student: 85
Second Student: 90
Third Student: 78
```

---

# Array Length

The length property gives the number of elements.

```java
int[] marks = {85, 90, 78, 88, 92};

System.out.println(marks.length);
```

### Output

```text
5
```

---

# Example 2: Display All Elements

```java
public class ArrayDisplay {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        for(int i = 0;
            i < marks.length;
            i++)
        {
            System.out.println(marks[i]);
        }
    }
}
```

### Output

```text
85
90
78
88
92
```

---

# Real-World Scenario: Store Monthly Sales

```java
public class Sales {

    public static void main(String[] args) {

        int[] sales =
        {
            12000,
            15000,
            18000,
            17000,
            22000
        };

        for(int i = 0;
            i < sales.length;
            i++)
        {
            System.out.println(
                "Month " + (i + 1)
                + ": ₹" + sales[i]
            );
        }
    }
}
```

### Output

```text
Month 1: ₹12000
Month 2: ₹15000
Month 3: ₹18000
Month 4: ₹17000
Month 5: ₹22000
```

---

# User Input Example

```java
import java.util.Scanner;

public class ArrayInput {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int[] marks = new int[5];

        for(int i = 0; i < 5; i++)
        {
            System.out.print(
                "Enter Mark " + (i + 1) + ": "
            );

            marks[i] = sc.nextInt();
        }

        System.out.println("\nEntered Marks:");

        for(int i = 0; i < 5; i++)
        {
            System.out.println(marks[i]);
        }

        sc.close();
    }
}
```

---

# Common Errors

## Array Index Out Of Bounds

❌ Incorrect

```java
int[] marks = {85,90,78};

System.out.println(marks[5]);
```

Error:

```text
ArrayIndexOutOfBoundsException
```

---

✅ Correct

```java
System.out.println(marks[2]);
```

---

# Advantages of Arrays

* Stores multiple values
* Easy iteration using loops
* Better memory management
* Reduces code duplication
* Faster access using indexes

---

# Real-World Applications

Arrays are used in:

* Student Management Systems
* Banking Applications
* Inventory Systems
* Sales Tracking
* Employee Records
* Weather Monitoring Systems
* Data Analytics

---

# Challenge Exercises

### Challenge 1

Store 10 student marks in an array.

---

### Challenge 2

Store monthly sales data and display all values.

---

### Challenge 3

Find the highest mark from an array.

---

### Challenge 4

Find the lowest mark from an array.

---

### Challenge 5

Calculate the total and average of marks stored in an array.

---

# Summary

* Arrays store multiple values of the same data type.
* Indexing starts from 0.
* Arrays have a fixed size.
* Elements can be accessed using indexes.
* Arrays work efficiently with loops.

---

# Conclusion

Arrays are one of the most important data structures in Java. They help organize, store, and process large amounts of related data efficiently. Understanding arrays is essential before learning advanced concepts such as multidimensional arrays, collections, and data structures.
