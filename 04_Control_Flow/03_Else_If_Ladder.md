# Else If Ladder in Java

In many real-world situations, there are more than two possible outcomes.

For example:

* Student Grade Calculation
* Income Tax Calculation
* Employee Performance Evaluation
* Online Shopping Discount Categories

In such cases, using only `if` or `if-else` is not enough.

Java provides the **else-if ladder** to check multiple conditions one after another.

---

# What is an Else If Ladder?

The else-if ladder allows a program to test multiple conditions.

The conditions are checked from top to bottom.

* If a condition is true, its block executes.
* The remaining conditions are skipped.
* If none of the conditions are true, the else block executes.

---

# Syntax

```java
if(condition1)
{
    // code
}
else if(condition2)
{
    // code
}
else if(condition3)
{
    // code
}
else
{
    // code
}
```

---

# Flow Diagram

```text
Condition 1
    ↓
True ? → Execute Block 1

False
    ↓

Condition 2
    ↓
True ? → Execute Block 2

False
    ↓

Condition 3
    ↓
True ? → Execute Block 3

False
    ↓

Else Block
```

---

# Real-World Scenario: Student Grade System

A school follows:

```text
90 - 100  → Grade A
80 - 89   → Grade B
70 - 79   → Grade C
50 - 69   → Grade D
Below 50  → Fail
```

---

## Example

```java
public class GradeSystem {

    public static void main(String[] args) {

        int marks = 85;

        if(marks >= 90)
        {
            System.out.println("Grade A");
        }
        else if(marks >= 80)
        {
            System.out.println("Grade B");
        }
        else if(marks >= 70)
        {
            System.out.println("Grade C");
        }
        else if(marks >= 50)
        {
            System.out.println("Grade D");
        }
        else
        {
            System.out.println("Fail");
        }
    }
}
```

### Output

```text
Grade B
```

---

# Explanation

Marks = 85

Check:

```java
marks >= 90
```

False

Check:

```java
marks >= 80
```

True

Therefore:

```java
System.out.println("Grade B");
```

executes and the remaining conditions are skipped.

---

# Real-World Scenario: Income Tax Calculation

```text
Income < ₹2,50,000      → No Tax
₹2,50,000 - ₹5,00,000  → 5% Tax
₹5,00,000 - ₹10,00,000 → 20% Tax
Above ₹10,00,000       → 30% Tax
```

---

## Example

```java
public class IncomeTax {

    public static void main(String[] args) {

        double income = 700000;

        if(income < 250000)
        {
            System.out.println("No Tax");
        }
        else if(income <= 500000)
        {
            System.out.println("5% Tax");
        }
        else if(income <= 1000000)
        {
            System.out.println("20% Tax");
        }
        else
        {
            System.out.println("30% Tax");
        }
    }
}
```

### Output

```text
20% Tax
```

---

# Real-World Scenario: Employee Performance Rating

```java
public class EmployeeRating {

    public static void main(String[] args) {

        int score = 92;

        if(score >= 90)
        {
            System.out.println("Outstanding");
        }
        else if(score >= 80)
        {
            System.out.println("Excellent");
        }
        else if(score >= 70)
        {
            System.out.println("Good");
        }
        else if(score >= 60)
        {
            System.out.println("Average");
        }
        else
        {
            System.out.println("Needs Improvement");
        }
    }
}
```

### Output

```text
Outstanding
```

---

# Using User Input

```java
import java.util.Scanner;

public class GradeCalculator {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Marks: ");

        int marks = sc.nextInt();

        if(marks >= 90)
        {
            System.out.println("Grade A");
        }
        else if(marks >= 80)
        {
            System.out.println("Grade B");
        }
        else if(marks >= 70)
        {
            System.out.println("Grade C");
        }
        else if(marks >= 50)
        {
            System.out.println("Grade D");
        }
        else
        {
            System.out.println("Fail");
        }

        sc.close();
    }
}
```

---

# Important Rules

### Rule 1

Conditions are checked from top to bottom.

---

### Rule 2

Only one block executes.

---

### Rule 3

The first true condition wins.

---

# Common Mistake

❌ Incorrect Order

```java
if(marks >= 50)
{
    System.out.println("Pass");
}
else if(marks >= 90)
{
    System.out.println("Grade A");
}
```

Output for 95 marks:

```text
Pass
```

Wrong result.

---

✅ Correct Order

```java
if(marks >= 90)
{
    System.out.println("Grade A");
}
else if(marks >= 50)
{
    System.out.println("Pass");
}
```

---

# Difference Between If Else and Else If Ladder

| If Else          | Else If Ladder      |
| ---------------- | ------------------- |
| Two outcomes     | Multiple outcomes   |
| One condition    | Multiple conditions |
| Simple decisions | Complex decisions   |

---

# Challenge Exercises

### Challenge 1

Create a grade calculator.

---

### Challenge 2

Create an income tax calculator.

---

### Challenge 3

Create a movie ticket pricing system.

```text
Age < 12 → Child Ticket
Age 12-59 → Adult Ticket
Age 60+ → Senior Citizen Ticket
```

---

### Challenge 4

Create a customer discount system.

```text
Purchase > ₹10000 → 20% Discount
Purchase > ₹5000  → 10% Discount
Purchase > ₹2000  → 5% Discount
Otherwise No Discount
```

---

# Summary

* Else-if ladder is used when multiple conditions must be checked.
* Conditions are checked from top to bottom.
* Only the first true condition executes.
* Widely used in grading systems, tax systems, employee evaluations, and e-commerce applications.

---

# Conclusion

The else-if ladder is a powerful decision-making structure that helps Java programs handle multiple possible outcomes efficiently. It is commonly used in real-world software applications where decisions depend on several conditions.
