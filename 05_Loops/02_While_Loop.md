# While Loop in Java

In programming, there are situations where we do not know in advance how many times a task should be repeated.

For example:

* An ATM keeps asking for a PIN until the correct PIN is entered.
* A login page keeps asking for credentials until login is successful.
* A game continues running until the player quits.
* A machine keeps processing items until all items are completed.

In such situations, Java provides the **While Loop**.

---

# What is a While Loop?

A While Loop repeatedly executes a block of code as long as a specified condition remains true.

The condition is checked before every iteration.

If the condition becomes false, the loop stops.

---

# Syntax

```java
while(condition)
{
    // code
}
```

---

# How While Loop Works

```text
Condition
    ↓
  True?
    ↓
Execute Code
    ↓
 Back to Condition

False
    ↓
 Loop Ends
```

---

# Components of a While Loop

### 1. Initialization

Variable declaration before the loop.

```java
int i = 1;
```

---

### 2. Condition

Determines whether the loop should continue.

```java
i <= 5
```

---

### 3. Update

Changes the value after every iteration.

```java
i++;
```

---

# Example 1: Print Numbers from 1 to 5

```java
public class WhileLoopExample {

    public static void main(String[] args) {

        int i = 1;

        while(i <= 5)
        {
            System.out.println(i);
            i++;
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
5
```

---

# Step-by-Step Execution

Initial Value:

```java
i = 1
```

Condition:

```java
1 <= 5
```

True

Output:

```text
1
```

Update:

```java
i++;
```

Now:

```java
i = 2
```

The process continues until:

```java
i = 6
```

Condition becomes false.

Loop stops.

---

# Why Use While Loop?

While loops are useful when the number of iterations is unknown.

---

# Real-World Scenario 1: ATM PIN Verification

### Problem

An ATM keeps asking for the PIN until the correct PIN is entered.

---

## Example

```java
public class ATM {

    public static void main(String[] args) {

        int enteredPin = 1234;
        int correctPin = 1234;

        while(enteredPin != correctPin)
        {
            System.out.println("Incorrect PIN");
        }

        System.out.println("Access Granted");
    }
}
```

### Output

```text
Access Granted
```

---

# Real-World Scenario 2: Factory Production Counter

A factory produces products continuously.

```java
public class Factory {

    public static void main(String[] args) {

        int product = 1;

        while(product <= 5)
        {
            System.out.println("Producing Product " + product);
            product++;
        }
    }
}
```

### Output

```text
Producing Product 1
Producing Product 2
Producing Product 3
Producing Product 4
Producing Product 5
```

---

# Real-World Scenario 3: Water Tank Filling

A water tank must be filled until it reaches 100%.

```java
public class WaterTank {

    public static void main(String[] args) {

        int level = 0;

        while(level <= 100)
        {
            System.out.println("Tank Level: " + level + "%");
            level += 20;
        }
    }
}
```

### Output

```text
Tank Level: 0%
Tank Level: 20%
Tank Level: 40%
Tank Level: 60%
Tank Level: 80%
Tank Level: 100%
```

---

# Example 2: Multiplication Table

```java
public class Table {

    public static void main(String[] args) {

        int number = 5;
        int i = 1;

        while(i <= 10)
        {
            System.out.println(number + " x " + i + " = " + (number * i));
            i++;
        }
    }
}
```

### Output

```text
5 x 1 = 5
5 x 2 = 10
...
5 x 10 = 50
```

---

# Example 3: Sum of Numbers

Find the sum from 1 to 5.

```java
public class SumExample {

    public static void main(String[] args) {

        int i = 1;
        int sum = 0;

        while(i <= 5)
        {
            sum = sum + i;
            i++;
        }

        System.out.println("Sum = " + sum);
    }
}
```

### Output

```text
Sum = 15
```

---

# User Input Example

```java
import java.util.Scanner;

public class NumberPrinter {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Limit: ");

        int limit = sc.nextInt();

        int i = 1;

        while(i <= limit)
        {
            System.out.println(i);
            i++;
        }

        sc.close();
    }
}
```

### Sample Output

```text
Enter Limit: 5

1
2
3
4
5
```

---

# Real-World Scenario 4: Login System

A login page keeps requesting credentials until login is successful.

```java
public class LoginSystem {

    public static void main(String[] args) {

        boolean loggedIn = false;
        int attempts = 0;

        while(!loggedIn && attempts < 3)
        {
            System.out.println("Attempt " + (attempts + 1));
            attempts++;

            if(attempts == 3)
            {
                loggedIn = true;
            }
        }

        System.out.println("Login Successful");
    }
}
```

---

# Infinite Loop

An Infinite Loop never ends.

---

## Example

```java
while(true)
{
    System.out.println("Running...");
}
```

Since the condition is always true, the loop never stops.

---

# Common Mistake

### Forgetting Update Statement

❌ Incorrect

```java
int i = 1;

while(i <= 5)
{
    System.out.println(i);
}
```

Output:

```text
1
1
1
1
1
...
```

Infinite Loop

---

✅ Correct

```java
int i = 1;

while(i <= 5)
{
    System.out.println(i);
    i++;
}
```

---

# Difference Between For Loop and While Loop

| For Loop                       | While Loop                          |
| ------------------------------ | ----------------------------------- |
| Used when iterations are known | Used when iterations are unknown    |
| Initialization inside loop     | Initialization usually outside loop |
| Compact syntax                 | Flexible syntax                     |
| Best for counting              | Best for condition-based repetition |

---

# Real-World Applications

While Loops are used in:

* ATM Machines
* Login Systems
* Online Games
* Chat Applications
* Inventory Systems
* Factory Automation
* Sensor Monitoring Systems

---

# Challenge Exercises

### Challenge 1

Print numbers from 1 to 100 using a while loop.

---

### Challenge 2

Print even numbers from 2 to 50.

---

### Challenge 3

Calculate the sum of numbers from 1 to 100.

---

### Challenge 4

Create a password verification system.

---

### Challenge 5

Create a countdown timer from 10 to 1.

---

# Summary

* A While Loop executes as long as the condition remains true.
* The condition is checked before every iteration.
* Suitable when the number of repetitions is unknown.
* Commonly used in login systems, ATM systems, games, and monitoring applications.

---

# Conclusion

The While Loop is a powerful control structure used when the number of iterations is not known beforehand. It allows programs to continue running until a specific condition is met, making it ideal for real-world applications such as authentication systems, automation processes, and continuous monitoring systems.
