# LinkedHashSet in Java

A **LinkedHashSet** is a class in the Java Collections Framework that stores **unique elements while maintaining the insertion order**.

Unlike `HashSet`, a `LinkedHashSet` remembers the order in which elements are inserted.

It combines the features of both a **Hash Table** and a **Linked List**.
  
--- 

# Real-World Examples
 
LinkedHashSet is used in many real-world applications where:
 
- Duplicate values should not be stored. 
- Insertion order should be preserved.
 
Examples: 

- Browser History
- Recently Viewed Products
- Playlist Management
- Student Attendance
- Order History
- Search History
- Bookmarks
- Notification History
 
---

# What is LinkedHashSet?

A **LinkedHashSet** is a collection that stores only **unique elements** while preserving the order in which they were added.

Example:

```text
Input

Java
Python
C++
Python
Java
HTML

Output

Java
Python
C++
HTML
```

Duplicates are removed, but the insertion order is maintained.

---

# LinkedHashSet Hierarchy

```text
Object
   │
AbstractCollection
   │
AbstractSet
   │
HashSet
   │
LinkedHashSet
```

LinkedHashSet extends the `HashSet` class.

---

# Import Statement

```java
import java.util.LinkedHashSet;
```

---

# Syntax

```java
LinkedHashSet<DataType> setName = new LinkedHashSet<>();
```

Example:

```java
LinkedHashSet<String> languages = new LinkedHashSet<>();
```

---

# Basic LinkedHashSet Program

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> languages = new LinkedHashSet<>();

        languages.add("Java");

        languages.add("Python");

        languages.add("C++");

        System.out.println(languages);
    }
}
```

### Output

```text
[Java, Python, C++]
```

Notice that the insertion order is preserved.

---

# Internal Working of LinkedHashSet

LinkedHashSet internally uses:

- Hash Table
- Doubly Linked List

Working Process:

1. Java calculates the hash code of the object.
2. The object is stored in the appropriate bucket.
3. A doubly linked list maintains the insertion order.
4. Duplicate elements are ignored.

```text
Hash Table

Bucket 1 --> Java
Bucket 2 --> Python
Bucket 3 --> C++
Bucket 4 --> HTML

Linked List

Java → Python → C++ → HTML
```

---

# Features of LinkedHashSet

- Stores unique elements
- Maintains insertion order
- Uses Hash Table internally
- Uses Doubly Linked List
- Allows one null value
- Fast insertion
- Fast searching
- Dynamic size
- Not synchronized

---

# Why Use LinkedHashSet?

LinkedHashSet is useful when:

- Duplicate values should not be stored.
- Insertion order must be preserved.
- Fast searching is required.
- Ordered unique data is needed.

---

# Adding Elements

Use:

```java
add()
```

Example:

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> fruits = new LinkedHashSet<>();

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

# Duplicate Elements

LinkedHashSet automatically ignores duplicate values.

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> subjects = new LinkedHashSet<>();

        subjects.add("Java");

        subjects.add("Python");

        subjects.add("Java");

        subjects.add("Python");

        System.out.println(subjects);
    }
}
```

### Output

```text
[Java, Python]
```

---

# Return Value of add()

The `add()` method returns:

- `true` → Element inserted successfully
- `false` → Duplicate element

Example:

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> set = new LinkedHashSet<>();

        System.out.println(set.add("Java"));

        System.out.println(set.add("Python"));

        System.out.println(set.add("Java"));
    }
}
```

### Output

```text
true
true
false
```

---

# Removing Elements

Use:

```java
remove()
```

Example:

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> cities = new LinkedHashSet<>();

        cities.add("Chennai");

        cities.add("Madurai");

        cities.add("Coimbatore");

        System.out.println(cities);

        cities.remove("Madurai");

        System.out.println(cities);
    }
}
```

### Output

```text
[Chennai, Madurai, Coimbatore]

[Chennai, Coimbatore]
```

---

# Searching an Element

Use:

```java
contains()
```

Example:

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> courses = new LinkedHashSet<>();

        courses.add("Java");

        courses.add("Python");

        courses.add("AI");

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

# Finding Size

Use:

```java
size()
```

Example:

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<Integer> numbers = new LinkedHashSet<>();

        numbers.add(10);

        numbers.add(20);

        numbers.add(30);

        System.out.println("Size: " + numbers.size());
    }
}
```

### Output

```text
Size: 3
```

---

# Checking Whether LinkedHashSet is Empty

Use:

```java
isEmpty()
```

Example:

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> names = new LinkedHashSet<>();

        System.out.println(names.isEmpty());

        names.add("Anu");

        System.out.println(names.isEmpty());
    }
}
```

### Output

```text
true
false
```
# Removing All Elements

Use:

```java
clear()
```

Example:

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> colors = new LinkedHashSet<>();

        colors.add("Red");

        colors.add("Green");

        colors.add("Blue");

        System.out.println("Before: " + colors);

        colors.clear();

        System.out.println("After: " + colors);
    }
}
```

### Output

```text
Before: [Red, Green, Blue]

