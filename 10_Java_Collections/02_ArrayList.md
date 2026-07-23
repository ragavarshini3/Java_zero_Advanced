# ArrayList in Java

`ArrayList` is one of the most commonly used classes in the Java Collections Framework.

It is used to store a group of elements in a **dynamic array**.

Unlike a normal Java array, the size of an `ArrayList` can automatically increase or decrease when elements are added or removed.

---

# What is an ArrayList?

An `ArrayList` is a resizable array provided by the `java.util` package.

It implements the `List` interface.

Example:

```java
ArrayList<String> students = new ArrayList<>();
```

We can dynamically add values:

```java
students.add("Anu");
students.add("Bala");
students.add("Charan");
```

---

# Importing ArrayList

Before using `ArrayList`, import it:

```java
import java.util.ArrayList;
```

---

# Syntax

```java
ArrayList<DataType> listName = new ArrayList<>();
```

Example:

```java
ArrayList<String> names = new ArrayList<>();
```

For integers:

```java
ArrayList<Integer> numbers = new ArrayList<>();
```

For decimal values:

```java
ArrayList<Double> prices = new ArrayList<>();
```

---

# Basic ArrayList Example

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        System.out.println(students);
    }
}
```

### Output

```text
[Anu, Bala, Charan]
```

---

# How ArrayList Works

Suppose we create:

```java
ArrayList<String> fruits = new ArrayList<>();
```

Initially:

```text
[]
```

Add Apple:

```java
fruits.add("Apple");
```

Now:

```text
Index      0
         Apple
```

Add Banana:

```java
fruits.add("Banana");
```

Now:

```text
Index      0        1
         Apple    Banana
```

Add Mango:

```java
fruits.add("Mango");
```

Now:

```text
Index      0        1        2
         Apple    Banana    Mango
```

ArrayList uses **zero-based indexing**.

The first element is at index `0`.

---

# Important Features of ArrayList

`ArrayList`:

- Has dynamic size
- Maintains insertion order
- Allows duplicate values
- Allows `null` values
- Supports index-based access
- Provides many built-in methods

---

# Adding Elements

Use the `add()` method.

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> fruits = new ArrayList<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");

        System.out.println(fruits);
    }
}
```

### Output

```text
[Apple, Banana, Mango]
```

---

# Adding an Element at a Specific Index

Syntax:

```java
list.add(index, value);
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> fruits = new ArrayList<>();

        fruits.add("Apple");
        fruits.add("Mango");

        fruits.add(1, "Banana");

        System.out.println(fruits);
    }
}
```

### Output

```text
[Apple, Banana, Mango]
```

`Banana` is inserted at index `1`.

---

# Accessing Elements

Use the `get()` method.

Syntax:

```java
list.get(index);
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        System.out.println(students.get(0));

        System.out.println(students.get(2));
    }
}
```

### Output

```text
Anu
Charan
```

---

# Updating an Element

Use the `set()` method.

Syntax:

```java
list.set(index, newValue);
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        students.set(1, "Priya");

        System.out.println(students);
    }
}
```

### Output

```text
[Anu, Priya, Charan]
```

`Bala` is replaced by `Priya`.

---

# Removing an Element by Index

Use:

```java
remove(index);
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> fruits = new ArrayList<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");

        fruits.remove(1);

        System.out.println(fruits);
    }
}
```

### Output

```text
[Apple, Mango]
```

---

# Removing an Element by Value

You can also remove an element using its value.

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> fruits = new ArrayList<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");

        fruits.remove("Banana");

        System.out.println(fruits);
    }
}
```

### Output

```text
[Apple, Mango]
```

---

# Finding the Size of ArrayList

Use:

```java
size()
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        System.out.println(
            "Total Students: " + students.size()
        );
    }
}
```

### Output

```text
Total Students: 3
```

---

# Checking Whether an Element Exists

Use:

```java
contains()
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> courses = new ArrayList<>();

        courses.add("Java");
        courses.add("Python");
        courses.add("Data Science");

        System.out.println(courses.contains("Java"));

        System.out.println(courses.contains("C++"));
    }
}
```

### Output

```text
true
false
```

---

# Finding the Index of an Element

Use:

```java
indexOf()
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        System.out.println(students.indexOf("Bala"));
    }
}
```

### Output

```text
1
```

If the element is not found, `indexOf()` returns:

```text
-1
```

---

# Checking Whether ArrayList is Empty

Use:

```java
isEmpty()
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        System.out.println(students.isEmpty());

        students.add("Anu");

        System.out.println(students.isEmpty());
    }
}
```

### Output

```text
true
false
```

---

# Removing All Elements

Use:

```java
clear()
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        System.out.println("Before: " + students);

        students.clear();

        System.out.println("After: " + students);
    }
}
```

### Output

```text
Before: [Anu, Bala, Charan]
After: []
```

---

# Looping Through an ArrayList

There are multiple ways to traverse an `ArrayList`.

---

## Using for Loop

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        for(int i = 0; i < students.size(); i++)
        {
            System.out.println(students.get(i));
        }
    }
}
```

