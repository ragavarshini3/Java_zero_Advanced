# TreeSet in Java

A **TreeSet** is a class in the Java Collections Framework that stores **unique elements in sorted order**.

Unlike `HashSet` and `LinkedHashSet`, a `TreeSet` automatically arranges elements in **ascending order** (natural sorting).

Internally, `TreeSet` uses a **Red-Black Tree**, which is a self-balancing Binary Search Tree.

---

# Real-World Examples

TreeSet is used in applications where:  
 
- Duplicate values should not be stored.
- Data should always remain sorted.

Examples:

- Student Rank List
- Leaderboards
- Dictionary Applications
- Contact List
- Product Catalog
- Exam Marks
- Employee IDs
- Train Timetable

---

# What is TreeSet?

A **TreeSet** is a collection that stores only **unique elements** in **sorted order**.

Example:

```text
Input

50
20
40
10
30
20

Output

10
20
30
40
50
```

Duplicates are removed automatically.

---

# TreeSet Hierarchy

```text
Object
   │
AbstractCollection
   │
AbstractSet
   │
TreeSet
```

TreeSet implements:

- Set
- NavigableSet
- SortedSet

---

# Import Statement

```java
import java.util.TreeSet;
```

---

# Syntax

```java
TreeSet<DataType> setName = new TreeSet<>();
```

Example:

```java
TreeSet<Integer> numbers = new TreeSet<>();
```

---

# Basic TreeSet Program

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(50);

        numbers.add(10);

        numbers.add(30);

        numbers.add(20);

        System.out.println(numbers);
    }
}
```

### Output

```text
[10, 20, 30, 50]
```

Notice that the elements are automatically sorted.

---

# Internal Working of TreeSet

TreeSet internally uses a **Red-Black Tree**.

A Red-Black Tree is a self-balancing Binary Search Tree.

Whenever an element is inserted:

1. TreeSet compares the element.
2. Finds the correct position.
3. Balances the tree.
4. Stores the element.

Example:

```text
Input

40
20
60
10
30
50
70
```

Tree Structure

```text
          40
        /    \
      20      60
     /  \    /  \
   10   30 50   70
```

Elements are always maintained in sorted order.

---

# Features of TreeSet

- Stores unique elements
- Automatically sorts elements
- Does not maintain insertion order
- Uses Red-Black Tree
- No duplicate values
- No indexing
- Dynamic size
- Not synchronized

---

# Why Use TreeSet?

Use TreeSet when:

- Data should remain sorted.
- Duplicate values are not allowed.
- Fast searching is required.
- Ordered records are needed.

---

# Adding Elements

Use:

```java
add()
```

Example

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<String> fruits = new TreeSet<>();

        fruits.add("Mango");

        fruits.add("Apple");

        fruits.add("Banana");

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

Duplicates are ignored.

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<String> languages = new TreeSet<>();

        languages.add("Java");

        languages.add("Python");

        languages.add("Java");

        System.out.println(languages);
    }
}
```

### Output

```text
[Java, Python]
```

---

# Return Value of add()

Returns

- true → inserted successfully
- false → duplicate

Example

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<String> set = new TreeSet<>();

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

Use

```java
remove()
```

Example

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(10);

        numbers.add(20);

        numbers.add(30);

        numbers.remove(20);

        System.out.println(numbers);
    }
}
```

### Output

```text
[10, 30]
```

---

# Searching an Element

Use

```java
contains()
```

Example

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<String> courses = new TreeSet<>();

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

Use

```java
size()
```

Example

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(10);

        numbers.add(20);

        numbers.add(30);

        System.out.println("Size : " + numbers.size());
    }
}
```

### Output

```text
Size : 3
```

---

# Checking Whether TreeSet is Empty

Use

```java
isEmpty()
```

Example

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<String> names = new TreeSet<>();

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

Use

```java
clear()
```

Example

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<String> colors = new TreeSet<>();

        colors.add("Red");

        colors.add("Green");

        colors.add("Blue");

        System.out.println("Before : " + colors);

        colors.clear();

        System.out.println("After : " + colors);
    }
}
```

### Output

```text
Before : [Blue, Green, Red]

After : []
```

---

# Traversing TreeSet

Using Enhanced for Loop

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(50);

        numbers.add(20);

        numbers.add(10);

        numbers.add(40);

        for(Integer number : numbers)
        {
            System.out.println(number);
        }
    }
}
```

### Output

```text
10
20
40
50
```

---

# Traversing Using Iterator

```java
import java.util.Iterator;
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<String> cities = new TreeSet<>();

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
Coimbatore
Madurai
```

---

# TreeSet with Integer Values

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(40);

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
[10, 20, 30, 40]
```

---

# TreeSet with String Values

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<String> languages = new TreeSet<>();

        languages.add("Python");

        languages.add("Java");

        languages.add("C");

        languages.add("C++");

        System.out.println(languages);
    }
}
```

