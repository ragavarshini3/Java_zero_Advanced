# HashSet in Java

A **HashSet** is a class in the Java Collections Framework that stores **unique elements**.

Unlike a `List`, a `HashSet` **does not allow duplicate values**.

It is one of the most commonly used collection classes when uniqueness is important.

HashSet internally uses a **Hash Table** for storing data, which provides fast insertion, deletion, and searching operations.

---

# Real-World Examples

HashSet is used in many real-world applications.

Examples:

- Unique Student Registration Numbers
- Email Address Validation
- Username Availability Check
- Aadhaar Number Storage
- PAN Number Verification
- Unique Product IDs
- Vehicle Registration Numbers
- Online Voting Systems

---

# What is HashSet?

A **HashSet** is a collection that stores only **unique objects**.

If you try to insert the same element multiple times, it will be stored only once.

Example:

```text
Input

Java
Python
Java
C++
Python

Output

Java
Python
C++
```

Duplicates are automatically removed.

---

# HashSet Hierarchy

```text
Object
   │
AbstractCollection
   │
AbstractSet
   │
HashSet
```

HashSet implements the **Set Interface**.

---

# Import Statement

```java
import java.util.HashSet;
```

---

# Syntax

```java
HashSet<DataType> setName = new HashSet<>();
```

Example:

```java
HashSet<String> languages = new HashSet<>();
```

---

# Basic HashSet Program

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> languages = new HashSet<>();

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

> **Note:** The output order may vary because `HashSet` does not maintain insertion order.

---

# Internal Working of HashSet

HashSet internally uses a **Hash Table**.

When an element is inserted:

1. Java calculates the **hashCode()** of the object.
2. The hash code determines the bucket where the object should be stored.
3. If another object has the same hash code, Java uses `equals()` to check whether it is actually a duplicate.
4. If it is a duplicate, the new element is ignored.
5. Otherwise, the element is stored.

```text
Hash Table

Bucket 1 --> Java

Bucket 2 --> Python

Bucket 3 --> C++

Bucket 4 --> HTML
```

---

# Features of HashSet

- Stores only unique elements
- Does not maintain insertion order
- Allows one `null` value
- Uses hashing internally
- Provides fast search operations
- Dynamic size
- Not synchronized
- Implements the Set interface

---

# Why Use HashSet?

HashSet is useful when:

- Duplicate values should not be stored.
- Fast searching is required.
- Order is not important.
- Unique records need to be maintained.

---

# Adding Elements

Use:

```java
add()
```

Example:

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> fruits = new HashSet<>();

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

HashSet automatically ignores duplicate values.

Example:

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> subjects = new HashSet<>();

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

Even though "Java" and "Python" were added twice, they appear only once.

---

# Return Value of add()

The `add()` method returns:

- `true` → Element added successfully
- `false` → Duplicate element

Example:

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> set = new HashSet<>();

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
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> cities = new HashSet<>();

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
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> courses = new HashSet<>();

        courses.add("Java");

        courses.add("Python");

        courses.add("AI");

        System.out.println(
                courses.contains("Java"));

        System.out.println(
                courses.contains("C++"));
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
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<Integer> numbers = new HashSet<>();

        numbers.add(10);

        numbers.add(20);

        numbers.add(30);

        System.out.println(
                "Size: " + numbers.size());
    }
}
```

### Output

```text
Size: 3
```

---

# Checking Whether HashSet is Empty

Use:

```java
isEmpty()
```

Example:

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> names = new HashSet<>();

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

---

# Removing All Elements

Use:

```java
clear()
```

Example:

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> colors = new HashSet<>();

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

# Traversing a HashSet

Using Enhanced for Loop

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> students = new HashSet<>();

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
Charan
Bala
```

> The order may be different every time because HashSet does not maintain insertion order.

---

# Using Iterator

```java
import java.util.HashSet;
import java.util.Iterator;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> cities = new HashSet<>();

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
# HashSet with Integer Values

HashSet can also store integer values.

Since collections store objects, we use the **Integer** wrapper class instead of the primitive type `int`.

Example:

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<Integer> numbers = new HashSet<>();

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
[20, 10, 30]
```

The duplicate value `20` is stored only once.

---

# HashSet with null Value

HashSet allows only **one null value**.

Example:

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> data = new HashSet<>();

        data.add("Java");

        data.add(null);

        data.add(null);

        data.add("Python");

        System.out.println(data);
    }
}
```

### Output

```text
[null, Java, Python]
```

Only one `null` value is stored.

---

# Real-World Example 1: Student Registration

A college should not register the same student twice.

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> registerNumbers = new HashSet<>();

        registerNumbers.add("23AIB001");

        registerNumbers.add("23AIB002");

        registerNumbers.add("23AIB001");

        System.out.println(registerNumbers);
    }
}
```

