# Array Operations in Java

After learning how to create and access arrays, the next step is understanding how to perform operations on them.

In real-world applications, arrays are rarely used just for storing data. We usually perform operations such as:

* Traversing
* Searching
* Updating
* Finding Maximum
* Finding Minimum
* Calculating Sum
* Calculating Average

These operations help us analyze and process data efficiently.

---

# What are Array Operations?

Array Operations are actions performed on array elements to retrieve, modify, or analyze data.

---

# Common Array Operations

```text
Array Operations
│
├── Traversing
├── Updating
├── Searching
├── Finding Maximum
├── Finding Minimum
├── Calculating Sum
└── Calculating Average
```

---

# Real-World Scenario

Imagine a Student Management System.

```java
int[] marks = {85, 90, 78, 88, 92};
```

Possible operations:

* Display all marks
* Update a student's mark
* Search for a particular mark
* Find highest mark
* Find lowest mark
* Calculate total marks
* Calculate average marks

---

# 1. Traversing an Array

Traversing means visiting every element of an array.

---

## Example

```java
public class TraversingArray {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        for(int i = 0; i < marks.length; i++)
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

# Real-World Scenario: Attendance System

Display all student roll numbers.

```java
int[] rollNumbers = {101, 102, 103, 104, 105};

for(int i = 0; i < rollNumbers.length; i++)
{
    System.out.println(rollNumbers[i]);
}
```

---

# 2. Updating Array Elements

Array elements can be modified using their index.

---

## Example

```java
public class UpdateArray {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        marks[2] = 95;

        System.out.println(marks[2]);
    }
}
```

### Output

```text
95
```

---

# Real-World Scenario: Correcting Student Marks

Before Update:

```text
78
```

After Revaluation:

```text
95
```

---

# 3. Searching an Element

Searching means finding whether a value exists in an array.

---

## Example

```java
public class SearchArray {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        int searchValue = 88;

        boolean found = false;

        for(int i = 0; i < marks.length; i++)
        {
            if(marks[i] == searchValue)
            {
                found = true;
                break;
            }
        }

        if(found)
        {
            System.out.println("Mark Found");
        }
        else
        {
            System.out.println("Mark Not Found");
        }
    }
}
```

### Output

```text
Mark Found
```

---

# Real-World Scenario: Product Search

An e-commerce website checks whether a product ID exists.

```java
int[] productIds = {101,102,103,104,105};
```

Search:

```text
103
```

Result:

```text
Product Found
```

---

# 4. Finding Maximum Value

Finding the largest value in an array.

---

## Example

```java
public class MaximumValue {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        int max = marks[0];

        for(int i = 1; i < marks.length; i++)
        {
            if(marks[i] > max)
            {
                max = marks[i];
            }
        }

        System.out.println("Highest Mark = " + max);
    }
}
```

### Output

```text
Highest Mark = 92
```

---

# Real-World Scenario: Highest Sales

```java
int[] sales =
{
    12000,
    15000,
    18000,
    17000,
    22000
};
```

Highest Sales:

```text
22000
```

---

# 5. Finding Minimum Value

Finding the smallest value in an array.

---

## Example

```java
public class MinimumValue {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        int min = marks[0];

        for(int i = 1; i < marks.length; i++)
        {
            if(marks[i] < min)
            {
                min = marks[i];
            }
        }

        System.out.println("Lowest Mark = " + min);
    }
}
```

### Output

```text
Lowest Mark = 78
```

---

# Real-World Scenario: Lowest Temperature

```java
int[] temperatures =
{
    32,
    35,
    28,
    30,
    34
};
```

Lowest Temperature:

```text
28
```

---

# 6. Calculating Sum

Sum means adding all elements.

---

## Example

```java
public class ArraySum {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        int sum = 0;

        for(int i = 0; i < marks.length; i++)
        {
            sum += marks[i];
        }

        System.out.println("Total Marks = " + sum);
    }
}
```

### Output

```text
Total Marks = 433
```

---

# Real-World Scenario: Monthly Sales

```java
int[] sales =
{
    12000,
    15000,
    18000,
    17000,
    22000
};
```

Total Sales:

```text
84000
```

---

# 7. Calculating Average

Average is calculated as:

```text
Average = Sum / Number of Elements
```

---

## Example

```java
public class AverageMarks {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        int sum = 0;

        for(int i = 0; i < marks.length; i++)
        {
            sum += marks[i];
        }

        double average =
                (double) sum / marks.length;

        System.out.println(
                "Average = " + average);
    }
}
```

### Output

```text
Average = 86.6
```

---

# Mini Project: Student Result Analysis

### Problem

A school wants to:

* Display all marks
* Find highest mark
* Find lowest mark
* Calculate total marks
* Calculate average marks

---

## Solution

```java
public class StudentAnalysis {

    public static void main(String[] args) {

        int[] marks = {85, 90, 78, 88, 92};

        int sum = 0;
        int max = marks[0];
        int min = marks[0];

        for(int i = 0; i < marks.length; i++)
        {
            sum += marks[i];

            if(marks[i] > max)
            {
                max = marks[i];
            }

            if(marks[i] < min)
            {
                min = marks[i];
            }
        }

        double average =
                (double) sum / marks.length;

        System.out.println("Highest = " + max);
        System.out.println("Lowest = " + min);
        System.out.println("Total = " + sum);
        System.out.println("Average = " + average);
    }
}
```

### Output

```text
Highest = 92
Lowest = 78
Total = 433
Average = 86.6
```

---

# Real-World Applications

Array Operations are widely used in:

* Student Management Systems
* Banking Applications
* Inventory Systems
* Sales Analysis
* Weather Monitoring
* Employee Management
* Data Analytics

---

# Challenge Exercises

### Challenge 1

Find the highest number in an array.

---

### Challenge 2

Find the lowest number in an array.

---

### Challenge 3

Calculate total sales for 12 months.

---

### Challenge 4

Search for a product ID in an array.

---

### Challenge 5

Calculate the average marks of students.

---

# Summary

* Traversing accesses all elements.
* Updating modifies existing elements.
* Searching finds a value.
* Maximum and Minimum identify extreme values.
* Sum calculates the total.
* Average provides overall performance.

---

# Conclusion

Array Operations are essential for processing and analyzing data. Almost every real-world software application performs these operations to generate reports, analyze trends, manage records, and support decision-making.
