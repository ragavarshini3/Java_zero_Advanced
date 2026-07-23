# LinkedList in Java

`LinkedList` is a class in the Java Collections Framework used to store multiple elements.

Like `ArrayList`, it implements the `List` interface.

However, internally, `LinkedList` stores elements as connected **nodes**, whereas `ArrayList` stores elements using a dynamic array.

`LinkedList` is useful when a program performs frequent insertion and deletion operations, especially at the beginning or end of a list.

---

# What is a LinkedList?

A `LinkedList` is a linear data structure where elements are stored as separate nodes connected to each other.

Each node conceptually contains:  

```text 
Previous Reference
       +
Data
       +
Next Reference
```

Java's `LinkedList` is implemented as a **doubly linked list**.

Example:

```text
null
  ↑
[Previous | Anu | Next]
        ↕
[Previous | Bala | Next]
        ↕
[Previous | Charan | Next]
                         ↓
                        null
```

Each element is connected to:

- The previous element
- The next element

This allows efficient insertion and deletion once the relevant position/node is reached.

---

# Importing LinkedList

Before using `LinkedList`, import it from `java.util`.

```java
import java.util.LinkedList;
```

---

# Syntax

```java
LinkedList<DataType> listName = new LinkedList<>();
```

Example with strings:

```java
LinkedList<String> students = new LinkedList<>();
```

Example with integers:

```java
LinkedList<Integer> numbers = new LinkedList<>();
```

---

# Basic LinkedList Example

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

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

# Important Features of LinkedList

`LinkedList`:

- Has dynamic size
- Maintains insertion order
- Allows duplicate values
- Allows `null` values
- Supports insertion at the beginning and end
- Supports deletion from the beginning and end
- Implements both `List` and `Deque`
- Can be used like a list, queue, or deque

---

# Adding Elements

Use the `add()` method.

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> fruits = new LinkedList<>();

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
list.add(index, element);
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> fruits = new LinkedList<>();

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

# Adding an Element at the Beginning

`LinkedList` provides:

```java
addFirst()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

        students.add("Bala");
        students.add("Charan");

        students.addFirst("Anu");

        System.out.println(students);
    }
}
```

### Output

```text
[Anu, Bala, Charan]
```

---

# Adding an Element at the End

Use:

```java
addLast()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

        students.add("Anu");
        students.add("Bala");

        students.addLast("Charan");

        System.out.println(students);
    }
}
```

### Output

```text
[Anu, Bala, Charan]
```

---

# Accessing Elements

Use:

```java
get(index)
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

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

# Accessing the First Element

Use:

```java
getFirst()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> names = new LinkedList<>();

        names.add("Anu");
        names.add("Bala");
        names.add("Charan");

        System.out.println(
            "First Element: " + names.getFirst()
        );
    }
}
```

### Output

```text
First Element: Anu
```

---

# Accessing the Last Element

Use:

```java
getLast()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> names = new LinkedList<>();

        names.add("Anu");
        names.add("Bala");
        names.add("Charan");

        System.out.println(
            "Last Element: " + names.getLast()
        );
    }
}
```

### Output

```text
Last Element: Charan
```

---

# Updating an Element

Use:

```java
set(index, newValue)
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

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

# Removing an Element

Use:

```java
remove()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> fruits = new LinkedList<>();

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

# Removing by Index

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> fruits = new LinkedList<>();

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

# Removing the First Element

Use:

```java
removeFirst()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> names = new LinkedList<>();

        names.add("Anu");
        names.add("Bala");
        names.add("Charan");

        names.removeFirst();

        System.out.println(names);
    }
}
```

### Output

```text
[Bala, Charan]
```

---

# Removing the Last Element

Use:

```java
removeLast()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> names = new LinkedList<>();

        names.add("Anu");
        names.add("Bala");
        names.add("Charan");

        names.removeLast();

        System.out.println(names);
    }
}
```

### Output

```text
[Anu, Bala]
```

---

# Finding the Size

Use:

```java
size()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

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
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> courses = new LinkedList<>();

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

# Finding the Index of an Element

Use:

```java
indexOf()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

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

---

# Checking Whether LinkedList is Empty

Use:

```java
isEmpty()
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> list = new LinkedList<>();

        System.out.println(list.isEmpty());

        list.add("Java");

        System.out.println(list.isEmpty());
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
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

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

# Traversing a LinkedList Using for Loop

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

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

For a `LinkedList`, repeated indexed access with `get(i)` can be inefficient for large lists because Java may need to traverse nodes to reach each index.

An enhanced `for` loop or iterator is generally better for sequential traversal.

---

# Traversing Using Enhanced for Loop

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> students = new LinkedList<>();

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

# LinkedList with Integer Values

Use the `Integer` wrapper class.

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<Integer> numbers = new LinkedList<>();

        numbers.add(10);
        numbers.add(20);
        numbers.add(30);

        System.out.println(numbers);
    }
}
```

### Output

```text
[10, 20, 30]
```

---

# LinkedList as a Queue

Because `LinkedList` implements `Deque`, it can be used for queue-like operations.

A queue follows:

```text
FIFO

