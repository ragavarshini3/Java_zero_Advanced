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
