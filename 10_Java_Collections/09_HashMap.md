# HashMap in Java

A **HashMap** is one of the most commonly used classes in the Java Collections Framework.

It is used to store data as **key-value pairs**.

Unlike `ArrayList`, `HashSet`, or `TreeSet`, a `HashMap` stores data using a **unique key** and its corresponding **value**.

HashMap provides fast insertion, deletion, and searching operations by internally using a **Hash Table**.

---

# Real-World Examples
 
HashMap is used in many real-world applications. 

Examples:

- Student ID → Student Name
- Employee ID → Employee Details
- Product ID → Product Name
- Roll Number → Student Marks
- Username → Password
- Country Code → Country Name
- Mobile Number → Customer Name
- Book ID → Book Title

---

# What is a HashMap?

A **HashMap** stores data in the form of:

```text
Key → Value
```

Example:

```text
101 → Ragavarshini

102 → Priya

103 → Kavin
```

Each key must be unique.

Values can be duplicated.

---

# HashMap Hierarchy

```text
Object
   │
AbstractMap
   │
HashMap
```

HashMap implements the **Map Interface**.

---

# Import Statement

```java
import java.util.HashMap;
```

---

# Syntax

```java
HashMap<KeyType, ValueType> mapName = new HashMap<>();
```

Example:

```java
HashMap<Integer, String> students = new HashMap<>();
```

---

# Basic HashMap Program

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
    }
}
```

### Output

```text
{101=Anu, 102=Bala, 103=Charan}
```

---

# Internal Working of HashMap

HashMap internally uses a **Hash Table**.

Working Process:

1. Java calculates the **hashCode()** of the key.
2. The hash code determines the bucket.
3. The key-value pair is stored in that bucket.
4. If another key has the same hash value, Java handles it using hashing techniques.

Example:

```text
Bucket 1

101 → Anu

Bucket 2

102 → Bala

Bucket 3

103 → Charan
```

---

# Features of HashMap

- Stores key-value pairs
- Keys must be unique
- Values can be duplicated
- Allows one null key
- Allows multiple null values
- Dynamic size
- Fast searching
- Fast insertion
- Fast deletion
- Not synchronized

---

# Why Use HashMap?

HashMap is useful when:

- Fast searching is required.
- Data should be stored using unique keys.
- Large amounts of data must be managed efficiently.

---

# Adding Elements

Use:

```java
put()
```

Example:

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
    }
}
```

### Output

```text
{101=Anu, 102=Bala, 103=Charan}
```

---

# Duplicate Keys

HashMap does not allow duplicate keys.

If the same key is inserted again, the old value is replaced.

Example:

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(101, "Priya");

        System.out.println(students);
    }
}
```

### Output

```text
{101=Priya}
```

---

# Duplicate Values

Duplicate values are allowed.

Example:

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(102, "Anu");

        students.put(103, "Priya");

        System.out.println(students);
    }
}
```

### Output

```text
{101=Anu, 102=Anu, 103=Priya}
```

---

# Getting a Value

Use:

```java
get()
```

Example:

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

        System.out.println(students.get(102));
    }
}
```

### Output

```text
Bala
```

---

# Updating a Value

Use:

```java
put()
```

Example:

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(102, "Bala");

        students.put(102, "Priya");

        System.out.println(students);
    }
}
```

### Output

```text
{101=Anu, 102=Priya}
```

---

# Removing an Element

Use:

```java
remove()
```

Example:

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

        students.remove(102);

        System.out.println(students);
    }
}
```

### Output

```text
{101=Anu, 103=Charan}
```

---

# Searching a Key

Use:

```java
containsKey()
```

Example:

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(102, "Bala");

        System.out.println(students.containsKey(101));

        System.out.println(students.containsKey(105));
    }
}
```

### Output

```text
true

false
```

---

# Searching a Value

Use:

```java
containsValue()
```

Example:

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(102, "Bala");

        System.out.println(students.containsValue("Anu"));

        System.out.println(students.containsValue("Priya"));
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
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(102, "Bala");

        students.put(103, "Charan");

        System.out.println("Size : " + students.size());
    }
}
```

### Output

```text
Size : 3
```

---

# Checking Whether HashMap is Empty

Use:

```java
isEmpty()
```

Example:

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        System.out.println(students.isEmpty());

        students.put(101, "Anu");

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
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(102, "Bala");

        students.put(103, "Charan");

        System.out.println("Before : " + students);

        students.clear();

        System.out.println("After : " + students);
    }
}
```

### Output

