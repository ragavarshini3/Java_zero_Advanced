# Recursion in Java

In previous lessons, we learned how methods call other methods.

Sometimes, a method needs to call **itself** to solve a problem.

This concept is called **Recursion**.

Recursion is a powerful programming technique used to solve problems by breaking them into smaller versions of the same problem.

---

# What is Recursion?

**Recursion** is a process in which a method calls itself repeatedly until a stopping condition (called the **Base Case**) is reached.

Without a base case, recursion continues forever and causes an error.

---

# Real-World Example

Imagine standing between two mirrors.

Each mirror reflects the other mirror repeatedly.

```
Mirror

↓

Reflection

↓

Reflection

↓

Reflection

↓

...
```

The reflections continue until the image disappears.

Recursion works similarly.

A method keeps calling itself until the stopping condition is met.

---

# Why Do We Need Recursion?

Some problems become easier using recursion.

Examples include:

- Factorial Calculation
- Fibonacci Series
- Binary Search
- Tree Traversal
- Folder Navigation
- Maze Solving
- Tower of Hanoi
- File System Search

---

# Components of Recursion

Every recursive method has two parts.

### 1. Base Case

Stops recursion.

### 2. Recursive Call

Calls the same method again.

Without the base case, the program never stops.

---

# Syntax

```java
returnType methodName(parameters)
{
    if(baseCondition)
    {
        return value;
    }

    return methodName(smallerProblem);
}
```

---

# How Recursion Works

```
main()

↓

factorial(5)

↓

factorial(4)

↓

factorial(3)

↓

factorial(2)

↓

factorial(1)

↓

Return Back

↓

Answer
```

---

# Example 1: Simple Recursion

```java
public class RecursionExample {

    static void printNumbers(int n)
    {
        if(n == 0)
        {
            return;
        }

        System.out.println(n);

        printNumbers(n - 1);
    }

    public static void main(String[] args)
    {
        printNumbers(5);
    }

}
```

### Output

```text
5
4
3
2
1
```

---

# Explanation

Execution

```
printNumbers(5)

↓

Print 5

↓

printNumbers(4)

↓

Print 4

↓

printNumbers(3)

↓

Print 3

↓

printNumbers(2)

↓

Print 2

↓

printNumbers(1)

↓

Print 1

↓

printNumbers(0)

↓

Stop
```

---

# Example 2: Factorial

Factorial Formula

```
5!

=

5 × 4 × 3 × 2 × 1

=

120
```

Program

```java
public class Factorial {

    static int factorial(int n)
    {
        if(n == 1)
        {
            return 1;
        }

        return n * factorial(n - 1);
    }

    public static void main(String[] args)
    {

        System.out.println(factorial(5));

    }

}
```

### Output

```text
120
```

---

# Dry Run

```
factorial(5)

↓

5 × factorial(4)

↓

5 × 4 × factorial(3)

↓

5 × 4 × 3 × factorial(2)

↓

5 × 4 × 3 × 2 × factorial(1)

↓

5 × 4 × 3 × 2 × 1

↓

120
```

---

# Example 3: Fibonacci Series

Formula

```
0

1

1

2

3

5

8
```

Program

```java
public class Fibonacci {

    static int fibonacci(int n)
    {
        if(n <= 1)
        {
            return n;
        }

        return fibonacci(n-1) + fibonacci(n-2);
    }

    public static void main(String[] args)
    {

        for(int i=0;i<10;i++)
        {
            System.out.print(fibonacci(i)+" ");
        }

    }

}
```

### Output

```text
0 1 1 2 3 5 8 13 21 34
```

---

# Example 4: Sum of Natural Numbers

```java
public class Sum {

    static int sum(int n)
    {
        if(n == 1)
        {
            return 1;
        }

        return n + sum(n-1);
    }

    public static void main(String[] args)
    {

        System.out.println(sum(10));

    }

}
```

### Output

```text
55
```

---

# Example 5: Power of a Number

```java
public class Power {

    static int power(int base,int exponent)
    {
        if(exponent==0)
        {
            return 1;
        }

        return base * power(base,exponent-1);
    }

    public static void main(String[] args)
    {

        System.out.println(power(2,5));

    }

}
```

