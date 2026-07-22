 # Nested Loops in Java

In many real-world applications, a single loop is not enough.

Sometimes, we need a loop inside another loop to perform repetitive tasks in multiple dimensions.

This concept is called **Nested Loops**.

--- 

# What is a Nested Loop?

A Nested Loop is a loop inside another loop.

The outer loop executes first.

For every iteration of the outer loop, the inner loop executes completely.

---

# Syntax

```java
for(initialization1; condition1; update1)
{
    for(initialization2; condition2; update2)
    {
        // code
    }
}
```

---

# How Nested Loops Work

```text
Outer Loop (1)
    Inner Loop Executes Completely

Outer Loop (2)
    Inner Loop Executes Completely

Outer Loop (3)
    Inner Loop Executes Completely
```

---

# Real-World Example

Imagine a school.

* 3 Classrooms
* Each classroom has 5 Students

To display every student in every classroom:

```text
Classroom 1
 Student 1
 Student 2
 Student 3
 Student 4
 Student 5

Classroom 2
 Student 1
 Student 2
 Student 3
 Student 4
 Student 5

Classroom 3
 Student 1
 Student 2
 Student 3
 Student 4
 Student 5
```

Nested loops are ideal for such situations.

---

# Example 1: Basic Nested Loop

```java
public class NestedLoopDemo {

    public static void main(String[] args) {

        for(int i = 1; i <= 3; i++)
        {
            for(int j = 1; j <= 2; j++)
            {
                System.out.println("i = " + i +
                                   ", j = " + j);
            }
        }
    }
}
```

### Output

```text
i = 1, j = 1
i = 1, j = 2
i = 2, j = 1
i = 2, j = 2
i = 3, j = 1
i = 3, j = 2
```

---

# Understanding Execution

Outer Loop:

```java
i = 1
```

Inner Loop:

```java
j = 1
j = 2
```

After inner loop completes:

```java
i = 2
```

Again:

```java
j = 1
j = 2
```

This process continues until the outer loop ends.

---

# Real-World Scenario 1: School Attendance System

A school has:

* 3 Classes
* 4 Students in each Class

```java
public class AttendanceSystem {

    public static void main(String[] args) {

        for(int classroom = 1;
            classroom <= 3;
            classroom++)
        {
            System.out.println(
                "Classroom " + classroom);

            for(int student = 1;
                student <= 4;
                student++)
            {
                System.out.println(
                    "Student " + student);
            }

            System.out.println();
        }
    }
}
```

### Output

```text
Classroom 1
Student 1
Student 2
Student 3
Student 4

Classroom 2
Student 1
Student 2
Student 3
Student 4

Classroom 3
Student 1
Student 2
Student 3
Student 4
```

---

# Real-World Scenario 2: Multiplication Tables

Generate tables from 1 to 5.

```java
public class MultiplicationTables {

    public static void main(String[] args) {

        for(int table = 1;
            table <= 5;
            table++)
        {
            System.out.println(
                "\nTable of " + table);

            for(int i = 1;
                i <= 10;
                i++)
            {
                System.out.println(
                    table + " x " + i +
                    " = " + (table * i));
            }
        }
    }
}
```

---

# Real-World Scenario 3: Cinema Seating Arrangement

A theater contains:

* 5 Rows
* 10 Seats per Row

```java
public class TheatreSeats {

    public static void main(String[] args) {

        for(int row = 1;
            row <= 5;
            row++)
        {
            System.out.println(
                "Row " + row);

            for(int seat = 1;
                seat <= 10;
                seat++)
            {
                System.out.print(
                    "Seat" + seat + " ");
            }

            System.out.println();
        }
    }
}
```

---

# Pattern Programming

Nested loops are heavily used in pattern problems.

---

# Example 2: Square Pattern

```java
public class SquarePattern {

    public static void main(String[] args) {

        for(int i = 1; i <= 5; i++)
        {
            for(int j = 1; j <= 5; j++)
            {
                System.out.print("* ");
            }

            System.out.println();
        }
    }
}
```

### Output

```text
* * * * *
* * * * *
* * * * *
* * * * *
* * * * *
```

---

# Example 3: Number Pattern

```java
public class NumberPattern {

    public static void main(String[] args) {

        for(int i = 1; i <= 5; i++)
        {
            for(int j = 1; j <= i; j++)
            {
                System.out.print(j + " ");
            }

            System.out.println();
        }
    }
}
```

### Output

```text
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

---

# Example 4: Star Triangle

```java
public class StarTriangle {

    public static void main(String[] args) {

        for(int i = 1; i <= 5; i++)
        {
            for(int j = 1; j <= i; j++)
            {
                System.out.print("* ");
            }

            System.out.println();
        }
    }
}
```

### Output

```text
*
* *
* * *
* * * *
* * * * *
```

---

# Real-World Scenario 4: Online Shopping Orders

Suppose:

* 3 Customers
* Each customer orders 2 products

```java
public class Orders {

    public static void main(String[] args) {

        for(int customer = 1;
            customer <= 3;
            customer++)
        {
            System.out.println(
                "Customer " + customer);

            for(int product = 1;
                product <= 2;
                product++)
            {
                System.out.println(
                    "Product " + product);
            }
        }
    }
}
```

---

# Nested While Loops

Nested loops are not limited to for loops.

---

## Example

```java
public class NestedWhile {

    public static void main(String[] args) {

        int i = 1;

        while(i <= 3)
        {
            int j = 1;

            while(j <= 3)
            {
                System.out.print(j + " ");
                j++;
            }

            System.out.println();

            i++;
        }
    }
}
```

### Output

```text
1 2 3
1 2 3
1 2 3
```

---

# Common Mistakes

## Infinite Inner Loop

❌ Incorrect

```java
for(int i = 1; i <= 3; i++)
{
    int j = 1;

    while(j <= 3)
    {
        System.out.println(j);
    }
}
```

Update missing.

Infinite loop occurs.

---

✅ Correct

```java
while(j <= 3)
{
    System.out.println(j);
    j++;
}
```

---

# Real-World Applications

Nested Loops are used in:

* Matrix Operations
* Game Development
* Seating Arrangements
* Pattern Printing
* School Management Systems
* Inventory Systems
* Ticket Booking Applications
* Data Processing

---

# Challenge Exercises

### Challenge 1

Print a square pattern of size 10.

---

### Challenge 2

Print multiplication tables from 1 to 10.

---

### Challenge 3

Create a classroom attendance system.

---

### Challenge 4

Create a seating arrangement for:

* 8 Rows
* 12 Seats per Row

---

### Challenge 5

Print the following pattern:

```text
1
12
123
1234
12345
```

---

# Summary

* A Nested Loop is a loop inside another loop.
* The inner loop executes completely for every iteration of the outer loop.
* Commonly used for patterns, tables, matrices, and multi-level data processing.
* Can be created using for, while, or do-while loops.

---

# Conclusion

Nested Loops are powerful structures used when repetitive operations need to occur within other repetitive operations. They are essential for pattern generation, matrix processing, seating arrangements, reporting systems, and many real-world software applications.