```text
Before : {101=Anu, 102=Bala, 103=Charan}

After : {}
```

---

# Important Note

HashMap:

- Allows only **one null key**
- Allows **multiple null values**

Example:

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> map = new HashMap<>();

        map.put(null, "Java");

        map.put(null, "Python");

        map.put(101, null);

        map.put(102, null);

        System.out.println(map);
    }
}
```

### Output

```text
{null=Python, 101=null, 102=null}
```
# Getting All Keys

Use:

```java
keySet()
```

It returns all the keys present in the HashMap.

Example:

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

        System.out.println(students.keySet());
    }
}
```

### Output

```text
[101, 102, 103]
```

---

# Getting All Values

Use:

```java
values()
```

It returns all the values present in the HashMap.

Example:

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

        System.out.println(students.values());
    }
}
```

### Output

```text
[Anu, Bala, Charan]
```

---

# Getting Key-Value Pairs

Use:

```java
entrySet()
```

Example:

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

        System.out.println(students.entrySet());
    }
}
```

### Output

```text
[101=Anu, 102=Bala, 103=Charan]
```

---

# Traversing Using keySet()

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

        for(Integer key : students.keySet())
        {
            System.out.println(
                key + " -> " + students.get(key)
            );
        }
    }
}
```

### Output

```text
101 -> Anu
102 -> Bala
103 -> Charan
```

---

# Traversing Using entrySet()

```java
import java.util.HashMap;
import java.util.Map;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(102, "Bala");

        students.put(103, "Charan");

        for(Map.Entry<Integer, String> entry : students.entrySet())
        {
            System.out.println(
                entry.getKey() + " -> " +
                entry.getValue()
            );
        }
    }
}
```

### Output

```text
101 -> Anu
102 -> Bala
103 -> Charan
```

---

# Traversing Using Iterator

```java
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(102, "Bala");

        students.put(103, "Charan");

        Iterator<Map.Entry<Integer, String>> iterator =
                students.entrySet().iterator();

        while(iterator.hasNext())
        {
            Map.Entry<Integer, String> entry =
                    iterator.next();

            System.out.println(
                    entry.getKey() + " : " +
                    entry.getValue());
        }
    }
}
```

---

# Replacing a Value

Use:

```java
replace()
```

Example:

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.put(102, "Bala");

        students.replace(102, "Priya");

        System.out.println(students);
    }
}
```

### Output

```text
{101=Anu, 102=Priya}
```

---

# Replacing All Values

Use:

```java
replaceAll()
```

Example

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, Integer> marks = new HashMap<>();

        marks.put(101, 80);

        marks.put(102, 70);

        marks.put(103, 90);

        marks.replaceAll(
                (key, value) -> value + 5
        );

        System.out.println(marks);
    }
}
```

### Output

```text
{101=85, 102=75, 103=95}
```

---

# putIfAbsent()

Adds the key-value pair only if the key is not already present.

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        students.putIfAbsent(101, "Priya");

        students.putIfAbsent(102, "Bala");

        System.out.println(students);
    }
}
```

### Output

```text
{101=Anu, 102=Bala}
```

---

# getOrDefault()

Returns the value if the key exists.

Otherwise returns the default value.

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> students = new HashMap<>();

        students.put(101, "Anu");

        System.out.println(
                students.getOrDefault(
                        101,
                        "Not Found"));

        System.out.println(
                students.getOrDefault(
                        105,
                        "Not Found"));
    }
}
```

### Output

```text
Anu

Not Found
```

---

# computeIfAbsent()

Computes a value only if the key does not exist.

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> map = new HashMap<>();

        map.computeIfAbsent(
                101,
                key -> "Java");

        map.computeIfAbsent(
                101,
                key -> "Python");

        System.out.println(map);
    }
}
```

### Output

```text
{101=Java}
```

---

# computeIfPresent()

Computes a value only if the key exists.

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, Integer> marks = new HashMap<>();

        marks.put(101, 80);

        marks.computeIfPresent(
                101,
                (key, value) -> value + 10
        );

        System.out.println(marks);
    }
}
```

### Output

```text
{101=90}
```

---

# Real-World Example 1: Student Marks

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, Integer> marks = new HashMap<>();

        marks.put(101, 450);

        marks.put(102, 480);

        marks.put(103, 420);

        for(Integer roll : marks.keySet())
        {
            System.out.println(
                "Roll No : " + roll +
                " Marks : " +
                marks.get(roll));
        }
    }
}
```

---

