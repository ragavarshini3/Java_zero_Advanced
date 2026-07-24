# Vector in Java

`Vector` is a class in the Java Collections Framework used to store multiple elements in a **dynamic array**.

Like `ArrayList`, a `Vector` can automatically grow or shrink when elements are added or removed.

The main difference is that `Vector` methods are **synchronized**, which makes `Vector` thread-safe for individual operations.
 
`Vector` is a legacy collection class, but it is still useful to understand because it appears in older Java applications and is the parent class of `Stack`.
 
---
 
# What is a Vector?

A `Vector` is a resizable array implementation of the `List` interface.

It can:
 
- Store multiple elements
- Increase its size dynamically
- Maintain insertion order
- Allow duplicate values
- Allow `null` values
- Access elements using indexes

Example:

```java
Vector<String> students = new Vector<>();
```

Elements can be added dynamically:

```java
students.add("Anu");
students.add("Bala");
students.add("Charan");
```

---

# Importing Vector

Before using `Vector`, import it from the `java.util` package.

```java
import java.util.Vector;
```

---

# Syntax

```java
Vector<DataType> vectorName = new Vector<>();
```

Example with strings:

```java
Vector<String> names = new Vector<>();
```

Example with integers:

```java
Vector<Integer> numbers = new Vector<>();
```

Example with doubles:

```java
Vector<Double> prices = new Vector<>();
```

---

# Basic Vector Example

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

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

# How Vector Works

Suppose we create:

```java
Vector<String> fruits = new Vector<>();
```

Initially:

```text
[]
```

Add Apple:

```java
fruits.add("Apple");
```

```text
Index      0
         Apple
```

Add Banana:

```java
fruits.add("Banana");
```

```text
Index      0        1
         Apple    Banana
```

Add Mango:

```java
fruits.add("Mango");
```

```text
Index      0        1        2
         Apple    Banana    Mango
```

Like arrays and `ArrayList`, `Vector` uses **zero-based indexing**.

---

# Important Features of Vector

`Vector`:

- Has dynamic size
- Maintains insertion order
- Allows duplicate values
- Allows `null` values
- Supports index-based access
- Implements the `List` interface
- Provides synchronized methods
- Can automatically increase its capacity

---

# Creating a Vector with Initial Capacity

We can specify the initial capacity.

```java
Vector<Integer> numbers = new Vector<>(5);
```

Here, the initial capacity is:

```text
5
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<Integer> numbers = new Vector<>(5);

        numbers.add(10);
        numbers.add(20);
        numbers.add(30);

        System.out.println(numbers);

        System.out.println(
            "Size: " + numbers.size()
        );

        System.out.println(
            "Capacity: " + numbers.capacity()
        );
    }
}
```

### Output

```text
[10, 20, 30]
Size: 3
Capacity: 5
```

---

# Size vs Capacity

`size()` and `capacity()` are different.

### Size

The number of actual elements stored.

### Capacity

The amount of internal storage currently available before the vector needs to grow.

Example:

```java
Vector<Integer> numbers = new Vector<>(5);

numbers.add(10);
numbers.add(20);
```

Then:

```text
Size     = 2
Capacity = 5
```

---

# Example: Size and Capacity

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> courses = new Vector<>(4);

        courses.add("Java");
        courses.add("Python");

        System.out.println(
            "Courses: " + courses
        );

        System.out.println(
            "Size: " + courses.size()
        );

        System.out.println(
            "Capacity: " + courses.capacity()
        );
    }
}
```

### Output

```text
Courses: [Java, Python]
Size: 2
Capacity: 4
```

---

# Adding Elements

Use:

```java
add()
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> fruits = new Vector<>();

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

# Using addElement()

`Vector` also provides the older method:

```java
addElement()
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> languages = new Vector<>();

        languages.addElement("Java");
        languages.addElement("Python");
        languages.addElement("C++");

        System.out.println(languages);
    }
}
```

### Output

```text
[Java, Python, C++]
```

Both:

```java
add()
```

and:

```java
addElement()
```

can add elements to a `Vector`.

For modern Java code, `add()` is generally preferred because it follows the `Collection` interface API.

---

# Adding at a Specific Index

Syntax:

```java
vector.add(index, element);
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> fruits = new Vector<>();

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

---

# Accessing an Element

Use:

```java
get(index)
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

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

# Using elementAt()

`Vector` also provides:

```java
elementAt(index)
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        System.out.println(
            students.elementAt(1)
        );
    }
}
```

### Output

```text
Bala
```

---

# Getting the First Element

Use:

```java
firstElement()
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> names = new Vector<>();

        names.add("Anu");
        names.add("Bala");
        names.add("Charan");

        System.out.println(
            "First: " + names.firstElement()
        );
    }
}
```

### Output

```text
First: Anu
```

---

# Getting the Last Element

Use:

```java
lastElement()
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> names = new Vector<>();

        names.add("Anu");
        names.add("Bala");
        names.add("Charan");

        System.out.println(
            "Last: " + names.lastElement()
        );
    }
}
```

### Output

```text
Last: Charan
```

---

# Updating an Element

Use:

```java
set(index, newValue)
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

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

---

# Removing an Element by Value

Use:

```java
remove()
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> fruits = new Vector<>();

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

# Removing an Element by Index

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> fruits = new Vector<>();

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

# Using removeElement()

`Vector` also provides:

```java
removeElement()
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> courses = new Vector<>();

        courses.add("Java");
        courses.add("Python");
        courses.add("C++");

        courses.removeElement("Python");

        System.out.println(courses);
    }
}
```

### Output

```text
[Java, C++]
```

---

# Finding the Size

Use:

```java
size()
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        System.out.println(
            "Total Students: " +
            students.size()
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
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> courses = new Vector<>();

        courses.add("Java");
        courses.add("Python");
        courses.add("AI");

        System.out.println(
            courses.contains("Java")
        );

        System.out.println(
            courses.contains("C++")
        );
    }
}
```

### Output

```text
true
false
```

---

# Finding the Index

Use:

```java
indexOf()
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        System.out.println(
            students.indexOf("Bala")
        );
    }
}
```

### Output

```text
1
```

If the value does not exist:

```text
-1
```

is returned.

---

# Checking Whether Vector is Empty

Use:

```java
isEmpty()
```

Example:

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> data = new Vector<>();

        System.out.println(data.isEmpty());

        data.add("Java");

        System.out.println(data.isEmpty());
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
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

        students.add("Anu");
        students.add("Bala");
        students.add("Charan");

        System.out.println(
            "Before: " + students
        );

        students.clear();

        System.out.println(
            "After: " + students
        );
    }
}
```

### Output

```text
Before: [Anu, Bala, Charan]
After: []
```

---

# Traversing Vector Using for Loop

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

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

# Traversing Using Enhanced for Loop

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

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

# Vector with Integer Values

Use the `Integer` wrapper class.

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<Integer> marks = new Vector<>();

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

# Finding Sum of Vector Elements

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<Integer> numbers = new Vector<>();

        numbers.add(10);
        numbers.add(20);
        numbers.add(30);
        numbers.add(40);

        int sum = 0;

        for(int number : numbers)
        {
            sum = sum + number;
        }

        System.out.println(
            "Sum: " + sum
        );
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
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<Integer> numbers = new Vector<>();

        numbers.add(40);
        numbers.add(90);
        numbers.add(20);
        numbers.add(75);

        int maximum = numbers.get(0);

        for(int number : numbers)
        {
            if(number > maximum)
            {
                maximum = number;
            }
        }

        System.out.println(
            "Maximum: " + maximum
        );
    }
}
```

### Output

```text
Maximum: 90
```

---

# Real-World Example 1: Student Record List

Suppose an older college management application maintains a synchronized list of student names.

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> students = new Vector<>();

        students.add("Ragavarshini");
        students.add("Priya");
        students.add("Kavin");
        students.add("Arun");

        System.out.println("Student Records:");

        for(String student : students)
        {
            System.out.println(student);
        }

        System.out.println(
            "Total Students: " +
            students.size()
        );
    }
}
```

### Output

```text
Student Records:
Ragavarshini
Priya
Kavin
Arun
Total Students: 4
```

---

# Real-World Example 2: Shared Task List

Imagine a legacy application where multiple threads may work with a shared task list.

A `Vector` provides synchronized individual methods.

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> tasks = new Vector<>();

        tasks.add("Generate Report");
        tasks.add("Send Email");
        tasks.add("Backup Database");

        System.out.println(
            "Tasks: " + tasks
        );

        tasks.remove("Send Email");

        System.out.println(
            "Remaining Tasks: " + tasks
        );
    }
}
```

