# For Loop in Java

Imagine you are a teacher who wants to print the numbers from 1 to 100.

Without loops, you would have to write:

```java
System.out.println(1);
System.out.println(2);
System.out.println(3);
...
System.out.println(100);
```

This is repetitive, time-consuming, and difficult to maintain.

Java provides loops to execute a block of code repeatedly.

One of the most commonly used loops is the **For Loop**.

---

# What is a For Loop?

A For Loop is used when the number of iterations is known in advance.

It repeatedly executes a block of code until a specified condition becomes false.

---

# Syntax

```java
for(initialization; condition; update)
{
    // code
}
```

---

# Components of a For Loop

## 1. Initialization

Executed only once at the beginning.

```java
int i = 1;
```

---

## 2. Condition

Checked before every iteration.

```java
i <= 5
```

If true → loop continues.

If false → loop stops.

---

## 3. Update

Executed after every iteration.

```java
i++
```

---

# Flow Diagram

```text
Initialization
      ↓
  Condition
      ↓
   True?
      ↓
 Execute Code
      ↓
    Update
      ↓
 Back to Condition
```

---

# Example 1: Print Numbers from 1 to 5

```java
public class ForLoopExample {

    public static void main(String[] args) {

        for(int i = 1; i <= 5; i++)
        {
            System.out.println(i);
        }
    }
}
```

### Output

```text
1
2
3
4
5
```

---

# How It Works

### Iteration 1

```java
i = 1
```

Condition:

```java
1 <= 5
```

True

Output:

```text
1
```

Update:

```java
i++
```

Now:

```java
i = 2
```

The process continues until `i = 6`.

Condition becomes false.

Loop stops.

---

# Real-World Scenario 1: Attendance System

A teacher wants to display roll numbers.

```java
public class Attendance {

    public static void main(String[] args) {

        for(int rollNo = 1; rollNo <= 5; rollNo++)
        {
            System.out.println("Student Roll No: " + rollNo);
        }
    }
}
```

### Output

```text
Student Roll No: 1
Student Roll No: 2
Student Roll No: 3
Student Roll No: 4
Student Roll No: 5
```

---

# Real-World Scenario 2: Online Order Processing

Suppose an e-commerce company receives 10 orders.

```java
public class OrderProcessing {

    public static void main(String[] args) {

        for(int order = 1; order <= 10; order++)
        {
            System.out.println("Processing Order " + order);
        }
    }
}
```

### Output

```text
Processing Order 1
Processing Order 2
...
Processing Order 10
```

---

# Example 2: Print Even Numbers

```java
public class EvenNumbers {

    public static void main(String[] args) {

        for(int i = 2; i <= 20; i += 2)
        {
            System.out.println(i);
        }
    }
}
```

### Output

```text
2
4
6
8
10
12
14
16
18
20
```

---

# Example 3: Multiplication Table

```java
public class MultiplicationTable {

    public static void main(String[] args) {

        int number = 5;

        for(int i = 1; i <= 10; i++)
        {
            System.out.println(number + " x " + i + " = " + (number * i));
        }
    }
}
```

### Output

```text
5 x 1 = 5
5 x 2 = 10
...
5 x 10 = 50
```

---

# Real-World Scenario 3: Employee Salary Calculation

A company wants to calculate monthly salary for 12 months.

```java
public class SalaryReport {

    public static void main(String[] args) {

        for(int month = 1; month <= 12; month++)
        {
            System.out.println("Generating Salary for Month " + month);
        }
    }
}
```

---

# Example 4: Reverse Counting

```java
public class ReverseCount {

    public static void main(String[] args) {

        for(int i = 10; i >= 1; i--)
        {
            System.out.println(i);
        }
    }
}
```

### Output

```text
10
9
8
7
6
5
4
3
2
1
```

---

# User Input Example

```java
import java.util.Scanner;

public class NumberPrinter {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Limit: ");

        int limit = sc.nextInt();

        for(int i = 1; i <= limit; i++)
        {
            System.out.println(i);
        }

        sc.close();
    }
}
```

### Sample Output

```text
Enter Limit: 5

1
2
3
4
5
```

---

# Common Mistakes

## Infinite Loop

❌ Incorrect

```java
for(int i = 1; i <= 5;)
{
    System.out.println(i);
}
```

No update statement.

Loop never ends.

---

✅ Correct

```java
for(int i = 1; i <= 5; i++)
{
    System.out.println(i);
}
```

---

# Challenge Exercises

### Challenge 1

Print numbers from 1 to 50.

---

### Challenge 2

Print even numbers from 1 to 100.

---

### Challenge 3

Print odd numbers from 1 to 100.

---

### Challenge 4

Generate multiplication table for any number.

---

### Challenge 5

Display employee IDs from 1001 to 1010.

---

# Summary

* For Loop is used when the number of iterations is known.
* It consists of initialization, condition, and update.
* It reduces repetitive code.
* Commonly used in reports, calculations, attendance systems, and data processing.

---

# Conclusion

The For Loop is one of the most powerful and frequently used looping constructs in Java. It helps automate repetitive tasks efficiently and is widely used in real-world applications such as payroll systems, report generation, order processing, and data analysis.
