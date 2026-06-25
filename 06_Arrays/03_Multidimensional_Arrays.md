# Multidimensional Arrays in Java

In the previous lessons, we learned about one-dimensional arrays, which store data in a single row.

However, many real-world applications require data to be stored in rows and columns.

For example:

* Student marks of multiple subjects
* Seating arrangement in a classroom
* Chess board
* Monthly sales of different branches
* Image pixels

To handle such data, Java provides **Multidimensional Arrays**.

---

# What is a Multidimensional Array?

A Multidimensional Array is an array that contains one or more arrays as its elements.

The most commonly used multidimensional array is the **Two-Dimensional (2D) Array**.

A 2D array stores data in the form of rows and columns.

---

# Real-World Example

Imagine a classroom with 3 students and their marks in 4 subjects.

```text
           Math   Science   English   Computer

Student 1    90      85        88         92

Student 2    78      80        75         82

Student 3    95      91        89         96
```

This data is naturally represented as a 2D array.

---

# Why Do We Need Multidimensional Arrays?

Without 2D arrays:

```java
int student1Math = 90;
int student1Science = 85;
int student2Math = 78;
...
```

This becomes difficult to manage.

With 2D arrays:

```java
int[][] marks =
{
    {90,85,88,92},
    {78,80,75,82},
    {95,91,89,96}
};
```

Advantages:

* Organized data storage
* Easy access using row and column indexes
* Simplifies matrix-related problems
* Ideal for tabular data

---

# Declaration

## Syntax

```java
dataType[][] arrayName;
```

Example:

```java
int[][] marks;
```

---

# Creating a 2D Array

```java
int[][] marks = new int[3][4];
```

Explanation:

* 3 → Rows
* 4 → Columns

---

# Memory Representation

```text
        Column

         0    1    2    3

Row 0   [ ]  [ ]  [ ]  [ ]

Row 1   [ ]  [ ]  [ ]  [ ]

Row 2   [ ]  [ ]  [ ]  [ ]
```

---

# Initializing a 2D Array

```java
int[][] marks =
{
    {90,85,88,92},
    {78,80,75,82},
    {95,91,89,96}
};
```

---

# Accessing Elements

Syntax:

```java
arrayName[row][column]
```

Example:

```java
System.out.println(marks[0][2]);
```

Output

```text
88
```

---

# Understanding Indexes

```text
          0    1    2    3

0        90   85   88   92

1        78   80   75   82

2        95   91   89   96
```

Example

```java
marks[2][1]
```

Output

```text
91
```

---

# Example 1: Display One Element

```java
public class TwoDArray {

    public static void main(String[] args) {

        int[][] marks =
        {
            {90,85,88},
            {78,80,75},
            {95,91,89}
        };

        System.out.println(marks[1][2]);
    }
}
```

### Output

```text
75
```

---

# Traversing a 2D Array

Nested loops are used.

```java
public class DisplayMatrix {

    public static void main(String[] args) {

        int[][] matrix =
        {
            {1,2,3},
            {4,5,6},
            {7,8,9}
        };

        for(int i = 0; i < matrix.length; i++)
        {
            for(int j = 0; j < matrix[i].length; j++)
            {
                System.out.print(matrix[i][j] + " ");
            }

            System.out.println();
        }
    }
}
```

### Output

```text
1 2 3

4 5 6

7 8 9
```

---

# Real-World Scenario 1: Student Marks

```java
public class StudentMarks {

    public static void main(String[] args) {

        int[][] marks =
        {
            {90,85,88},
            {78,80,75},
            {95,91,89}
        };

        for(int student = 0;
            student < marks.length;
            student++)
        {
            System.out.println(
                "Student " + (student + 1));

            for(int subject = 0;
                subject < marks[student].length;
                subject++)
            {
                System.out.print(
                    marks[student][subject] + " ");
            }

            System.out.println("\n");
        }
    }
}
```

---

# Real-World Scenario 2: Cinema Seating

Imagine a theatre with:

* 4 Rows
* 5 Seats

```java
public class Theatre {

    public static void main(String[] args) {

        int[][] seats = new int[4][5];

        for(int row = 0;
            row < seats.length;
            row++)
        {
            for(int seat = 0;
                seat < seats[row].length;
                seat++)
            {
                seats[row][seat] = 1;
            }
        }

        System.out.println(
            "All seats reserved."
        );
    }
}
```

---

# Real-World Scenario 3: Monthly Sales

```java
public class Sales {

    public static void main(String[] args) {

        int[][] sales =
        {
            {12000,15000,17000},
            {18000,20000,21000},
            {22000,24000,26000}
        };

        for(int branch = 0;
            branch < sales.length;
            branch++)
        {
            System.out.println(
                "Branch " + (branch + 1));

            for(int month = 0;
                month < sales[branch].length;
                month++)
            {
                System.out.print(
                    sales[branch][month] + " ");
            }

            System.out.println("\n");
        }
    }
}
```

---

# Taking User Input

```java
import java.util.Scanner;

public class MatrixInput {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int[][] matrix = new int[2][3];

        System.out.println("Enter Matrix:");

        for(int i = 0; i < matrix.length; i++)
        {
            for(int j = 0; j < matrix[i].length; j++)
            {
                matrix[i][j] = sc.nextInt();
            }
        }

        System.out.println("\nMatrix:");

        for(int i = 0; i < matrix.length; i++)
        {
            for(int j = 0; j < matrix[i].length; j++)
            {
                System.out.print(matrix[i][j] + " ");
            }

            System.out.println();
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
matrix[3][2]
```

Error

```text
ArrayIndexOutOfBoundsException
```

---

## Using Wrong Loop Limits

Always use

```java
matrix.length
```

for rows.

Use

```java
matrix[i].length
```

for columns.

---

# Advantages

* Represents tabular data efficiently.
* Easy to perform matrix operations.
* Better organization of related data.
* Simplifies nested data processing.

---

# Real-World Applications

Multidimensional arrays are used in:

* Student Management Systems
* Banking Reports
* Image Processing
* Chess Games
* Sudoku Games
* Weather Forecasting
* Inventory Management
* Seating Arrangements
* Matrix Calculations

---

# Challenge Exercises

### Challenge 1

Create a 3 × 3 matrix and display it.

---

### Challenge 2

Accept marks of 5 students in 4 subjects.

Display all marks.

---

### Challenge 3

Find the total marks of each student.

---

### Challenge 4

Find the highest value in a matrix.

---

### Challenge 5

Create a seating arrangement system for:

* 10 Rows
* 8 Seats

---

# Summary

* A Multidimensional Array is an array of arrays.
* A 2D array stores data in rows and columns.
* Elements are accessed using row and column indexes.
* Nested loops are used to traverse 2D arrays.
* Widely used for matrix operations and tabular data.

---

# Conclusion

Multidimensional Arrays are an essential part of Java programming when working with structured data. They provide an efficient way to represent tables, matrices, reports, and other real-world datasets. Mastering multidimensional arrays prepares you for advanced topics such as matrix algorithms, image processing, game development, and data analysis.