### Output

```text
Anu
Bala
Charan
```

---

## Using Enhanced for Loop

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        for(String student : students)
        {
            System.out.println(student);
        }
    }
}
```

### Output

```text
Anu
Bala
Charan
```

---

# ArrayList with Integer Values

Collections cannot directly use primitive types such as:

```text
int
double
char
boolean
```

We use wrapper classes.

For `int`, use:

```java
Integer
```

Example:

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<Integer> marks = new ArrayList<>();

        marks.add(85);
        marks.add(90);
        marks.add(95);

        System.out.println(marks);
    }
}
```

### Output

```text
[85, 90, 95]
```

---

# Finding Sum of ArrayList Elements

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<Integer> numbers = new ArrayList<>();

        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(40);

        int sum = 0;

        for(int number : numbers)
        {
            sum = sum + number;
        }

        System.out.println("Sum: " + sum);
    }
}
```

### Output

```text
Sum: 100
```

---

# Finding Maximum Element

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<Integer> numbers = new ArrayList<>();

        numbers.add(25);
        numbers.add(80);
        numbers.add(45);
        numbers.add(100);
        numbers.add(60);

        int maximum = numbers.get(0);

        for(int number : numbers)
        {
            if(number > maximum)
            {
                maximum = number;
            }
        }

        System.out.println("Maximum: " + maximum);
    }
}
```

### Output

```text
Maximum: 100
```

---

# Sorting an ArrayList

Use:

```java
Collections.sort()
```

Example:

```java
import java.util.ArrayList;
import java.util.Collections;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<Integer> numbers = new ArrayList<>();

        numbers.add(50);
        numbers.add(10);
        numbers.add(40);
        numbers.add(20);

        Collections.sort(numbers);

        System.out.println(numbers);
    }
}
```

### Output

```text
[10, 20, 40, 50]
```

---

# Real-World Example 1: Student Management System

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Ragavarshini");
        students.add("Priya");
        students.add("Arun");

        System.out.println("Student List:");

        for(String student : students)
        {
            System.out.println(student);
        }

        students.add("Kavin");

        System.out.println(
            "Total Students: " + students.size()
        );
    }
}
```

### Output

```text
Student List:
Ragavarshini
Priya
Arun
Total Students: 4
```

---

# Real-World Example 2: Shopping Cart

Consider an e-commerce website.

A customer adds products to a shopping cart.

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> cart = new ArrayList<>();

        cart.add("Laptop");
        cart.add("Mouse");
        cart.add("Keyboard");

        System.out.println("Cart: " + cart);

        cart.remove("Mouse");

        System.out.println(
            "After Removing Mouse: " + cart
        );

        System.out.println(
            "Total Products: " + cart.size()
        );
    }
}
```

### Output

```text
Cart: [Laptop, Mouse, Keyboard]
After Removing Mouse: [Laptop, Keyboard]
Total Products: 2
```

---

# Real-World Example 3: Student Marks

Suppose we need to calculate the average marks of a student.

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<Integer> marks = new ArrayList<>();

        marks.add(85);
        marks.add(90);
        marks.add(78);
        marks.add(92);
        marks.add(88);

        int total = 0;

        for(int mark : marks)
        {
            total += mark;
        }

        double average =
            (double) total / marks.size();

        System.out.println("Total: " + total);

        System.out.println("Average: " + average);
    }
}
```

### Output

```text
Total: 433
Average: 86.6
```

---

# Real-World Example 4: To-Do List

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> tasks = new ArrayList<>();

        tasks.add("Complete Java Assignment");
        tasks.add("Attend Class");
        tasks.add("Practice Coding");

        System.out.println("Tasks:");

        for(String task : tasks)
        {
            System.out.println(task);
        }

        tasks.remove("Attend Class");

        System.out.println("\nRemaining Tasks:");

        for(String task : tasks)
        {
            System.out.println(task);
        }
    }
}
```

