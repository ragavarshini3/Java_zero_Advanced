# If Statement in Java

In real-world applications, decisions are made based on conditions.

For example:

* If a student scores above 40, they pass. 
* If a person is above 18, they can vote.
* If a customer spends more than ₹5000, they get a discount.

Java uses the **if statement** to make decisions based on conditions.

---

# What is an If Statement?

An if statement executes a block of code only when a specified condition is true.

---

# Syntax

```java
if(condition)
{
    // code to execute
}
```

---

# Flow Diagram

```text
Condition
    ↓
  true
    ↓
Execute Code

  false
    ↓
Skip Code
```

---

# Example 1: Voting Eligibility

```java
public class VotingEligibility {

    public static void main(String[] args) {

        int age = 20;

        if(age >= 18)
        {
            System.out.println("Eligible to Vote");
        }
    }
}
```

### Output

```text
Eligible to Vote
```

---

# Explanation

Condition:

```java
age >= 18
```

Result:

```text
20 >= 18
```

Condition is true.

Therefore:

```java
System.out.println("Eligible to Vote");
```

gets executed.

---

# Example 2: Student Pass Check

```java
public class StudentResult {

    public static void main(String[] args) {

        int marks = 75;

        if(marks >= 40)
        {
            System.out.println("Pass");
        }
    }
}
```

### Output

```text
Pass
```

---

# Real-World Scenario: ATM Withdrawal

A customer wants to withdraw money.

Condition:

* Balance should be greater than withdrawal amount.

```java
public class ATM {

    public static void main(String[] args) {

        double balance = 10000;
        double withdraw = 5000;

        if(balance >= withdraw)
        {
            System.out.println("Withdrawal Successful");
        }
    }
}
```

### Output

```text
Withdrawal Successful
```

---

# Example 3: Discount Eligibility

```java
public class Discount {

    public static void main(String[] args) {

        double purchaseAmount = 6000;

        if(purchaseAmount >= 5000)
        {
            System.out.println("Discount Applied");
        }
    }
}
```

### Output

```text
Discount Applied
```

---

# Using User Input with If Statement

```java
import java.util.Scanner;

public class AgeCheck {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Age: ");

        int age = sc.nextInt();

        if(age >= 18)
        {
            System.out.println("Eligible to Vote");
        }

        sc.close();
    }
}
```

### Sample Output

```text
Enter Age: 21
Eligible to Vote
```

---

# Important Points

* The condition must return true or false.
* If the condition is true, the block executes.
* If the condition is false, the block is skipped.
* Curly braces `{}` define the block of code.

---

# Common Mistakes

## Using Assignment Instead of Comparison

❌ Incorrect

```java
if(age = 18)
```

---

✅ Correct

```java
if(age == 18)
```

---

## Missing Curly Braces

❌

```java
if(age >= 18)
System.out.println("Eligible");
System.out.println("Welcome");
```

Only the first statement belongs to if.

---

✅

```java
if(age >= 18)
{
    System.out.println("Eligible");
    System.out.println("Welcome");
}
```

---

# Challenge Exercises

### Challenge 1

Check whether a number is positive.

### Challenge 2

Check whether a student passed.

Passing marks = 40.

### Challenge 3

Check whether a customer is eligible for a discount.

Minimum purchase = ₹5000.

### Challenge 4

Check whether a person is eligible to vote.

Minimum age = 18.

---

# Summary

* The if statement is used for decision making.
* Code executes only when the condition is true.
* It is one of the most important control flow statements in Java.
* Commonly used in banking, shopping, login systems, and student applications.

---

# Conclusion

The if statement is the foundation of decision-making in Java. It allows programs to perform actions based on specific conditions and is widely used in almost every real-world application.
