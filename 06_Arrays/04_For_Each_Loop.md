# For-Each Loop in Java

In the previous lessons, we learned how to traverse arrays using the traditional **for loop**.

Although the for loop is powerful, writing indexes repeatedly is unnecessary when we only need to read every element of an array.

To simplify iteration, Java introduced the **For-Each Loop**, also known as the **Enhanced For Loop**.

---

# What is a For-Each Loop?

The For-Each Loop is a special loop designed to iterate through every element of an array or collection without using indexes.

It automatically accesses each element one by one.

---

# Why Do We Need a For-Each Loop?

Consider an array of student marks.

```java
int[] marks = {85, 90, 78, 88, 92};
```

Using a normal for loop:

```java
for(int i = 0; i < marks.length; i++)
{
    System.out.println(marks[i]);
}
```

Using a For-Each Loop:

```java
for(int mark : marks)
{
    System.out.println(mark);
}
```

The second approach is shorter, cleaner, and easier to understand.

---

# Syntax

```java
for(dataType variable : array)
{
    // code
}
```

---

# Syntax Explanation

| Part     | Description                     |
| -------- | ------------------------------- |
| dataType | Data type of array elements     |
| variable | Stores each element temporarily |
| array    | Array being traversed           |

---

# How For-Each Loop Works

```text
Array

85 90 78 88 92

↓

mark = 85

↓

mark = 90

↓

mark = 78

↓

mark = 88

↓

mark = 92

↓

Loop Ends
```

---

# Example 1: Display Array Elements

```java
public class ForEachExample {

    public static void main(String[] args) {

        int[] numbers = {10,20,30,40,50};

        for(int number : numbers)
        {
            System.out.println(number);
        }

    }

}
```

### Output

```text
10
20
30
40
50
```

---

# Step-by-Step Execution

Array

```text
10 20 30 40 50
```

Iteration 1

```text
number = 10
```

Iteration 2

```text
number = 20
```

Iteration 3

```text
number = 30
```

...

Until every element is processed.

---

# Real-World Scenario 1: Student Marks

A teacher wants to display marks of all students.

```java
public class StudentMarks {

    public static void main(String[] args) {

        int[] marks = {85,90,78,88,92};

        for(int mark : marks)
        {
            System.out.println("Mark : " + mark);
        }

    }

}
```

### Output

```text
Mark : 85
Mark : 90
Mark : 78
Mark : 88
Mark : 92
```

---

# Real-World Scenario 2: Employee IDs

```java
public class Employee {

    public static void main(String[] args) {

        int[] employeeIds =
        {
            101,
            102,
            103,
            104,
            105
        };

        for(int id : employeeIds)
        {
            System.out.println("Employee ID : " + id);
        }

    }

}
```

---

# Real-World Scenario 3: Monthly Sales

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

        for(int amount : sales)
        {
            System.out.println("₹" + amount);
        }

    }

}
```

### Output

```text
₹12000
₹15000
₹18000
₹17000
₹22000
```

---

# Finding Sum Using For-Each

```java
public class SumArray {

    public static void main(String[] args) {

        int[] numbers = {10,20,30,40,50};

        int sum = 0;

        for(int number : numbers)
        {
            sum += number;
        }

        System.out.println("Sum = " + sum);

    }

}
```

### Output

```text
Sum = 150
```

---

# Finding Average

```java
public class Average {

    public static void main(String[] args) {

        int[] marks = {85,90,78,88,92};

        int sum = 0;

        for(int mark : marks)
        {
            sum += mark;
        }

        double average =
                (double)sum / marks.length;

        System.out.println("Average = " + average);

    }

}
```

### Output

```text
Average = 86.6
```

---

# Using For-Each with Strings

```java
public class Fruits {

    public static void main(String[] args) {

        String[] fruits =
        {
            "Apple",
            "Banana",
            "Orange",
            "Mango"
        };

        for(String fruit : fruits)
        {
            System.out.println(fruit);
        }

    }

}
```

### Output

```text
Apple
Banana
Orange
Mango
```

---

# Using For-Each with Multidimensional Arrays

```java
public class Matrix {

    public static void main(String[] args) {

        int[][] matrix =
        {
            {1,2,3},
            {4,5,6},
            {7,8,9}
        };

        for(int[] row : matrix)
        {
            for(int value : row)
            {
                System.out.print(value + " ");
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

# Difference Between For Loop and For-Each Loop

| For Loop                   | For-Each Loop                   |
| -------------------------- | ------------------------------- |
| Uses index                 | No index                        |
| Can modify elements        | Mainly used for reading         |
| More flexible              | Simpler syntax                  |
| Suitable for any iteration | Best for arrays and collections |

---

# Limitations of For-Each Loop

You cannot:

* Access index directly
* Traverse in reverse order
* Skip elements easily
* Modify array elements using the loop variable

Example:

```java
for(int number : numbers)
{
    number = number * 2;
}
```

This does **not** modify the original array.

---

# Common Mistakes

## Mistake 1

Trying to access the index.

❌ Incorrect

```java
for(int number : numbers)
{
    System.out.println(numbers[number]);
}
```

---

## Correct

```java
for(int number : numbers)
{
    System.out.println(number);
}
```

---

# Real-World Applications

The For-Each Loop is commonly used in:

* Student Management Systems
* Banking Applications
* Inventory Systems
* Employee Records
* Sales Reports
* Weather Data Analysis
* Data Analytics
* Java Collections Framework

---

# Challenge Exercises

### Challenge 1

Display all student names using a For-Each Loop.

---

### Challenge 2

Find the total marks using a For-Each Loop.

---

### Challenge 3

Display all employee IDs.

---

### Challenge 4

Display all monthly sales values.

---

### Challenge 5

Display all values in a 2D matrix using nested For-Each Loops.

---

# Summary

* The For-Each Loop is also called the Enhanced For Loop.
* It is used to traverse arrays and collections.
* It automatically accesses each element.
* It improves code readability.
* It is best suited for reading data.

---

# Conclusion

The For-Each Loop simplifies array traversal by eliminating the need for indexes. It makes Java code cleaner, easier to read, and less error-prone. It is widely used in real-world applications where array elements need to be processed sequentially without modifying their positions.