### Output

```text
[C, C++, Java, Python]
```

---

# Important Note

TreeSet **does not allow null values**.

Example

```java
TreeSet<String> set = new TreeSet<>();

set.add(null);
```

This throws

```text
NullPointerException
```

because TreeSet needs to compare elements for sorting.

---

# First Element

Use

```java
first()
```

Example

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(50);

        numbers.add(20);

        numbers.add(10);

        System.out.println(numbers.first());
    }
}
```

### Output

```text
10
```

---

# Last Element

Use

```java
last()
```

Example

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(50);

        numbers.add(20);

        numbers.add(10);

        System.out.println(numbers.last());
    }
}
```

### Output

```text
50
```

---

# Higher Element

Returns the smallest element greater than the given element.

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(10);

        numbers.add(20);

        numbers.add(30);

        numbers.add(40);

        System.out.println(numbers.higher(20));
    }
}
```

### Output

```text
30
```

---

# Lower Element

Returns the greatest element smaller than the given element.

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> numbers = new TreeSet<>();

        numbers.add(10);

        numbers.add(20);

        numbers.add(30);

        numbers.add(40);

        System.out.println(numbers.lower(20));
    }
}
```

### Output

```text
10
```

---

# Ceiling Element

Returns the given element if present.

Otherwise returns the next greater element.

```java
numbers.ceiling(25);
```

Output

```text
30
```

---

# Floor Element

Returns the given element if present.

Otherwise returns the next smaller element.

```java
numbers.floor(25);
```

Output

```text
20
```

---

# Poll First

Removes and returns the first element.

```java
numbers.pollFirst();
```

---

# Poll Last

Removes and returns the last element.

```java
numbers.pollLast();
```

---

# Descending Order

```java
System.out.println(numbers.descendingSet());
```

Example Output

```text
[50, 40, 30, 20, 10]
```

---

# TreeSet Methods

| Method | Description |
|----------|-------------|
| add() | Adds an element |
| remove() | Removes an element |
| contains() | Searches an element |
| size() | Returns number of elements |
| clear() | Removes all elements |
| first() | Returns first element |
| last() | Returns last element |
| higher() | Returns next greater element |
| lower() | Returns next smaller element |
| ceiling() | Returns nearest greater or equal |
| floor() | Returns nearest smaller or equal |
| pollFirst() | Removes first element |
| pollLast() | Removes last element |
| descendingSet() | Returns descending order |
| iterator() | Traverses TreeSet |

# Real-World Example 1: Student Rank List

A college wants to display student marks in ascending order.

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> marks = new TreeSet<>();

        marks.add(450);

        marks.add(390);

        marks.add(480);

        marks.add(420);

        marks.add(390);

        System.out.println("Sorted Marks: " + marks);
    }
}
```

### Output

```text
Sorted Marks: [390, 420, 450, 480]
```

---

# Real-World Example 2: Product Price List

An online shopping website wants to display product prices in ascending order.

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> prices = new TreeSet<>();

        prices.add(2500);

        prices.add(1500);

        prices.add(3200);

        prices.add(1800);

        System.out.println(prices);
    }
}
```

### Output

```text
[1500, 1800, 2500, 3200]
```

---

# Real-World Example 3: Dictionary Application

Dictionary words should appear alphabetically.

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<String> dictionary = new TreeSet<>();

        dictionary.add("Orange");

        dictionary.add("Apple");

        dictionary.add("Banana");

        dictionary.add("Mango");

        System.out.println(dictionary);
    }
}
```

### Output

```text
[Apple, Banana, Mango, Orange]
```

---

# Real-World Example 4: Employee IDs

A company stores employee IDs in sorted order.

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> employeeIds = new TreeSet<>();

        employeeIds.add(105);

        employeeIds.add(101);

        employeeIds.add(108);

        employeeIds.add(103);

        System.out.println(employeeIds);
    }
}
```

### Output

```text
[101, 103, 105, 108]
```

---

# Real-World Example 5: Leaderboard

Display player scores in sorted order.

```java
import java.util.TreeSet;

public class Main
{
    public static void main(String[] args)
    {
        TreeSet<Integer> scores = new TreeSet<>();

        scores.add(980);

        scores.add(1200);

        scores.add(860);

        scores.add(1500);

        System.out.println(scores);

        System.out.println(
                "Highest Score : " +
                scores.last());
    }
}
```

### Output

```text
[860, 980, 1200, 1500]

Highest Score : 1500
```

---

# Advantages of TreeSet

- Stores unique elements
- Automatically sorts data
- Fast searching
- Dynamic size
- Supports navigation methods
- Implements NavigableSet
- Good for sorted data

---

# Limitations of TreeSet