### Output

```text
32
```

---

# Real-World Scenario 1: Folder Navigation

Suppose a computer contains folders inside folders.

```
Documents

↓

Projects

↓

Java

↓

Programs

↓

Files
```

A recursive method can visit every folder automatically.

---

# Real-World Scenario 2: Organization Hierarchy

```
CEO

↓

Manager

↓

Team Lead

↓

Developer
```

Each employee may manage more employees.

Recursion is useful for displaying the complete hierarchy.

---

# Real-World Scenario 3: Binary Search Tree

```
          50

        /    \

      30      70

     /  \    /  \

   20   40 60   80
```

Searching every child node naturally uses recursion.

---

# Real-World Scenario 4: File Search

When searching for a file,

```
Computer

↓

Drive

↓

Folder

↓

Sub Folder

↓

Sub Folder

↓

Target File
```

Recursion automatically searches every directory.

---

# Stack Memory in Recursion

Each recursive call is stored in the **Call Stack**.

Example

```
factorial(5)

↓

factorial(4)

↓

factorial(3)

↓

factorial(2)

↓

factorial(1)
```

After reaching the base case,

The stack starts returning one by one.

```
factorial(1)

↑

factorial(2)

↑

factorial(3)

↑

factorial(4)

↑

factorial(5)
```

---

# Recursion vs Loop

| Recursion | Loop |
|-----------|------|
| Method calls itself | Uses for/while |
| Uses Call Stack | Uses Iteration |
| Elegant for tree problems | Faster for simple repetition |
| More memory | Less memory |
| Easier for divide-and-conquer algorithms | Easier for simple counting |

---

# Advantages of Recursion

- Simple code
- Easy to understand
- Solves complex problems
- Ideal for trees and graphs
- Reduces lengthy iterative code
- Widely used in algorithms

---

# Disadvantages of Recursion

- More memory usage
- Slower than loops for simple tasks
- Risk of StackOverflowError
- Difficult to debug for beginners

---

# Common Mistakes

## Missing Base Case

❌ Incorrect

```java
static void demo()
{
    demo();
}
```

Output

```text
StackOverflowError
```

---

## Correct

```java
static void demo(int n)
{
    if(n==0)
    {
        return;
    }

    demo(n-1);
}
```

---

# Real-World Applications

Recursion is used in:

- Binary Search
- Merge Sort
- Quick Sort
- Tree Traversal
- Graph Algorithms
- Artificial Intelligence
- Robotics
- File System Navigation
- Compiler Design
- Game Development

---

# Interview Questions

### What is Recursion?

A method calling itself.

---

### What is the Base Case?

The stopping condition.

---

### What happens if there is no Base Case?

The program throws **StackOverflowError**.

---

### Which data structure supports Recursion?

Call Stack.

---

### Is every recursive program convertible into a loop?

Yes.

---

# Challenge Exercises

### Challenge 1

Print numbers from 1 to N using recursion.

---

### Challenge 2

Find the factorial of a number.

---

### Challenge 3

Calculate the sum of digits of a number.

---

### Challenge 4

Reverse a string using recursion.

---

### Challenge 5

Find the greatest common divisor (GCD) using recursion.

---

### Challenge 6

Check whether a string is a palindrome using recursion.

---

### Challenge 7

Calculate the nth Fibonacci number.

---

### Challenge 8

Find the power of a number using recursion.

---

# Summary

- Recursion is a method calling itself.
- Every recursive method requires a base case.
- Recursive calls solve smaller versions of the same problem.
- The Call Stack stores every recursive call.
- Recursion is commonly used in trees, graphs, searching, sorting, and divide-and-conquer algorithms.

---

# Conclusion

Recursion is one of the most important problem-solving techniques in Java. Although loops are suitable for many repetitive tasks, recursion provides a cleaner and more intuitive solution for hierarchical and divide-and-conquer problems. Mastering recursion prepares you for advanced topics such as data structures, algorithms, tree traversal, graph processing, dynamic programming, and technical coding interviews.