### Output

```text
[23AIB001, 23AIB002]
```

Duplicate register numbers are automatically removed.

---

# Real-World Example 2: Username Availability

A website should not allow duplicate usernames.

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> usernames = new HashSet<>();

        usernames.add("ragavarshini");

        usernames.add("varsh");

        usernames.add("ragavarshini");

        if(usernames.add("ragavarshini"))
        {
            System.out.println("Username Created");
        }
        else
        {
            System.out.println("Username Already Exists");
        }
    }
}
```

### Output

```text
Username Already Exists
```

---

# Real-World Example 3: Online Voting System

A person should vote only once.

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> voters = new HashSet<>();

        voters.add("VOTER101");

        voters.add("VOTER102");

        if(voters.add("VOTER101"))
        {
            System.out.println("Vote Accepted");
        }
        else
        {
            System.out.println("Duplicate Vote");
        }
    }
}
```

### Output

```text
Duplicate Vote
```

---

# Real-World Example 4: Email Verification

Every email address should be unique.

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<String> emails = new HashSet<>();

        emails.add("abc@gmail.com");

        emails.add("xyz@gmail.com");

        emails.add("abc@gmail.com");

        System.out.println(emails);
    }
}
```

### Output

```text
[abc@gmail.com, xyz@gmail.com]
```

---

# Real-World Example 5: Product IDs

Every product in an e-commerce website should have a unique product ID.

```java
import java.util.HashSet;

public class Main
{
    public static void main(String[] args)
    {
        HashSet<Integer> productIds = new HashSet<>();

        productIds.add(101);

        productIds.add(102);

        productIds.add(103);

        productIds.add(101);

        System.out.println(productIds);
    }
}
```

### Output

```text
[101, 102, 103]
```

---

# Advantages of HashSet

- Stores only unique elements
- Fast insertion
- Fast searching
- Fast deletion
- Dynamic size
- Allows one null value
- Simple to use
- Good performance

---

# Limitations of HashSet

- Does not maintain insertion order
- Cannot access elements using an index
- Duplicate elements are not allowed
- Not synchronized

---

# HashSet vs ArrayList

| HashSet | ArrayList |
|----------|-----------|
| Stores unique elements | Allows duplicates |
| No indexing | Supports indexing |
| Does not maintain insertion order | Maintains insertion order |
| Fast searching | Slower searching |
| Implements Set | Implements List |

---

# HashSet vs LinkedHashSet

| HashSet | LinkedHashSet |
|----------|---------------|
| No insertion order | Maintains insertion order |
| Faster | Slightly slower |
| Uses Hash Table | Uses Hash Table + Linked List |
| Unique values | Unique values |

Example:

```java
HashSet<String> set = new HashSet<>();

LinkedHashSet<String> set2 = new LinkedHashSet<>();
```

---

# HashSet vs TreeSet

| HashSet | TreeSet |
|----------|----------|
| Unordered | Sorted |
| Faster | Slower |
| Uses Hash Table | Uses Red-Black Tree |
| Allows one null | Does not allow null |

---

# HashSet vs Vector

| HashSet | Vector |
|----------|---------|
| No duplicate elements | Duplicate elements allowed |
| No index | Index available |
| No insertion order | Maintains insertion order |
| Implements Set | Implements List |

---

# Common Mistake 1

Expecting elements to be printed in insertion order.

```java
HashSet<String> names = new HashSet<>();

names.add("A");

names.add("B");

names.add("C");

System.out.println(names);
```

Output order is unpredictable.

---

# Common Mistake 2

Trying to access an element using an index.

Incorrect:

```java
set.get(0);
```

HashSet does not support indexing.

---

# Common Mistake 3

Trying to store duplicate values.

```java
set.add("Java");

set.add("Java");
```

Only one value is stored.

---

# Common Mistake 4

Using HashSet when insertion order is important.

Instead, use:

```java
LinkedHashSet
```

---

# HashSet Methods

| Method | Description |
|----------|-------------|
| add() | Adds an element |
| remove() | Removes an element |
| contains() | Searches an element |
| clear() | Removes all elements |
| size() | Number of elements |
| isEmpty() | Checks whether empty |
| iterator() | Traverses the HashSet |

---

# Time Complexity

| Operation | Complexity |
|------------|------------|
| Add | O(1) Average |
| Remove | O(1) Average |
| Search | O(1) Average |

HashSet is one of the fastest collection classes for searching unique elements.

---

# Applications of HashSet

- Student Registration
- Employee IDs
- Aadhaar Numbers
- PAN Numbers
- Email IDs
- Usernames
- Product IDs
- Vehicle Numbers
- Online Voting
- Inventory Management
