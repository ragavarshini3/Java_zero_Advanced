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

# Interview Questions

### 1. What is HashSet?

A `HashSet` is a class in the Java Collections Framework that stores **unique elements**.

It implements the **Set** interface and internally uses a **Hash Table**.

---

### 2. Can HashSet store duplicate values?

No.

HashSet automatically ignores duplicate elements.

Example:

```java
HashSet<String> set = new HashSet<>();

set.add("Java");

set.add("Java");

System.out.println(set);
```

Output:

```text
[Java]
```

---

### 3. Does HashSet maintain insertion order?

No.

The elements are stored based on their hash values.

Therefore, the output order is unpredictable.

---

### 4. Does HashSet allow null values?

Yes.

Only **one null value** is allowed.

Example:

```java
HashSet<String> set = new HashSet<>();

set.add(null);

set.add(null);

System.out.println(set);
```

Output

```text
[null]
```

---

### 5. Which interface does HashSet implement?

`Set`

---

### 6. Which data structure is used internally?

Hash Table

---

### 7. What is the average time complexity of add(), remove(), and contains()?

Average Complexity

| Operation | Complexity |
|------------|------------|
| add() | O(1) |
| remove() | O(1) |
| contains() | O(1) |

---

### 8. Can we access elements using an index?

No.

HashSet does not support indexing.

---

### 9. Difference between HashSet and LinkedHashSet?

| HashSet | LinkedHashSet |
|----------|---------------|
| Unordered | Insertion Order |
| Faster | Slightly Slower |
| Hash Table | Hash Table + Linked List |

---

### 10. Difference between HashSet and TreeSet?

| HashSet | TreeSet |
|----------|----------|
| Unordered | Sorted |
| Faster | Slower |
| Allows one null | Doesn't allow null |

---

# Frequently Asked Interview Programs

### Program 1

Remove duplicate numbers from an array using HashSet.

### Program 2

Find common elements between two arrays.

### Program 3

Count unique words in a paragraph.

### Program 4

Store unique email IDs.

### Program 5

Remove duplicate characters from a string.

---

# Practice Problems

## Basic Problems

1. Create a HashSet of integers.
2. Insert five numbers.
3. Display all elements.
4. Remove one element.
5. Search an element using contains().
6. Find the total number of elements.
7. Check whether the HashSet is empty.
8. Remove all elements.
9. Store five names without duplicates.
10. Traverse a HashSet using a for-each loop.

---

## Intermediate Problems

1. Remove duplicate integers from an array.
2. Count unique elements.
3. Store unique city names.
4. Create a student registration system.
5. Store unique email IDs.
6. Find common elements between two HashSets.
7. Merge two HashSets.
8. Remove all duplicate words from a sentence.
9. Find missing numbers using HashSet.
10. Implement a username availability checker.

---

## Advanced Problems

1. Build a Library Book Management System using HashSet.
2. Online Voting System using unique voter IDs.
3. Employee ID Management.
4. Inventory Management System.
5. Duplicate File Detector.
6. Social Media Username Checker.
7. Product Catalog Management.
8. Vehicle Registration System.
9. Student Attendance Management.
10. Hospital Patient Record System.

---

# Best Use Cases of HashSet

HashSet is preferred when:

- Duplicate values should not be stored.
- Searching should be very fast.
- Order is not important.
- Large datasets are involved.
- Unique records must be maintained.

Examples:

- Aadhaar Numbers
- PAN Numbers
- Passport Numbers
- Employee IDs
- Student Register Numbers
- Product IDs
- Email IDs
- Usernames

---

# When NOT to Use HashSet

Do not use HashSet when:

- Insertion order is important.
- Elements must be sorted.
- Random indexing is required.
- Duplicate elements are needed.

Instead use:

- ArrayList
- LinkedHashSet
- TreeSet

---

# Summary

- HashSet stores **only unique elements**.
- Duplicate values are automatically ignored.
- HashSet implements the **Set** interface.
- It internally uses a **Hash Table**.
- It provides **O(1)** average time complexity for insertion, deletion, and searching.
- It does not maintain insertion order.
- It allows only one `null` value.
- It is widely used for storing unique records.

---

# Conclusion

`HashSet` is one of the most efficient collection classes in Java for storing **unique elements**. It offers excellent performance for insertion, deletion, and searching by using a **Hash Table** internally. Since it does not maintain insertion order, it is best suited for applications where uniqueness and speed are more important than ordering.

HashSet is commonly used in real-world applications such as user registration systems, email validation, inventory management, product catalogs, voter registration, student records, and duplicate detection systems. Mastering HashSet helps developers build efficient and scalable Java applications.

---

# Next Topic

```text
07_LinkedHashSet.md
```