### Output

```text
Tasks: [Generate Report, Send Email, Backup Database]
Remaining Tasks: [Generate Report, Backup Database]
```

---

# Real-World Example 3: Product Inventory

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<String> products = new Vector<>();

        products.add("Laptop");
        products.add("Keyboard");
        products.add("Mouse");
        products.add("Monitor");

        System.out.println(
            "Products: " + products
        );

        products.remove("Mouse");

        products.add("Webcam");

        System.out.println(
            "Updated Products: " +
            products
        );

        System.out.println(
            "Total Products: " +
            products.size()
        );
    }
}
```

### Output

```text
Products: [Laptop, Keyboard, Mouse, Monitor]
Updated Products: [Laptop, Keyboard, Monitor, Webcam]
Total Products: 4
```

---

# Real-World Example 4: Student Marks

```java
import java.util.Vector;

public class Main
{
    public static void main(String[] args)
    {
        Vector<Integer> marks = new Vector<>();

        marks.add(85);
        marks.add(92);
        marks.add(78);
        marks.add(88);
        marks.add(95);

        int total = 0;

        for(int mark : marks)
        {
            total += mark;
        }

        double average =
            (double) total / marks.size();

        System.out.println(
            "Total: " + total
        );

        System.out.println(
            "Average: " + average
        );
    }
}
```

### Output

```text
Total: 438
Average: 87.6
```

---

# Vector and Thread Safety

One important feature of `Vector` is that many of its methods are synchronized.

For example:

```java
vector.add(value);
vector.remove(value);
vector.get(index);
```

Synchronization helps control access when multiple threads use the same vector.

However, this does **not** mean every sequence of multiple operations is automatically thread-safe.

For example:

```java
if(!vector.isEmpty())
{
    vector.remove(0);
}
```

Another thread could modify the vector between these operations.

More advanced concurrent programming may require additional synchronization or concurrent collection classes.

---

# ArrayList vs Vector

Both are dynamic arrays, but there are important differences.

| Feature | ArrayList | Vector |
|---|---|---|
| Dynamic Size | Yes | Yes |
| Maintains Order | Yes | Yes |
| Allows Duplicates | Yes | Yes |
| Index Access | Yes | Yes |
| Synchronized Methods | No | Yes |
| Performance | Usually faster for single-threaded use | Synchronization adds overhead |
| Legacy Class | No | Yes |
| Common Modern Usage | Very common | Less common |

---

# When to Use ArrayList

Use `ArrayList` when:

- You need a dynamic array.
- Thread safety is not required.
- You want good general-purpose performance.
- You are writing typical modern Java code.

Example:

```java
ArrayList<String> students =
    new ArrayList<>();
```

---

# When to Use Vector

`Vector` may be encountered or considered when:

- Working with legacy Java code.
- An existing API specifically uses `Vector`.
- Synchronized individual list operations are required.

In modern concurrent applications, developers often use more specialized concurrency utilities depending on the requirement.

---

# Vector vs LinkedList

| Feature | Vector | LinkedList |
|---|---|---|
| Internal Structure | Dynamic array | Doubly linked list |
| Random Access | Fast | Slower |
| Synchronized Methods | Yes | No |
| Memory | Less node overhead | More due to links |
| Beginning/End Operations | Supported | Particularly convenient |
| Implements | List | List and Deque |

---

# Important Vector Methods

| Method | Description |
|---|---|
| `add()` | Adds an element |
| `addElement()` | Adds an element using legacy Vector API |
| `add(index, value)` | Adds at a specific index |
| `get()` | Gets an element |
| `elementAt()` | Gets an element |
| `firstElement()` | Returns first element |
| `lastElement()` | Returns last element |
| `set()` | Updates an element |
| `remove()` | Removes an element |
| `removeElement()` | Removes specified element |
| `size()` | Returns number of elements |
| `capacity()` | Returns current capacity |
| `contains()` | Checks whether value exists |
| `indexOf()` | Returns element index |
| `isEmpty()` | Checks whether vector is empty |
| `clear()` | Removes all elements |

---

# Common Mistake 1: Size and Capacity Confusion

Consider:

```java
Vector<Integer> numbers =
    new Vector<>(10);