# Real-World Example 2: Employee Database

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> employees = new HashMap<>();

        employees.put(1001, "Ravi");

        employees.put(1002, "Priya");

        employees.put(1003, "Arun");

        System.out.println(employees);
    }
}
```

---

# Real-World Example 3: Product Catalog

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<Integer, String> products = new HashMap<>();

        products.put(1, "Laptop");

        products.put(2, "Mouse");

        products.put(3, "Keyboard");

        System.out.println(products);
    }
}
```

---

# Real-World Example 4: Country Codes

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<String, String> countries = new HashMap<>();

        countries.put("IN", "India");

        countries.put("US", "United States");

        countries.put("JP", "Japan");

        System.out.println(countries);
    }
}
```

---

# Real-World Example 5: Username and Password

```java
import java.util.HashMap;

public class Main
{
    public static void main(String[] args)
    {
        HashMap<String, String> login = new HashMap<>();

        login.put("admin", "12345");

        login.put("student", "java@123");

        System.out.println(login);
    }
}
```

---

# Advantages of HashMap

- Stores data as key-value pairs
- Fast insertion
- Fast searching
- Fast deletion
- Dynamic size
- Allows one null key
- Allows multiple null values
- Easy to use

---

# Limitations of HashMap

- Does not maintain insertion order
- Keys must be unique
- Not synchronized
- No indexing support

---

# HashMap vs HashSet

| HashMap | HashSet |
|----------|----------|
| Stores key-value pairs | Stores only values |
| Implements Map | Implements Set |
| Keys must be unique | Elements must be unique |
| Values may repeat | No duplicates |

---

# HashMap vs LinkedHashMap

| HashMap | LinkedHashMap |
|----------|---------------|
| No insertion order | Maintains insertion order |
| Faster | Slightly slower |
| Uses Hash Table | Uses Hash Table + Linked List |

---

# HashMap vs TreeMap

| HashMap | TreeMap |
|----------|---------|
| Unordered | Sorted by key |
| O(1) Average | O(log n) |
| One null key allowed | Null keys are not allowed |
| Uses Hash Table | Uses Red-Black Tree |

---

# Common Mistake 1

Using duplicate keys.

```java
map.put(101, "Anu");

map.put(101, "Priya");
```

The old value is replaced.

---

# Common Mistake 2

Expecting insertion order.

HashMap does not maintain insertion order.

---

# Common Mistake 3

Using `get()` with a key that does not exist.

```java
System.out.println(map.get(999));
```

Output

```text
null
```

Always check:

```java
containsKey()
```

before accessing the value.

# Applications of HashMap

HashMap is widely used in real-world applications where data is stored as **key-value pairs**.

Some common applications include:

- Student Management System
- Employee Database
- Banking Applications
- Product Catalog
- Library Management
- E-Commerce Websites
- Hospital Management
- Online Shopping Carts
- Login Authentication
- Inventory Management

---

# Interview Questions

### 1. What is HashMap?

A `HashMap` is a class in the Java Collections Framework that stores data as **key-value pairs**.

It implements the **Map** interface.

---

### 2. Which interface does HashMap implement?

```text
Map
```

---

### 3. Can HashMap store duplicate keys?

No.

Duplicate keys replace the previous value.

Example

```java
HashMap<Integer, String> map = new HashMap<>();

map.put(101, "Anu");

map.put(101, "Priya");

System.out.println(map);
```

### Output

```text
{101=Priya}
```

---

### 4. Can HashMap store duplicate values?

Yes.

Multiple keys can have the same value.

---

### 5. Does HashMap maintain insertion order?

No.

The order of elements is not guaranteed.

---

### 6. Does HashMap allow null values?

Yes.

- One null key
- Multiple null values

Example

```java
HashMap<Integer, String> map = new HashMap<>();

map.put(null, "Java");

map.put(101, null);

map.put(102, null);

