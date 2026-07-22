# Introduction to Java Collections Framework

In Java, we often need to store multiple values.

For example:

- Student names in a class
- Products in a shopping cart
- Employee details in a company
- Course names for a student
- Customer details in a bank

Instead of creating many separate variables, Java provides the **Collections Framework**.

The Java Collections Framework helps us store, manage, search, sort, and process multiple objects easily. 

---

# What is a Collection?

A **Collection** is an object that stores multiple values together.

Example without a collection:

```java
public class Main
{
    public static void main(String[] args)
    {
        String student1 = "Anu";
        String student2 = "Bala";
        String student3 = "Charan";

        System.out.println(student1);
        System.out.println(student2);
        System.out.println(student3);
    }
}
```

### Output

```text
Anu
Bala
Charan
```

This is manageable for three students, but difficult for hundreds of students.

Using a collection makes it easier.

---

# Example Using a Collection

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

Here, all student names are stored in one `ArrayList`.

---

# Why Do We Need Collections?

Collections are useful when:

- The number of values is not fixed.
- We need to add new values.
- We need to remove values.
- We need to search for values.
- We need to sort values.
- We need to store unique values.
- We need to store key-value pairs.

---

# Arrays vs Collections

Arrays and collections are both used to store multiple values.

| Arrays | Collections |
|---|---|
| Fixed size | Dynamic size |
| Limited methods | Many built-in methods |
| Difficult to add or remove values | Easy to add or remove values |
| Can store primitive data types | Stores objects |
| Less flexible | More flexible |

---

# Array Example

```java
public class Main
{
    public static void main(String[] args)
    {
        String[] students = new String[3];

        students[0] = "Anu";
        students[1] = "Bala";
        students[2] = "Charan";

        System.out.println(students[0]);
        System.out.println(students[1]);
        System.out.println(students[2]);
    }
}
```

### Output

```text
Anu
Bala
Charan
```

The array size is fixed as `3`.

---

# Collection Example

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
        students.add("Divya");

        System.out.println(students);
    }
}
```

### Output

```text
[Anu, Bala, Charan, Divya]
```

`ArrayList` grows automatically when new elements are added.

---

# Java Collections Framework

The Java Collections Framework contains interfaces and classes used to manage groups of objects.

Main collection types:

```text
1. List
2. Set
3. Queue
4. Map
```

---

# Collections Hierarchy

```text
Collection
│
├── List
│   ├── ArrayList
│   ├── LinkedList
│   ├── Vector
│   └── Stack
│
├── Set
│   ├── HashSet
│   ├── LinkedHashSet
│   └── TreeSet
│
└── Queue
    ├── PriorityQueue
    └── ArrayDeque

Map
│
├── HashMap
├── LinkedHashMap
└── TreeMap
```

`Map` is separate from the `Collection` interface.

---

# 1. List

A `List` stores elements in insertion order.

It allows duplicate values.

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
        fruits.add("Apple");

        System.out.println(fruits);
    }
}
```

### Output

```text
[Apple, Banana, Mango, Apple]
```

The duplicate value `Apple` is allowed.

---

# 2. Set

A `Set` stores only unique values.

Duplicate values are automatically removed.

Example:

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> courses = new HashSet<>();

        courses.add("Java");
        courses.add("Python");
        courses.add("Data Science");
        courses.add("Java");

        System.out.println(courses);
    }
}
```

### Output

```text
[Java, Python, Data Science]
```

The duplicate `Java` value is stored only once.

Note: `HashSet` does not guarantee insertion order.

---

# 3. Queue

A `Queue` stores elements in processing order.

It usually follows:

```text
FIFO

First In First Out
```

Example: People waiting in a ticket counter queue.

```java
import java.util.LinkedList;
import java.util.Queue;

public class Main
{
    public static void main(String[] args)
    {
        Queue<String> customers = new LinkedList<>();

        customers.add("Anu");
        customers.add("Bala");
        customers.add("Charan");

        System.out.println("Queue: " + customers);

        System.out.println("Serving: " + customers.poll());

        System.out.println("Remaining Queue: " + customers);
    }
}
```

### Output

```text
Queue: [Anu, Bala, Charan]
Serving: Anu
Remaining Queue: [Bala, Charan]
```

---

# 4. Map

A `Map` stores values as key-value pairs.

Example:

```text
Student ID → Student Name

101 → Anu
102 → Bala
103 → Charan
```

Example program:

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");
        students.put(102, "Bala");
        students.put(103, "Charan");

        System.out.println(students);

        System.out.println("Student with ID 102: " + students.get(102));
    }
}
```

### Output

```text
{101=Anu, 102=Bala, 103=Charan}
Student with ID 102: Bala
```

---

# Generics in Collections

Generics specify the type of values stored in a collection.

Example:

```java
ArrayList<String> names = new ArrayList<>();
```

Here:

```text
ArrayList = Collection type
String = Type of data stored
```

Another example:

```java
ArrayList<Integer> marks = new ArrayList<>();
```

This collection stores only integer values.

---

