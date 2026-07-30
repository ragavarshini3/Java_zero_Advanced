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