First In First Out
```

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> customers = new LinkedList<>();

        customers.addLast("Customer 1");
        customers.addLast("Customer 2");
        customers.addLast("Customer 3");

        System.out.println(
            "Waiting: " + customers
        );

        String served = customers.removeFirst();

        System.out.println(
            "Served: " + served
        );

        System.out.println(
            "Remaining: " + customers
        );
    }
}
```

### Output

```text
Waiting: [Customer 1, Customer 2, Customer 3]
Served: Customer 1
Remaining: [Customer 2, Customer 3]
```

---

# Real-World Example 1: Hospital Patient Queue

Imagine patients waiting to meet a doctor.

The first patient who arrives should normally be served first.

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> patients = new LinkedList<>();

        patients.addLast("Rahul");
        patients.addLast("Priya");
        patients.addLast("Arun");

        System.out.println(
            "Waiting Patients: " + patients
        );

        String currentPatient =
            patients.removeFirst();

        System.out.println(
            "Doctor is checking: " +
            currentPatient
        );

        System.out.println(
            "Remaining Patients: " +
            patients
        );
    }
}
```

### Output

```text
Waiting Patients: [Rahul, Priya, Arun]
Doctor is checking: Rahul
Remaining Patients: [Priya, Arun]
```

---

# Real-World Example 2: Music Playlist

A music application can maintain songs using a `LinkedList`.

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> playlist = new LinkedList<>();

        playlist.add("Song A");
        playlist.add("Song B");
        playlist.add("Song C");

        System.out.println(
            "Playlist: " + playlist
        );

        playlist.addFirst("Intro Song");

        playlist.addLast("Ending Song");

        System.out.println(
            "Updated Playlist: " +
            playlist
        );
    }
}
```

### Output

```text
Playlist: [Song A, Song B, Song C]
Updated Playlist: [Intro Song, Song A, Song B, Song C, Ending Song]
```

---

# Real-World Example 3: Delivery Queue

An e-commerce logistics system may maintain pending deliveries.

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> deliveries =
            new LinkedList<>();

        deliveries.addLast("Order-101");
        deliveries.addLast("Order-102");
        deliveries.addLast("Order-103");

        System.out.println(
            "Pending Deliveries: " +
            deliveries
        );

        String completed =
            deliveries.removeFirst();

        System.out.println(
            "Delivered: " + completed
        );

        System.out.println(
            "Remaining Deliveries: " +
            deliveries
        );
    }
}
```

### Output

```text
Pending Deliveries: [Order-101, Order-102, Order-103]
Delivered: Order-101
Remaining Deliveries: [Order-102, Order-103]
```

---

# Real-World Example 4: Emergency Patient

Suppose a hospital has normal patients waiting.

An emergency patient arrives and must be added to the beginning.

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> patients =
            new LinkedList<>();

        patients.addLast("Patient A");
        patients.addLast("Patient B");
        patients.addLast("Patient C");

        System.out.println(
            "Normal Queue: " + patients
        );

        patients.addFirst(
            "Emergency Patient"
        );

        System.out.println(
            "Updated Queue: " + patients
        );

        System.out.println(
            "Next Patient: " +
            patients.removeFirst()
        );
    }
}
```

### Output

```text
Normal Queue: [Patient A, Patient B, Patient C]
Updated Queue: [Emergency Patient, Patient A, Patient B, Patient C]
Next Patient: Emergency Patient
```

---

# ArrayList vs LinkedList

Both implement the `List` interface, but their internal structures are different.

| Feature | ArrayList | LinkedList |
|---|---|---|
| Internal Structure | Dynamic array | Doubly linked list |
| Random index access | Fast | Slower |
| `get(index)` | Generally efficient | Requires traversal |
| Add/remove at ends | Efficient in many cases | Efficient |
| Insert/remove at known node position | Requires shifting elements | Link changes are efficient |
| Memory usage | Lower | Higher due to node references |
| Implements | `List` | `List` and `Deque` |

---

# Important Performance Note

A common statement is:

```text
LinkedList is always faster for insertion and deletion.
```

This is not completely correct.

For example, to insert at index `5000`, a `LinkedList` must first traverse the list to find that position.

So the total operation may still take time.

`LinkedList` is particularly useful when:

- Frequent operations happen at the beginning or end.
- Queue or deque operations are needed.
- Sequential traversal is common.

`ArrayList` is usually better when:

- Frequent random access using indexes is required.
- Most operations involve reading elements.
- Memory efficiency is important.

---

# Important LinkedList Methods