System.out.println(map);
```

---

### 7. Which data structure is used internally?

HashMap internally uses a **Hash Table**.

(Java 8 and later may also use balanced tree structures for heavily populated buckets.)

---

### 8. What is the average time complexity of add(), remove(), and search?

| Operation | Complexity |
|------------|------------|
| put() | O(1) |
| get() | O(1) |
| remove() | O(1) |
| containsKey() | O(1) |

---

### 9. Difference between HashMap and HashSet?

| HashMap | HashSet |
|----------|----------|
| Stores key-value pairs | Stores only values |
| Implements Map | Implements Set |
| Keys must be unique | Elements must be unique |

---

### 10. Difference between HashMap and TreeMap?

| HashMap | TreeMap |
|----------|----------|
| Unordered | Sorted by key |
| O(1) Average | O(log n) |
| Allows one null key | Null keys are not allowed |

---

### 11. Difference between HashMap and LinkedHashMap?

| HashMap | LinkedHashMap |
|----------|---------------|
| No insertion order | Maintains insertion order |
| Faster | Slightly slower |

---

### 12. What happens if the same key is inserted again?

The old value is replaced by the new value.

---

### 13. What is the difference between containsKey() and containsValue()?

| Method | Description |
|----------|-------------|
| containsKey() | Checks whether a key exists |
| containsValue() | Checks whether a value exists |

---

### 14. How do you traverse a HashMap?

Using:

- keySet()
- values()
- entrySet()
- Iterator

---

### 15. Can HashMap be synchronized?

No.

For thread-safe operations, consider using synchronized wrappers or concurrent map implementations depending on the application.

---

# Frequently Asked Interview Programs

### Program 1

Store student names using roll numbers as keys.

---

### Program 2

Create an employee database.

---

### Program 3

Count the frequency of words in a sentence.

---

### Program 4

Count the frequency of characters in a string.

---

### Program 5

Store product IDs and product names.

---

### Program 6

Create a login authentication system.

---

### Program 7

Store country codes and country names.

---

### Program 8

Maintain inventory details.

---

### Program 9

Create a phone directory.

---

### Program 10

Implement a library management system.

---

# Practice Problems

## Basic Problems

### Problem 1

Create a HashMap of student names.

---

### Problem 2

Insert five key-value pairs.

---

### Problem 3

Display all keys.

---

### Problem 4

Display all values.

---

### Problem 5

Display all key-value pairs.

---

### Problem 6

Update a value.

---

### Problem 7

Remove one key.

---

### Problem 8

Check whether a key exists.

---

### Problem 9

Check whether a value exists.

---

### Problem 10

Find the size of the HashMap.

---

# Intermediate Problems

### Problem 1

Create a student mark management system.

---

### Problem 2

Store employee salaries.

---

### Problem 3

Create a product catalog.

---

### Problem 4

Maintain country codes.

---

### Problem 5

Create a library book database.

---

### Problem 6

Store username-password pairs.

---

### Problem 7

Implement a phone directory.

---

### Problem 8

Count word frequency in a paragraph.

---

### Problem 9

Count character frequency in a string.

---

### Problem 10

Create an online shopping cart.

---

# Advanced Problems

### Problem 1

Bank Account Management System.

---

### Problem 2

Hospital Patient Record System.

---

### Problem 3

Library Management System.

---

### Problem 4

Inventory Management System.

---

### Problem 5

Student Information System.

---

### Problem 6

Online Banking Application.

---

### Problem 7

Restaurant Billing System.

---

### Problem 8

Customer Relationship Management (CRM).

---

### Problem 9

Hotel Booking Management System.

---

### Problem 10

E-Commerce Product Management System.

---

# Best Use Cases of HashMap

HashMap is best suited for applications where:

- Data is naturally represented as key-value pairs.
- Fast searching is required.
- Keys are unique.
- Large datasets need efficient access.

Examples:

- Employee Records
- Student Database
- Product Catalog
- Banking Systems
- Login Authentication
- Phone Directory
- Library Management
- Inventory Systems
- Shopping Applications
- Hospital Management

---

# When NOT to Use HashMap

Avoid using HashMap when:

- Insertion order must be preserved.
- Keys should always remain sorted.
- Index-based access is required.

Instead use:

- LinkedHashMap
- TreeMap
- ArrayList

---

# Summary

- HashMap stores **key-value pairs**.
- Keys are **unique**.
- Values can be **duplicated**.
- It implements the **Map** interface.
- Internally, it uses a **Hash Table**.
- It allows one **null key** and multiple **null values**.
- It provides average **O(1)** time complexity for insertion, deletion, and searching.
- It is one of the most widely used collection classes in Java.

---

# Conclusion

`HashMap` is one of the most powerful and frequently used classes in the Java Collections Framework. It enables efficient storage and retrieval of data using **unique keys** and their corresponding **values**. Because of its fast average performance and flexible key-value structure, HashMap is widely used in real-world applications such as student databases, banking systems, e-commerce platforms, inventory management, and authentication systems.

Understanding HashMap is essential for Java developers because it forms the foundation for solving many coding problems and designing scalable applications.

---

# Next Topic

```text
10_LinkedHashMap.md
```

The second `null` key replaces the first one.