After: []
```

---

# Traversing a LinkedHashSet

Using Enhanced for Loop

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> students = new LinkedHashSet<>();

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

Notice that the insertion order is maintained.

---

# Traversing Using Iterator

```java
import java.util.Iterator;
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> cities = new LinkedHashSet<>();

        cities.add("Chennai");

        cities.add("Madurai");

        cities.add("Coimbatore");

        Iterator<String> iterator = cities.iterator();

        while(iterator.hasNext())
        {
            System.out.println(iterator.next());
        }
    }
}
```

### Output

```text
Chennai
Madurai
Coimbatore
```

---

# LinkedHashSet with Integer Values

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<Integer> numbers = new LinkedHashSet<>();

        numbers.add(10);

        numbers.add(20);

        numbers.add(30);

        numbers.add(20);

        System.out.println(numbers);
    }
}
```

### Output

```text
[10, 20, 30]
```

Duplicate values are ignored while maintaining insertion order.

---

# LinkedHashSet with null Value

LinkedHashSet allows only **one null value**.

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> data = new LinkedHashSet<>();

        data.add("Java");

        data.add(null);

        data.add("Python");

        data.add(null);

        System.out.println(data);
    }
}
```

### Output

```text
[Java, null, Python]
```

---

# Real-World Example 1: Browser History

Browser history should preserve the order of visited pages without duplicates.

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> history = new LinkedHashSet<>();

        history.add("Google");

        history.add("YouTube");

        history.add("GitHub");

        history.add("YouTube");

        System.out.println(history);
    }
}
```

### Output

```text
[Google, YouTube, GitHub]
```

---

# Real-World Example 2: Recently Viewed Products

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> products = new LinkedHashSet<>();

        products.add("Laptop");

        products.add("Mouse");

        products.add("Keyboard");

        products.add("Laptop");

        System.out.println(products);
    }
}
```

### Output

```text
[Laptop, Mouse, Keyboard]
```

---

# Real-World Example 3: Playlist Management

Songs should appear in the order they were added.

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> playlist = new LinkedHashSet<>();

        playlist.add("Song A");

        playlist.add("Song B");

        playlist.add("Song C");

        playlist.add("Song B");

        System.out.println(playlist);
    }
}
```

### Output

```text
[Song A, Song B, Song C]
```

---

# Real-World Example 4: Student Attendance

Each student should be marked present only once while preserving attendance order.

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> attendance = new LinkedHashSet<>();

        attendance.add("Anu");

        attendance.add("Bala");

        attendance.add("Charan");

        attendance.add("Anu");

        System.out.println(attendance);
    }
}
```

### Output

```text
[Anu, Bala, Charan]
```

---

# Real-World Example 5: Search History

```java
import java.util.LinkedHashSet;

public class Main
{
    public static void main(String[] args)
    {
        LinkedHashSet<String> searches = new LinkedHashSet<>();

        searches.add("Java");

        searches.add("Python");

        searches.add("AI");

        searches.add("Java");

        System.out.println(searches);
    }
}
```

### Output

```text
[Java, Python, AI]
```

---

# Advantages of LinkedHashSet

- Stores unique elements
- Maintains insertion order
- Fast insertion
- Fast searching
- Fast deletion
- Allows one null value
- Dynamic size
- Easy to use

---

# Limitations of LinkedHashSet

- Does not allow duplicate elements
- No indexing support
- Slightly slower than HashSet
- More memory is required because of the linked list

---

# LinkedHashSet vs HashSet

| LinkedHashSet | HashSet |
|---------------|----------|
| Maintains insertion order | Does not maintain insertion order |
| Uses Hash Table + Linked List | Uses Hash Table |
| Slightly slower | Faster |
| More memory | Less memory |

---

# LinkedHashSet vs TreeSet

| LinkedHashSet | TreeSet |
|---------------|----------|
| Insertion order | Sorted order |
| Allows one null | Does not allow null |
| Faster | Slower |
| Hash Table | Red-Black Tree |

---

# LinkedHashSet vs ArrayList

| LinkedHashSet | ArrayList |
|---------------|-----------|
| No duplicates | Duplicates allowed |
| No indexing | Supports indexing |
| Maintains insertion order | Maintains insertion order |
| Implements Set | Implements List |

---

# Common Mistake 1

Trying to store duplicate elements.

```java
set.add("Java");

