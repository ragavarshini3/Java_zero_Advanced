# Stack in Java

A **Stack** is a linear data structure that follows the **LIFO (Last In, First Out)** principle.

This means the **last element added to the stack is the first element removed**.

Think of a stack of books.

If you place books one on top of another: 

```text 
Top
-------
Book 5
-------
Book 4 
-------
Book 3
-------
Book 2
-------
Book 1
-------
Bottom
```

The last book placed on the stack (**Book 5**) is removed first.

---

# Real-World Examples

Stacks are used in many real-world applications.

Examples:

- Browser Back Button
- Undo Operation in MS Word
- Redo Operation
- Call Stack in Java
- Expression Evaluation
- Parentheses Matching
- Navigation History
- Game Move History

---

# What is Stack in Java?

A `Stack` is a class in the Java Collections Framework.

It extends the `Vector` class.

```text
Object
   │
Vector
   │
Stack
```

Import statement:

```java
import java.util.Stack;
```

---

# Syntax

```java
Stack<DataType> stackName = new Stack<>();
```

Example:

```java
Stack<String> books = new Stack<>();
```

---

# Basic Stack Program

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> books = new Stack<>();

        books.push("Java");

        books.push("Python");

        books.push("C++");

        System.out.println(books);
    }
}
```

### Output

```text
[Java, Python, C++]
```

---

# LIFO Principle

Suppose we insert:

```text
10
20
30
40
```

Stack becomes:

```text
Top
40
30
20
10
```

Removing elements:

```text
Removed → 40

Removed → 30

Removed → 20

Removed → 10
```

Last inserted element is removed first.

---

# Stack Methods

| Method | Description |
|----------|-------------|
| push() | Add an element |
| pop() | Remove top element |
| peek() | View top element |
| empty() | Check whether stack is empty |
| search() | Search an element |
| size() | Number of elements |

---

# push()

Adds an element to the top.

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> colors = new Stack<>();

        colors.push("Red");

        colors.push("Green");

        colors.push("Blue");

        System.out.println(colors);
    }
}
```

### Output

```text
[Red, Green, Blue]
```

---

# pop()

Removes the top element.

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<Integer> numbers = new Stack<>();

        numbers.push(10);

        numbers.push(20);

        numbers.push(30);

        System.out.println(numbers);

        System.out.println(
                "Removed: " + numbers.pop());

        System.out.println(numbers);
    }
}
```

### Output

```text
[10, 20, 30]
Removed: 30
[10, 20]
```

---

# peek()

Returns the top element without removing it.

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> cities = new Stack<>();

        cities.push("Chennai");

        cities.push("Coimbatore");

        cities.push("Madurai");

        System.out.println(cities.peek());

        System.out.println(cities);
    }
}
```

### Output

```text
Madurai
[Chennai, Coimbatore, Madurai]
```

---

# empty()

Checks whether the stack is empty.

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<Integer> stack = new Stack<>();

        System.out.println(stack.empty());

        stack.push(100);

        System.out.println(stack.empty());
    }
}
```

### Output

```text
true
false
```

---

# search()

Searches an element.

Returns its position from the top.

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> stack = new Stack<>();

        stack.push("Java");

        stack.push("Python");

        stack.push("C++");

        System.out.println(
                stack.search("Python"));
    }
}
```

### Output

```text
2
```

---

# size()

Returns the total number of elements.

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> stack = new Stack<>();

        stack.push("A");

        stack.push("B");

        stack.push("C");

        System.out.println(
                stack.size());
    }
}
```

### Output

```text
3
```

---

# Traversing a Stack

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> stack = new Stack<>();

        stack.push("Java");

        stack.push("Python");

        stack.push("C++");

        for(String language : stack)
        {
            System.out.println(language);
        }
    }
}
```

### Output

```text
Java
Python
C++
```

---

# Real-World Example 1: Browser Back Button

Every visited webpage is stored in a stack.

```text
Visit Google

↓

Visit YouTube

↓

Visit GitHub

↓

Back Button

↓

GitHub removed

↓

Current Page → YouTube
```

