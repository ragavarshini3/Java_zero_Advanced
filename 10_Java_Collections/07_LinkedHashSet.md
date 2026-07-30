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