- Does not allow duplicate elements
- Does not maintain insertion order
- Does not support indexing
- Does not allow null values
- Slower than HashSet for insertion

---

# TreeSet vs HashSet

| TreeSet | HashSet |
|----------|----------|
| Sorted order | Unordered |
| Uses Red-Black Tree | Uses Hash Table |
| Slower | Faster |
| No null value | One null allowed |
| Navigable methods available | Navigation methods unavailable |

---

# TreeSet vs LinkedHashSet

| TreeSet | LinkedHashSet |
|----------|---------------|
| Sorted order | Insertion order |
| Red-Black Tree | Hash Table + Linked List |
| Slower | Faster |
| No null | One null allowed |

---

# TreeSet vs ArrayList

| TreeSet | ArrayList |
|----------|-----------|
| Sorted automatically | Manual sorting required |
| No duplicates | Duplicates allowed |
| No indexing | Supports indexing |
| Implements Set | Implements List |

---

# TreeSet vs HashMap

| TreeSet | HashMap |
|----------|----------|
| Stores only values | Stores key-value pairs |
| Sorted values | Unordered keys |
| Implements Set | Implements Map |

---

# Common Mistake 1

Trying to insert duplicate values.

```java
set.add(100);

set.add(100);
```

Only one value is stored.

---

# Common Mistake 2

Trying to insert null.

```java
TreeSet<String> set = new TreeSet<>();

set.add(null);
```

Output

```text
NullPointerException
```

---

# Common Mistake 3

Expecting insertion order.

```java
TreeSet<Integer> set = new TreeSet<>();

set.add(30);

set.add(10);

set.add(20);
```

Output

```text
[10, 20, 30]
```

The order is sorted, **not insertion order**.

---

# Common Mistake 4

Trying to access elements using an index.

Incorrect:

```java
set.get(0);
```

TreeSet does not support indexing.

---

# Common Mistake 5

Assuming TreeSet is faster than HashSet.

HashSet is generally faster for insertion and searching because it uses a Hash Table.

TreeSet provides sorting, which introduces additional overhead.

---

# Time Complexity

| Operation | Complexity |
|------------|------------|
| add() | O(log n) |
| remove() | O(log n) |
| contains() | O(log n) |
| first() | O(log n) |
| last() | O(log n) |
| higher() | O(log n) |
| lower() | O(log n) |

TreeSet operations are based on the Red-Black Tree.

---

# Applications of TreeSet

TreeSet is widely used in applications where sorted unique data is required.

Some common applications include:

- Student Rank List
- Employee Records
- Product Catalog
- Dictionary Applications
- Leaderboards
- Railway Timetables
- Hospital Priority Records
- Library Book Index
- Contact Management
- Banking Applications
# Interview Questions

### 1. What is TreeSet?

A `TreeSet` is a class in the Java Collections Framework that stores **unique elements in sorted order**.

It internally uses a **Red-Black Tree**.

---

### 2. Which interface does TreeSet implement?

TreeSet implements:

- Set
- SortedSet
- NavigableSet

---

### 3. Does TreeSet allow duplicate elements?

No.

Duplicate elements are automatically ignored.

Example:

```java
TreeSet<Integer> set = new TreeSet<>();

set.add(10);

set.add(10);

System.out.println(set);
```

### Output

```text
[10]
```

---

### 4. Does TreeSet maintain insertion order?

No.

TreeSet maintains **sorted order**, not insertion order.

---

### 5. Does TreeSet allow null values?

No.

Trying to insert a null value throws a `NullPointerException`.

---

### 6. Which data structure is used internally?

TreeSet internally uses a **Red-Black Tree**.

---

### 7. What is the average time complexity of add(), remove(), and contains()?

| Operation | Complexity |
|------------|------------|
| add() | O(log n) |
| remove() | O(log n) |
| contains() | O(log n) |

---

### 8. Can we access elements using an index?

No.

TreeSet does not support indexing.

---

### 9. Difference between TreeSet and HashSet?

| TreeSet | HashSet |
|----------|----------|
| Sorted order | Unordered |
| Red-Black Tree | Hash Table |
| O(log n) | O(1) Average |
| No null | One null allowed |

---

### 10. Difference between TreeSet and LinkedHashSet?

| TreeSet | LinkedHashSet |
|----------|---------------|
| Sorted order | Insertion order |
| Red-Black Tree | Hash Table + Linked List |
| No null | One null allowed |

---

### 11. Which methods return the first and last elements?

```java
first();

last();
```

---

### 12. Which methods return the next greater and next smaller elements?

```java
higher();

lower();
```

---

### 13. What is the difference between ceiling() and higher()?

| Method | Description |
|----------|-------------|
| higher() | Strictly greater element |
| ceiling() | Greater or equal element |

Example:

```text
TreeSet

10 20 30 40
```

```java
higher(20) → 30

ceiling(20) → 20

ceiling(25) → 30
```