Program:

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> browser = new Stack<>();

        browser.push("Google");

        browser.push("YouTube");

        browser.push("GitHub");

        System.out.println(
                "Current Page: " + browser.peek());

        browser.pop();

        System.out.println(
                "After Back: " + browser.peek());
    }
}
```

### Output

```text
Current Page: GitHub
After Back: YouTube
```

---

# Real-World Example 2: Undo Operation

Every edit is pushed into a stack.

When Undo is pressed, the latest action is removed.

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> edits = new Stack<>();

        edits.push("Typed Hello");

        edits.push("Typed Java");

        edits.push("Deleted Word");

        System.out.println(
                "Undo: " + edits.pop());

        System.out.println(
                "Current Edit: " + edits.peek());
    }
}
```

### Output

```text
Undo: Deleted Word
Current Edit: Typed Java
```

---

# Real-World Example 3: Plate Stack

A hotel stores plates one above another.

The last plate placed is used first.

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> plates = new Stack<>();

        plates.push("Plate 1");

        plates.push("Plate 2");

        plates.push("Plate 3");

        System.out.println(
                "Serving: " + plates.pop());

        System.out.println(
                "Remaining Plates: " + plates);
    }
}
```

### Output

```text
Serving: Plate 3
Remaining Plates: [Plate 1, Plate 2]
```

---

# Real-World Example 4: Game Moves

Games store moves in a stack.

When Undo is clicked, the last move is removed.

```java
import java.util.Stack;

public class Main
{
    public static void main(String[] args)
    {
        Stack<String> moves = new Stack<>();

        moves.push("Move 1");

        moves.push("Move 2");

        moves.push("Move 3");

        System.out.println(
                "Undo Move: " + moves.pop());

        System.out.println(
                moves);
    }
}
```

### Output

```text
Undo Move: Move 3
[Move 1, Move 2]
```

---

# Advantages of Stack

- Easy insertion and deletion
- Follows LIFO
- Useful for Undo/Redo
- Used in recursion
- Used in browser history
- Used in expression evaluation
- Easy implementation

---

# Limitations

- Only top element can be accessed directly
- No random access
- Not suitable when searching frequently
- Follows only LIFO order

---

# Stack vs Queue

| Stack | Queue |
|---------|---------|
| LIFO | FIFO |
| push() | offer()/add() |
| pop() | poll()/remove() |
| peek() | peek() |
| Last inserted removed first | First inserted removed first |

---

# Common Mistakes

### Pop from Empty Stack

```java
Stack<Integer> stack = new Stack<>();

stack.pop();
```

Throws:

```text
EmptyStackException
```

Always check:

```java
if(!stack.empty())
{
    stack.pop();
}
```

---

### Peek from Empty Stack

```java
stack.peek();
```

Throws:

```text
EmptyStackException
```

---

# Interview Questions

### What is Stack?

A linear data structure that follows LIFO.

---

### Which class does Stack extend?

Vector.

---

### What does push() do?

Adds an element.

---

### What does pop() do?

Removes the top element.

---

### Difference between pop() and peek()?

| pop() | peek() |
|--------|---------|
| Removes element | Doesn't remove |
| Returns top | Returns top |

---

### Which real-world applications use Stack?

- Browser History
- Undo/Redo
- Function Calls
- Expression Evaluation
- Parentheses Matching

---

# Practice Problems

### Basic Problems

1. Push five integers and display them.
2. Pop two elements.
3. Display the top element.
4. Find stack size.
5. Search for an element.

---

### Advanced Problems

1. Reverse a string using Stack.
2. Check balanced parentheses.
3. Convert decimal to binary using Stack.
4. Evaluate postfix expression.
5. Implement browser history using Stack.

---

# Summary

- Stack follows **LIFO**.
- Stack extends `Vector`.
- `push()` adds an element.
- `pop()` removes the top element.
- `peek()` views the top element.
- `empty()` checks whether the stack is empty.
- Used in browser history, undo systems, recursion, and expression evaluation.

---

# Conclusion

`Stack` is one of the most useful data structures in Java for solving problems that require **Last In, First Out (LIFO)** behavior. It is commonly used in browser navigation, undo/redo functionality, recursion, expression evaluation, and many algorithmic problems.

The next topic is:

```text
06_HashSet.md
```