---

# Important ArrayList Methods

| Method | Description |
|---|---|
| `add()` | Adds an element |
| `add(index, value)` | Adds an element at a specific position |
| `get()` | Gets an element |
| `set()` | Updates an element |
| `remove()` | Removes an element |
| `size()` | Returns number of elements |
| `contains()` | Checks whether an element exists |
| `indexOf()` | Finds the index of an element |
| `isEmpty()` | Checks whether the list is empty |
| `clear()` | Removes all elements |

---

# Array vs ArrayList

| Array | ArrayList |
|---|---|
| Fixed size | Dynamic size |
| Uses `length` | Uses `size()` |
| Can store primitives directly | Uses wrapper classes for primitives |
| Fewer built-in operations | Many built-in methods |
| Faster for simple fixed data | More flexible for dynamic data |

Array:

```java
int[] numbers = new int[5];
```

ArrayList:

```java
ArrayList<Integer> numbers = new ArrayList<>();
```

---

# Advantages of ArrayList

- Dynamic size
- Easy to add elements
- Easy to remove elements
- Easy to update values
- Supports duplicate elements
- Maintains insertion order
- Provides index-based access
- Many useful built-in methods

---

# Limitations of ArrayList

`ArrayList` may not be the best choice when:

- Frequent insertion happens at the beginning.
- Frequent deletion happens in the middle.
- Thread-safe operations are required.

For frequent insertions and deletions, `LinkedList` may sometimes be more suitable.

---

# Common Mistakes

## Invalid Index

```java
ArrayList<String> names = new ArrayList<>();

names.add("Anu");

System.out.println(names.get(5));
```

This causes:

```text
IndexOutOfBoundsException
```

Always check:

```java
index < list.size()
```

---

## Using `int` Instead of `Integer`

Incorrect:

```java
ArrayList<int> numbers = new ArrayList<>();
```

Correct:

```java
ArrayList<Integer> numbers = new ArrayList<>();
```

---

# Interview Questions

### What is ArrayList?

`ArrayList` is a resizable array implementation of the `List` interface.

---

### Does ArrayList allow duplicates?

Yes.

---

### Does ArrayList maintain insertion order?

Yes.

---

### Can ArrayList store null values?

Yes.

---

### How do you add an element?

```java
list.add(value);
```

---

### How do you access an element?

```java
list.get(index);
```

---

### How do you update an element?

```java
list.set(index, value);
```

---

### How do you find the size?

```java
list.size();
```

---

# Challenge 1: Student Names

Create an `ArrayList` containing five student names.

Display all names using an enhanced `for` loop.

---

# Challenge 2: Find Maximum

Create an `ArrayList<Integer>` containing:

```text
20
55
10
90
45
```

Find and display the maximum value.

Expected Output:

```text
Maximum: 90
```

---

# Challenge 3: Shopping Cart

Create a shopping cart using `ArrayList`.

Perform:

```text
Add Laptop
Add Mouse
Add Keyboard
Remove Mouse
Display remaining products
```

Expected Output:

```text
[Laptop, Keyboard]
```

---

# Challenge 4: Search Student

Create an ArrayList:

```text
Anu
Bala
Charan
Divya
```

Ask the user to enter a student name.

Check whether the student exists using:

```java
contains()
```

---

# Challenge 5: Average Marks

Store five student marks in an `ArrayList<Integer>`.

Calculate:

```text
Total
Average
Maximum Mark
Minimum Mark
```

---

# Summary

- `ArrayList` is a dynamic array.
- It belongs to the `java.util` package.
- It implements the `List` interface.
- It maintains insertion order.
- It allows duplicate values.
- Elements are accessed using indexes.
- `add()` adds elements.
- `get()` retrieves elements.
- `set()` updates elements.
- `remove()` removes elements.
- `size()` returns the number of elements.
- `contains()` searches for an element.

---

# Conclusion

`ArrayList` is one of the most commonly used collections in Java.

It is useful when we need:

- Dynamic data storage
- Fast index-based access
- Easy insertion and removal
- Ordered data
- Duplicate values

Real-world applications include:

- Student lists
- Shopping carts
- To-do lists
- Employee records
- Product lists
- Marks management

Next topic:

```text
03_LinkedList.md
```