set.add("Java");
```

Only one element is stored.

---

# Common Mistake 2

Trying to access elements using an index.

Incorrect:

```java
set.get(0);
```

LinkedHashSet does not support indexing.

---

# Common Mistake 3

Expecting sorted output.

LinkedHashSet maintains **insertion order**, not sorted order.

---

# LinkedHashSet Methods

| Method | Description |
|----------|-------------|
| add() | Adds an element |
| remove() | Removes an element |
| contains() | Searches an element |
| clear() | Removes all elements |
| size() | Returns the number of elements |
| isEmpty() | Checks whether the set is empty |
| iterator() | Traverses the set |

---

# Time Complexity

| Operation | Average Complexity |
|------------|--------------------|
| add() | O(1) |
| remove() | O(1) |
| contains() | O(1) |

LinkedHashSet provides almost the same performance as HashSet while preserving insertion order.
# Applications of LinkedHashSet

LinkedHashSet is widely used in applications where **duplicate elements should not be stored** and the **order of insertion must be preserved**.

Some common applications include:

- Browser History
- Search History
- Playlist Management
- Recently Viewed Products
- Student Attendance System
- Bookmarks
- Order History
- Notification History
- Unique Customer Records
- Library Management Systems

---

# Interview Questions

### 1. What is LinkedHashSet?

A `LinkedHashSet` is a class in the Java Collections Framework that stores **unique elements** while maintaining the **insertion order**.

---

### 2. Which interface does LinkedHashSet implement?

`Set`

---

### 3. Which class does LinkedHashSet extend?

`HashSet`

---

### 4. Does LinkedHashSet allow duplicate elements?

No.

Duplicate elements are automatically ignored.

Example:

```java
LinkedHashSet<String> set = new LinkedHashSet<>();

set.add("Java");

set.add("Java");

System.out.println(set);
```

Output

```text
[Java]
```

---

### 5. Does LinkedHashSet maintain insertion order?

Yes.

Elements are displayed in the same order in which they were inserted.

---

### 6. Does LinkedHashSet allow null values?

Yes.

Only **one null value** is allowed.

---

### 7. What is the difference between HashSet and LinkedHashSet?

| HashSet | LinkedHashSet |
|----------|---------------|
| Unordered | Maintains insertion order |
| Faster | Slightly slower |
| Uses Hash Table | Uses Hash Table + Linked List |

---

### 8. What is the difference between LinkedHashSet and TreeSet?

| LinkedHashSet | TreeSet |
|---------------|----------|
| Insertion order | Sorted order |
| Allows one null | Does not allow null |
| Faster | Slower |

---

### 9. Can we access elements using an index?

No.

LinkedHashSet does not support indexing.

---

### 10. What is the average time complexity of add(), remove(), and contains()?

| Operation | Complexity |
|------------|------------|
| add() | O(1) |
| remove() | O(1) |
| contains() | O(1) |

---

# Frequently Asked Interview Programs

### Program 1

Remove duplicate elements from an array while preserving insertion order.

---

### Program 2

Store unique usernames in the order of registration.

---

### Program 3

Maintain browser history without duplicate URLs.

---

### Program 4

Implement a recently viewed products list.

---

### Program 5

Store unique student attendance records.

---

# Practice Problems

## Basic Problems

1. Create a LinkedHashSet of integers.
2. Insert five numbers.
3. Remove one element.
4. Search for an element.
5. Find the size of the LinkedHashSet.
6. Check whether the LinkedHashSet is empty.
7. Traverse using a for-each loop.
8. Traverse using an Iterator.
9. Store five names without duplicates.
10. Remove all elements using `clear()`.

---

## Intermediate Problems

1. Remove duplicate words from a sentence while preserving order.
2. Store unique email IDs.
3. Create a student attendance system.
4. Merge two LinkedHashSets.
5. Find common elements between two LinkedHashSets.
6. Store unique cities.
7. Remove duplicate product IDs.
8. Maintain recently viewed products.
9. Build a browser history application.
10. Create a search history manager.

---

## Advanced Problems

1. Library Book Management System.
2. Playlist Management System.
3. Customer Order Tracking System.
4. Employee Attendance System.
5. Inventory Management System.
6. Product Recommendation History.
7. E-Commerce Recently Viewed Products.
8. Hotel Booking History.
9. Flight Reservation Records.
10. Banking Transaction History.

---

# Best Use Cases of LinkedHashSet

Use LinkedHashSet when:

- Duplicate elements should not be stored.
- Insertion order is important.
- Fast searching is required.
- Ordered unique records are needed.

Examples:

- Browser History
- Search History
- Playlist Management
- Student Attendance
- Customer Orders
- Recently Viewed Products
- Bookmarks
- Notification History

---

# When NOT to Use LinkedHashSet

Do not use LinkedHashSet when:

- Sorted order is required.
- Duplicate elements are needed.
- Random indexing is required.
- Memory usage should be minimal.

Instead, use:

- TreeSet (for sorted data)
- ArrayList (for indexed access)
- HashSet (for faster unordered storage)

---

# Summary

- LinkedHashSet stores **only unique elements**.
- It **maintains insertion order**.
- It internally uses a **Hash Table** and a **Doubly Linked List**.
- Duplicate elements are automatically ignored.
- It allows only one `null` value.
- It provides **O(1)** average time complexity for insertion, deletion, and searching.
- It is slightly slower than HashSet because it maintains insertion order.
- It is ideal for applications where uniqueness and insertion order are both important.

---

# Conclusion

`LinkedHashSet` is a powerful collection class in Java that combines the advantages of **HashSet** and a **Linked List**. It stores only unique elements while preserving the order in which they were inserted. This makes it suitable for applications such as browser history, playlists, search history, recently viewed products, and attendance systems where maintaining insertion order is essential.

By understanding LinkedHashSet and its methods, developers can efficiently manage ordered collections of unique elements and build reliable Java applications.

---

# Next Topic

```text
08_TreeSet.md
```