numbers.add(100);
numbers.add(200);
```

The result is:

```text
Size = 2
Capacity = 10
```

`size()` represents actual elements.

`capacity()` represents internal storage capacity.

---

# Common Mistake 2: Invalid Index

```java
Vector<String> names = new Vector<>();

names.add("Anu");

System.out.println(names.get(5));
```

This causes:

```text
ArrayIndexOutOfBoundsException
```

or another index-related runtime exception depending on the method used.

Always ensure the index is valid.

---

# Common Mistake 3: Assuming Vector Makes All Code Thread-Safe

Although individual `Vector` methods are synchronized, a group of multiple operations may still need proper synchronization.

Thread safety depends on how the complete program accesses shared data.

---

# Advantages of Vector

- Dynamic size
- Maintains insertion order
- Allows duplicates
- Supports index-based access
- Provides synchronized methods
- Provides capacity management
- Useful when maintaining older Java applications

---

# Limitations of Vector

- Synchronization can add performance overhead
- Less commonly used in modern Java applications
- `ArrayList` is often preferred for normal single-threaded list operations
- Synchronized individual methods do not automatically make complex multi-step operations thread-safe

---

# Interview Questions

### What is Vector in Java?

`Vector` is a resizable array implementation of the `List` interface.

---

### Does Vector allow duplicate values?

Yes.

---

### Does Vector maintain insertion order?

Yes.

---

### Is Vector synchronized?

Many of its methods are synchronized.

---

### What is the difference between ArrayList and Vector?

Both are dynamic arrays, but `Vector` provides synchronized methods, while `ArrayList` does not.

---

### What is the difference between size and capacity?

`size()` represents the number of actual elements.

`capacity()` represents the current internal storage capacity.

---

### Is Vector a legacy class?

Yes. `Vector` has existed since early versions of Java and is considered a legacy collection class.

---

### Which class extends Vector?

`Stack` extends `Vector`.

---

# Challenge 1: Student Vector

Create a `Vector` containing:

```text
Anu
Bala
Charan
Divya
```

Display:

```text
First Student
Last Student
Total Students
```

---

# Challenge 2: Integer Vector

Create:

```text
10
20
30
40
50
```

Calculate:

```text
Sum
Average
Maximum
Minimum
```

---

# Challenge 3: Product Inventory

Create a `Vector` containing:

```text
Laptop
Mouse
Keyboard
Monitor
```

Perform:

```text
Remove Mouse
Add Webcam
Display final products
```

Expected Output:

```text
[Laptop, Keyboard, Monitor, Webcam]
```

---

# Challenge 4: Size and Capacity

Create:

```java
Vector<Integer> numbers =
    new Vector<>(5);
```

Add three numbers.

Display:

```text
Size
Capacity
```

Understand why both values are different.

---

# Challenge 5: Search Student

Create a `Vector` of student names.

Ask the user to enter a student name.

Check whether the student exists using:

```java
contains()
```

If found:

```text
Student Found
```

Otherwise:

```text
Student Not Found
```

---

# Summary

- `Vector` is part of `java.util`.
- It implements the `List` interface.
- It works like a dynamic array.
- It maintains insertion order.
- It allows duplicate values.
- It supports index-based access.
- Many Vector methods are synchronized.
- `size()` returns the number of elements.
- `capacity()` returns the current internal capacity.
- `add()` adds an element.
- `get()` accesses an element.
- `set()` updates an element.
- `remove()` removes an element.
- `Stack` extends `Vector`.

---

# Conclusion

`Vector` is a dynamic array collection similar to `ArrayList`, but it provides synchronized methods.

It is especially important for understanding:

- Legacy Java applications
- Dynamic arrays
- Synchronization basics
- The foundation of the older `Stack` class

For most normal modern list operations, `ArrayList` is generally preferred when synchronization is not required.

The next topic is:

```text
05_Stack.md
```
