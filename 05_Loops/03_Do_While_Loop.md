# Do While Loop in Java

In the previous topic, we learned that a While Loop checks the condition before executing the loop body.

But sometimes we want the loop body to execute at least once, even if the condition is false.

For such situations, Java provides the **Do While Loop**.

---

# What is a Do While Loop?

A Do While Loop executes the code block first and then checks the condition.

This means the loop body is guaranteed to execute at least once.

---

# Syntax

```java
do
{
    // code
}
while(condition);
```

---

# How Do While Loop Works

```text
Execute Code
      ↓
 Check Condition
      ↓
   True?
      ↓
 Execute Again

 False
      ↓
  Loop Ends
```

---

# Difference Between While and Do While

### While Loop

```java
while(condition)
{
    // code
}
```

Condition checked first.

---

### Do While Loop

```java
do
{
    // code
}
while(condition);
```

Code executes first.

---

# Example 1: Print Numbers from 1 to 5

```java
public class DoWhileExample {

    public static void main(String[] args) {

        int i = 1;

        do
        {
            System.out.println(i);
            i++;
        }
        while(i <= 5);
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

Execute:

```java
System.out.println(i);
```

Output:

```text
1
```

Update:

```java
i++
```

Condition:

```java
i <= 5
```

True

Loop continues.

---

# Real-World Scenario 1: ATM Menu

An ATM should display the menu at least once.

```java
public class ATMMenu {

    public static void main(String[] args) {

        int choice = 1;

        do
        {
            System.out.println("ATM Menu");
            System.out.println("1. Balance");
            System.out.println("2. Withdraw");
            System.out.println("3. Exit");

            choice = 3;

        }
        while(choice != 3);

        System.out.println("Thank You");
    }
}
```

### Output

```text
ATM Menu
1. Balance
2. Withdraw
3. Exit

Thank You
```

---

# Real-World Scenario 2: Online Food Ordering

The menu should appear at least once.

```java
public class FoodOrder {

    public static void main(String[] args) {

        int orderStatus = 1;

        do
        {
            System.out.println("Displaying Food Menu");
            orderStatus++;
        }
        while(orderStatus <= 3);
    }
}
```

### Output

```text
Displaying Food Menu
Displaying Food Menu
Displaying Food Menu
```

---

# Example 2: Multiplication Table

```java
public class Table {

    public static void main(String[] args) {

        int number = 5;
        int i = 1;

        do
        {
            System.out.println(number + " x " + i +
                    " = " + (number * i));

            i++;

        }
        while(i <= 10);
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

# Example 3: Countdown Timer

```java
public class Countdown {

    public static void main(String[] args) {

        int count = 5;

        do
        {
            System.out.println(count);
            count--;
        }
        while(count >= 1);

        System.out.println("Launch!");
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
Launch!
```

---

# Special Property of Do While Loop

The loop body executes at least once.

---

## Example

```java
public class Test {

    public static void main(String[] args) {

        int i = 10;

        do
        {
            System.out.println("Executed Once");
        }
        while(i < 5);
    }
}
```

### Output

```text
Executed Once
```

---

# Comparison with While Loop

### While Loop

```java
int i = 10;

while(i < 5)
{
    System.out.println("Hello");
}
```

Output:

```text
No Output
```

---

### Do While Loop

```java
int i = 10;

do
{
    System.out.println("Hello");
}
while(i < 5);
```

Output:

```text
Hello
```

---

# User Input Example

```java
import java.util.Scanner;

public class NumberPrinter {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int number;

        do
        {
            System.out.print("Enter a number: ");
            number = sc.nextInt();

        }
        while(number < 0);

        System.out.println("Valid Number Entered");

        sc.close();
    }
}
```

### Sample Output

```text
Enter a number: -5
Enter a number: -2
Enter a number: 10

Valid Number Entered
```

---

# Real-World Scenario 3: Login System

Keep asking until login succeeds.

```java
public class Login {

    public static void main(String[] args) {

        int attempts = 0;

        do
        {
            System.out.println("Login Attempt");

            attempts++;

        }
        while(attempts < 3);

        System.out.println("Login Success");
    }
}
```

---

# Common Mistakes

## Missing Semicolon

❌ Incorrect

```java
do
{
    System.out.println("Hello");
}
while(i < 5)
```

---

✅ Correct

```java
do
{
    System.out.println("Hello");
}
while(i < 5);
```

Notice the semicolon after while.

---

# Real-World Applications

Do While Loops are commonly used in:

* ATM Menus
* Login Systems
* Game Menus
* Food Ordering Systems
* Online Surveys
* Menu-Driven Programs

---

# Challenge Exercises

### Challenge 1

Print numbers from 1 to 20 using do while.

---

### Challenge 2

Create a countdown timer.

---

### Challenge 3

Create a menu-driven ATM system.

---

### Challenge 4

Keep asking the user to enter a positive number.

---

### Challenge 5

Create a login attempt system with 3 attempts.

---

# Summary

* Do While Loop executes the code first.
* Condition is checked after execution.
* The loop body runs at least once.
* Ideal for menu-driven applications.

---

# Conclusion

The Do While Loop is useful when a task must execute at least once before checking a condition. It is widely used in ATM systems, login pages, games, and menu-driven applications where user interaction is required before validation.