# Example: Type Safety Using Generics

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> students = new ArrayList<>();

        students.add("Ragavarshini");
        students.add("Priya");

        System.out.println(students);

        // students.add(100);
        // Error because this ArrayList accepts only String values
    }
}
```

### Output

```text
[Ragavarshini, Priya]
```

---

# Common Collection Methods

| Method | Purpose |
|---|---|
| `add()` | Adds an element |
| `remove()` | Removes an element |
| `contains()` | Checks whether an element exists |
| `size()` | Returns the number of elements |
| `clear()` | Removes all elements |
| `isEmpty()` | Checks whether the collection is empty |

---

# Example: Common Methods

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

        System.out.println("Courses: " + courses);

        System.out.println("Total Courses: " + courses.size());

        System.out.println("Contains Java: " + courses.contains("Java"));

        courses.remove("Python");

        System.out.println("After Removing Python: " + courses);

        System.out.println("Is Empty: " + courses.isEmpty());
    }
}
```

### Output

```text
Courses: [Java, Python, Data Science]
Total Courses: 3
Contains Java: true
After Removing Python: [Java, Data Science]
Is Empty: false
```

---

# Real-World Example: Student Attendance System

A college can use an `ArrayList` to store students who attended a class.

```java
import java.util.ArrayList;

public class Main
{
    public static void main(String[] args)
    {
        ArrayList<String> attendanceList = new ArrayList<>();

        attendanceList.add("Ragavarshini");
        attendanceList.add("Priya");
        attendanceList.add("Kavin");
        attendanceList.add("Arun");

        System.out.println("Students Present:");

        for(String student : attendanceList)
        {
            System.out.println(student);
        }
    }
}
```

### Output

```text
Students Present:
Ragavarshini
Priya
Kavin
Arun
```

---

# Real-World Example: Online Shopping Cart

An e-commerce application can use an `ArrayList` to store products.

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

        System.out.println("Shopping Cart: " + cart);

        cart.remove("Mouse");

        System.out.println("Updated Cart: " + cart);
    }
}
```

### Output

```text
Shopping Cart: [Laptop, Mouse, Keyboard]
Updated Cart: [Laptop, Keyboard]
```

---

# Real-World Example: Unique Course Registration

A student should not register for the same course twice.

A `HashSet` can be used for this.

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> registeredCourses = new HashSet<>();

        registeredCourses.add("Java");
        registeredCourses.add("Python");
        registeredCourses.add("Data Science");
        registeredCourses.add("Java");

        System.out.println("Registered Courses: " + registeredCourses);
    }
}
```

### Output

```text
Registered Courses: [Java, Python, Data Science]
```

The duplicate course is automatically removed.

---

# Real-World Example: Employee Directory

A company can store employee ID and employee name using `HashMap`.

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> employees = new HashMap<>();

        employees.put(1001, "Alice");
        employees.put(1002, "Bob");
        employees.put(1003, "Charlie");

        System.out.println(
                "Employee with ID 1002: " +
                employees.get(1002));
    }
}
```

### Output

```text
Employee with ID 1002: Bob
```

---

# Important Wrapper Classes

Collections store objects, not primitive data types.

| Primitive Data Type | Wrapper Class |
|---|---|
| `int` | `Integer` |
| `double` | `Double` |
| `char` | `Character` |
| `boolean` | `Boolean` |
| `long` | `Long` |
| `float` | `Float` |

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

# Common Mistakes

## Forgetting Import Statement

❌ Incorrect:

```java
ArrayList<String> names = new ArrayList<>();
```

✅ Correct:

```java
import java.util.ArrayList;
```

---

## Using Primitive Types in Generics

❌ Incorrect:

```java
ArrayList<int> numbers = new ArrayList<int>();
```

✅ Correct:

```java
ArrayList<Integer> numbers = new ArrayList<Integer>();
```

---

## Expecting HashSet to Maintain Order

```java
HashSet<String> names = new HashSet<>();
```

`HashSet` does not guarantee insertion order.

Use `LinkedHashSet` if insertion order is required.

---

# Advantages of Collections

- Dynamic size
- Easy to add and remove elements
- Built-in methods
- Supports searching
- Supports sorting
- Supports unique values
- Supports key-value pairs
- Reduces code complexity
- Useful for real-world applications

---

# Interview Questions

### What is the Java Collections Framework?

The Java Collections Framework is a set of interfaces and classes used to store and manage groups of objects.

---

### What are the main collection interfaces?

- List
- Set
- Queue
- Map

---

### What is the difference between List and Set?

A List allows duplicate values and maintains insertion order. A Set stores only unique values.

---

### What is the difference between Array and ArrayList?

An array has fixed size, while an ArrayList can grow or shrink dynamically.

---

### What is a Map?

A Map stores data using key-value pairs.

---

### Does Map extend Collection?

No. `Map` is separate from the `Collection` interface.

---

# Challenge Exercises

### Challenge 1

Create an `ArrayList` with five student names and display them using a loop.

---

### Challenge 2

Create a `HashSet` with course names. Add one duplicate course and display the output.

---

### Challenge 3

Create a `HashMap` that stores employee ID and employee name.

Display one employee name using the employee ID.

---

### Challenge 4

Create a queue for customers waiting in a bank.

Remove and display the first customer.

---

### Challenge 5

Create an `ArrayList` of integers.

Add five numbers, remove one number, and display the final list.

---

# Summary

- Collections store multiple objects together.
- Collections are dynamic and flexible.
- Main collection types are List, Set, Queue, and Map.
- List allows duplicates and maintains order.
- Set stores unique values.
- Queue follows FIFO order.
- Map stores key-value pairs.
- Generics provide type safety.
- Collections are used in many real-world Java applications.

---

# Conclusion

The Java Collections Framework helps developers manage multiple values efficiently.

After learning this introduction, continue with:

```text
02_ArrayList.md
```