| Method | Description |
|---|---|
| `add()` | Adds an element |
| `addFirst()` | Adds at the beginning |
| `addLast()` | Adds at the end |
| `get()` | Gets an element by index |
| `getFirst()` | Gets the first element |
| `getLast()` | Gets the last element |
| `set()` | Updates an element |
| `remove()` | Removes an element |
| `removeFirst()` | Removes the first element |
| `removeLast()` | Removes the last element |
| `contains()` | Searches for an element |
| `indexOf()` | Finds an element index |
| `size()` | Returns the number of elements |
| `isEmpty()` | Checks whether list is empty |
| `clear()` | Removes all elements |

---

# Common Mistake 1: Invalid Index

```java
LinkedList<String> names = new LinkedList<>();

names.add("Anu");

System.out.println(names.get(5));
```

This causes:

```text
IndexOutOfBoundsException
```

Always ensure:

```java
index >= 0 && index < list.size()
```

---

# Common Mistake 2: Removing from an Empty LinkedList

Example:

```java
LinkedList<String> names = new LinkedList<>();

names.removeFirst();
```

This can throw:

```text
NoSuchElementException
```

Check first:

```java
if(!names.isEmpty())
{
    names.removeFirst();
}
```

---

# Safer Queue-Style Methods

`LinkedList` also provides methods such as:

```text
peek()
poll()
offer()
```

Unlike some methods that throw exceptions when the list is empty, `peek()` and `poll()` can be safer in queue-style operations.

Example:

```java
import java.util.LinkedList;

public class Main
{
    public static void main(String[] args)
    {
        LinkedList<String> queue =
            new LinkedList<>();

        queue.offer("Customer A");
        queue.offer("Customer B");

        System.out.println(
            "Next: " + queue.peek()
        );

        System.out.println(
            "Serving: " + queue.poll()
        );

        System.out.println(
            "Remaining: " + queue
        );
    }
}
```

### Output

```text
Next: Customer A
Serving: Customer A
Remaining: [Customer B]
```

---

# Advantages of LinkedList

- Dynamic size
- Easy insertion at the beginning
- Easy insertion at the end
- Easy removal from both ends
- Maintains insertion order
- Allows duplicate values
- Can work as a list
- Can support queue and deque operations

---

# Limitations of LinkedList

- Slower random index access than `ArrayList`
- Uses more memory because nodes store references
- Searching may require sequential traversal
- Repeated `get(index)` operations can be inefficient for large lists

---

# Interview Questions

### What is LinkedList in Java?

`LinkedList` is a doubly linked list implementation that implements the `List` and `Deque` interfaces.

---

### Does LinkedList maintain insertion order?

Yes.

---

### Does LinkedList allow duplicate values?

Yes.

---

### Can LinkedList contain null?

Yes.

---

### What is the difference between ArrayList and LinkedList?

`ArrayList` uses a dynamic array internally, while `LinkedList` uses linked nodes.

`ArrayList` is generally better for frequent random access.

`LinkedList` is useful for frequent operations at the beginning or end and for queue/deque behavior.

---

### Which method adds an element at the beginning?

```java
addFirst()
```

---

### Which method adds an element at the end?

```java
addLast()
```

---

### Which method removes the first element?

```java
removeFirst()
```

---

### Which method removes the last element?

```java
removeLast()
```

---

# Challenge 1: Student Queue

Create a `LinkedList` containing:

```text
Anu
Bala
Charan
```

Add:

```text
Priya
```

at the beginning.

Expected Output:

```text
[Priya, Anu, Bala, Charan]
```

---

# Challenge 2: Remove First and Last

Create:

```text
[10, 20, 30, 40, 50]
```

Remove the first and last elements.

Expected Output:

```text
[20, 30, 40]
```

---

# Challenge 3: Hospital Queue

Create a patient queue.

Add:

```text
Patient A
Patient B
Patient C
```

Then add:

```text
Emergency Patient
```

to the beginning.

Display the patient who should be treated first.

---

# Challenge 4: Delivery System

Create a delivery queue with five order IDs.

Complete the first delivery using:

```java
removeFirst()
```

Display the remaining orders.

---

# Challenge 5: Search Element

Create a `LinkedList` of programming languages:

```text
Java
Python
C++
JavaScript
```

Ask the user for a language and check whether it exists using:

```java
contains()
```

---

# Summary

- `LinkedList` is part of `java.util`.
- It is implemented using a doubly linked list.
- It implements `List` and `Deque`.
- It has dynamic size.
- It maintains insertion order.
- It allows duplicate and null values.
- `addFirst()` adds at the beginning.
- `addLast()` adds at the end.
- `removeFirst()` removes the first element.
- `removeLast()` removes the last element.
- Random index access is slower than `ArrayList`.
- It is useful for queue and deque operations.

---

# Conclusion

`LinkedList` is useful when an application needs flexible insertion and removal, particularly at the beginning or end of a sequence.

Real-world examples include:

- Patient queues
- Delivery queues
- Music playlists
- Task processing systems
- Navigation histories
- Queue and deque implementations

The next topic is:

```text
04_Vector.md
```
