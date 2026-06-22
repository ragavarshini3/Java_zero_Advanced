# Break and Continue Statements in Java

When working with loops, there are situations where we may want to:

* Stop the loop completely.
* Skip a particular iteration.

Java provides two special control statements:

1. **break**
2. **continue**

These statements help control the flow of loops efficiently.

---

# Why Do We Need Break and Continue?

Imagine:

* An ATM stops processing after the correct PIN is entered.
* A search operation stops when the required item is found.
* A teacher skips absent students while marking attendance.

In such situations, break and continue are useful.

---

# Break Statement

The **break statement** immediately terminates the loop.

Once break executes:

* The loop stops.
* Control moves to the next statement after the loop.

---

# Syntax

```java
break;
```

---

# Flow Diagram

```text
Loop
 ↓
Condition
 ↓
Break?
 ↓
Yes
 ↓
Loop Ends
```

---

# Example 1: Stop at Number 5

```java
public class BreakExample {

    public static void main(String[] args) {

        for(int i = 1; i <= 10; i++)
        {
            if(i == 5)
            {
                break;
            }

            System.out.println(i);
        }
    }
}
```

### Output

```text
1
2
3
4
```

---

# Explanation

When:

```java
i == 5
```

becomes true:

```java
break;
```

executes.

The loop terminates immediately.

---

# Real-World Scenario 1: Product Search

Suppose an online shopping application searches for a product.

```java
public class ProductSearch {

    public static void main(String[] args) {

        int[] products = {101,102,103,104,105};

        int target = 103;

        for(int product : products)
        {
            if(product == target)
            {
                System.out.println("Product Found");
                break;
            }
        }
    }
}
```

### Output

```text
Product Found
```

Once the product is found, searching further is unnecessary.

---

# Real-World Scenario 2: ATM PIN Verification

```java
public class ATM {

    public static void main(String[] args) {

        int attempts = 1;

        while(attempts <= 3)
        {
            System.out.println(
                "Checking PIN..."
            );

            if(attempts == 2)
            {
                System.out.println(
                    "PIN Verified"
                );

                break;
            }

            attempts++;
        }
    }
}
```

### Output

```text
Checking PIN...
Checking PIN...
PIN Verified
```

---

# Continue Statement

The continue statement skips the current iteration and moves to the next iteration.

Unlike break, continue does not terminate the loop.

---

# Syntax

```java
continue;
```

---

# Flow Diagram

```text
Loop
 ↓
Condition
 ↓
Continue?
 ↓
Yes
 ↓
Skip Current Iteration
 ↓
Next Iteration
```

---

# Example 2: Skip Number 5

```java
public class ContinueExample {

    public static void main(String[] args) {

        for(int i = 1; i <= 10; i++)
        {
            if(i == 5)
            {
                continue;
            }

            System.out.println(i);
        }
    }
}
```

### Output

```text
1
2
3
4
6
7
8
9
10
```

Notice that:

```text
5
```

is skipped.

---

# Real-World Scenario 3: Attendance System

Skip absent students.

```java
public class Attendance {

    public static void main(String[] args) {

        for(int student = 1;
            student <= 5;
            student++)
        {
            if(student == 3)
            {
                continue;
            }

            System.out.println(
                "Attendance Marked for Student "
                + student
            );
        }
    }
}
```

### Output

```text
Attendance Marked for Student 1
Attendance Marked for Student 2
Attendance Marked for Student 4
Attendance Marked for Student 5
```

Student 3 was absent.

---

# Real-World Scenario 4: E-Commerce Order Processing

Skip cancelled orders.

```java
public class Orders {

    public static void main(String[] args) {

        for(int order = 1;
            order <= 5;
            order++)
        {
            if(order == 4)
            {
                continue;
            }

            System.out.println(
                "Processing Order " + order
            );
        }
    }
}
```

### Output

```text
Processing Order 1
Processing Order 2
Processing Order 3
Processing Order 5
```

Order 4 was cancelled.

---

# Break vs Continue

| Break                       | Continue                                  |
| --------------------------- | ----------------------------------------- |
| Stops the loop completely   | Skips current iteration                   |
| Loop ends immediately       | Loop continues                            |
| Used when task is completed | Used when specific data should be ignored |

---

# Example Comparison

```java
for(int i = 1; i <= 5; i++)
{
    if(i == 3)
    {
        break;
    }

    System.out.println(i);
}
```

Output:

```text
1
2
```

---

```java
for(int i = 1; i <= 5; i++)
{
    if(i == 3)
    {
        continue;
    }

    System.out.println(i);
}
```

Output:

```text
1
2
4
5
```

---

# Using Break in Nested Loops

```java
public class NestedBreak {

    public static void main(String[] args) {

        for(int i = 1; i <= 3; i++)
        {
            for(int j = 1; j <= 3; j++)
            {
                if(j == 2)
                {
                    break;
                }

                System.out.println(
                    "i = " + i +
                    ", j = " + j
                );
            }
        }
    }
}
```

### Output

```text
i = 1, j = 1
i = 2, j = 1
i = 3, j = 1
```

---

# Common Mistakes

## Confusing Break and Continue

❌ Using break when only one iteration should be skipped.

```java
if(i == 5)
{
    break;
}
```

Loop stops entirely.

---

✅ Correct

```java
if(i == 5)
{
    continue;
}
```

Only skips that iteration.

---

# Real-World Applications

Break and Continue are commonly used in:

* ATM Systems
* Login Verification
* Search Algorithms
* Attendance Systems
* E-Commerce Applications
* Inventory Management
* Ticket Booking Systems

---

# Challenge Exercises

### Challenge 1

Print numbers from 1 to 20 but stop at 15.

---

### Challenge 2

Print numbers from 1 to 20 while skipping multiples of 3.

---

### Challenge 3

Create a product search system using break.

---

### Challenge 4

Create an attendance system using continue.

---

### Challenge 5

Create a login attempt system that stops after successful login.

---

# Summary

* break terminates the loop immediately.
* continue skips the current iteration.
* Both statements improve efficiency and control.
* Frequently used in searching, validation, authentication, and data processing.

---

# Conclusion

Break and Continue are powerful control statements that provide greater flexibility when working with loops. They help developers stop unnecessary processing and skip unwanted data, making programs more efficient and easier to manage.