---

### 14. What is the difference between floor() and lower()?

| Method | Description |
|----------|-------------|
| lower() | Strictly smaller element |
| floor() | Smaller or equal element |

---

### 15. Can TreeSet store custom objects?

Yes.

But custom objects must implement:

- Comparable

or

- Comparator

for sorting.

---

# Frequently Asked Interview Programs

### Program 1

Sort student marks using TreeSet.

---

### Program 2

Remove duplicate numbers and display them in ascending order.

---

### Program 3

Display highest and lowest marks.

---

### Program 4

Find the next greater element using `higher()`.

---

### Program 5

Display elements in descending order.

---

### Program 6

Create a contact list in alphabetical order.

---

### Program 7

Create a leaderboard using TreeSet.

---

### Program 8

Display train timings in sorted order.

---

### Program 9

Maintain product prices in ascending order.

---

### Program 10

Create a dictionary application.

---

# Practice Problems

## Basic Problems

### Problem 1

Create a TreeSet of integers.

Insert:

```text
40
20
50
10
30
```

Display the output.

---

### Problem 2

Store five names.

Display them in alphabetical order.

---

### Problem 3

Remove one element.

Display the updated TreeSet.

---

### Problem 4

Search for an element using:

```java
contains()
```

---

### Problem 5

Display:

- First Element
- Last Element

using:

```java
first()

last()
```

---

### Problem 6

Display the number of elements.

---

### Problem 7

Check whether the TreeSet is empty.

---

### Problem 8

Traverse using an Enhanced for Loop.

---

### Problem 9

Traverse using an Iterator.

---

### Problem 10

Remove all elements using:

```java
clear()
```

---

# Intermediate Problems

### Problem 1

Remove duplicate integers from an array.

---

### Problem 2

Display all numbers in descending order.

---

### Problem 3

Find the next greater element using:

```java
higher()
```

---

### Problem 4

Find the previous smaller element using:

```java
lower()
```

---

### Problem 5

Display the nearest greater element using:

```java
ceiling()
```

---

### Problem 6

Display the nearest smaller element using:

```java
floor()
```

---

### Problem 7

Store employee IDs in sorted order.

---

### Problem 8

Create a student rank list.

---

### Problem 9

Maintain product prices.

---

### Problem 10

Display alphabetical city names.

---

# Advanced Problems

### Problem 1

Create a Library Book Management System.

---

### Problem 2

Create a Product Catalog.

---

### Problem 3

Create a Student Ranking System.

---

### Problem 4

Create a Railway Timetable Management System.

---

### Problem 5

Create a Contact Management Application.

---

### Problem 6

Create an Online Leaderboard.

---

### Problem 7

Create a Hospital Patient Priority System.

---

### Problem 8

Create a Banking Customer Management System.

---

### Problem 9

Create a Dictionary Application.

---

### Problem 10

Create an Inventory Management System.

---

# Best Use Cases of TreeSet

TreeSet is best suited for applications where:

- Duplicate values should not be stored.
- Data must always remain sorted.
- Navigation operations are required.
- Fast searching in sorted data is needed.

Examples:

- Leaderboards
- Student Rankings
- Product Catalogs
- Dictionary Applications
- Contact Lists
- Employee Records
- Library Systems
- Banking Applications
- Hospital Priority Records
- Exam Results

---

# When NOT to Use TreeSet

Do not use TreeSet when:

- Insertion order should be maintained.
- Duplicate values are required.
- Fast O(1) searching is more important than sorting.
- Index-based access is required.

Instead use:

- HashSet
- LinkedHashSet
- ArrayList

---

# Summary

- TreeSet stores **only unique elements**.
- Elements are automatically arranged in **ascending order**.
- It internally uses a **Red-Black Tree**.
- Duplicate elements are ignored.
- Null values are **not allowed**.
- TreeSet implements `Set`, `SortedSet`, and `NavigableSet`.
- It provides useful navigation methods such as `first()`, `last()`, `higher()`, `lower()`, `ceiling()`, and `floor()`.
- The average time complexity of insertion, deletion, and searching is **O(log n)**.
- TreeSet is suitable for applications that require sorted unique data.

---

# Conclusion

`TreeSet` is one of the most useful collection classes in Java for maintaining **sorted and unique elements**. Unlike `HashSet` and `LinkedHashSet`, it automatically arranges data in ascending order using a **Red-Black Tree**. It also provides powerful navigation methods that make searching and retrieving nearby elements easy.

TreeSet is widely used in applications such as student ranking systems, leaderboards, product catalogs, dictionaries, employee records, railway timetables, and banking systems where sorted data is essential.

By mastering `TreeSet`, developers can efficiently manage ordered collections and build scalable Java applications that require automatic sorting.

---

# Next Topic

```text
09_HashMap.md
```
