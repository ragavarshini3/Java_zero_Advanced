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

The second `null` key replaces the first one.
