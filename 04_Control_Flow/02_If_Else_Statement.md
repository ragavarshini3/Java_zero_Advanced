# If Else Statement in Java

In the previous topic, we learned that the **if statement** executes a block of code only when a condition is true.

But what if we want to perform one action when the condition is true and another action when the condition is false?

For such situations, Java provides the **if-else statement**.

---
 
# What is an If Else Statement?

The if-else statement allows a program to choose between two possible actions.

* If the condition is true → execute the if block.
* If the condition is false → execute the else block.

---

# Syntax

```java
if(condition)
{
    // Executes when condition is true
}
else
{
    // Executes when condition is false
}
```

---

# Flow Diagram

```text
        Condition
            ↓
         True ?
        /      \
      Yes      No
       ↓        ↓
   If Block  Else Block
```

---

# Why Do We Need If Else?

Imagine real-world situations:

* A student either passes or fails.
* A person is either eligible or not eligible to vote.
* A login attempt is either successful or unsuccessful.
* A customer either gets a discount or does not.

In such cases, we need two different outcomes.

---

# Example 1: Pass or Fail

A student passes if marks are 40 or above.

```java
public class StudentResult {

    public static void main(String[] args) {

        int marks = 35;

        if(marks >= 40)
        {
            System.out.println("Pass");
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
Fail
```

---

# Explanation

Condition:

```java
marks >= 40
```

Substituting the value:

```text
35 >= 40
```

Result:

```text
false
```

Since the condition is false, the else block executes.

---

# Example 2: Voting Eligibility

A person must be at least 18 years old to vote.

```java
public class VotingEligibility {

    public static void main(String[] args) {

        int age = 16;

        if(age >= 18)
        {
            System.out.println("Eligible to Vote");
        }
        else
        {
            System.out.println("Not Eligible to Vote");
        }
    }
}
```

### Output

```text
Not Eligible to Vote
```

---

# Example 3: ATM Withdrawal

A withdrawal can only happen if sufficient balance is available.

```java
public class ATM {

    public static void main(String[] args) {

        double balance = 5000;
        double withdrawAmount = 7000;

        if(balance >= withdrawAmount)
        {
            System.out.println("Withdrawal Successful");
        }
        else
        {
            System.out.println("Insufficient Balance");
        }
    }
}
```

### Output

```text
Insufficient Balance
```

---

# Example 4: Shopping Discount

Customers spending ₹5000 or more receive a discount.

```java
public class Discount {

    public static void main(String[] args) {

        double purchaseAmount = 3500;

        if(purchaseAmount >= 5000)
        {
            System.out.println("Discount Applied");
        }
        else
        {
            System.out.println("No Discount Available");
        }
    }
}
```

### Output

```text
No Discount Available
```

---

# Example 5: Login System

A simple login verification.

```java
public class LoginSystem {

    public static void main(String[] args) {

        String username = "admin";
        String password = "1234";

        if(username.equals("admin") &&
           password.equals("1234"))
        {
            System.out.println("Login Successful");
        }
        else
        {
            System.out.println("Invalid Credentials");
        }
    }
}
```

### Output

```text
Login Successful
```

---

# Using User Input

Real-world applications accept input from users.

```java
import java.util.Scanner;

public class AgeCheck {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Your Age: ");

        int age = sc.nextInt();

        if(age >= 18)
        {
            System.out.println("Eligible to Vote");
        }
        else
        {
            System.out.println("Not Eligible to Vote");
        }

        sc.close();
    }
}
```

### Sample Output

```text
Enter Your Age: 17
Not Eligible to Vote
```

---

# Real-World Scenario: Online Food Delivery

Free delivery is available only for orders above ₹500.

```java
public class FoodDelivery {

    public static void main(String[] args) {

        double orderAmount = 450;

        if(orderAmount >= 500)
        {
            System.out.println("Free Delivery");
        }
        else
        {
            System.out.println("Delivery Charges Apply");
        }
    }
}
```

### Output

```text
Delivery Charges Apply
```

---

# Real-World Scenario: Movie Ticket Booking

A customer gets a child ticket if age is below 12.

```java
public class MovieTicket {

    public static void main(String[] args) {

        int age = 10;

        if(age < 12)
        {
            System.out.println("Child Ticket");
        }
        else
        {
            System.out.println("Adult Ticket");
        }
    }
}
```

### Output

```text
Child Ticket
```

---

# Nested Conditions with If Else

Conditions can also use logical operators.

```java
int marks = 85;
int attendance = 90;

if(marks >= 40 && attendance >= 75)
{
    System.out.println("Eligible for Exam");
}
else
{
    System.out.println("Not Eligible for Exam");
}
```

### Output

```text
Eligible for Exam
```

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

❌ Incorrect

```java
if(age >= 18)
    System.out.println("Eligible");
else
    System.out.println("Not Eligible");
```

Although valid for a single statement, braces improve readability.

---

✅ Recommended

```java
if(age >= 18)
{
    System.out.println("Eligible");
}
else
{
    System.out.println("Not Eligible");
}
```

---

# Difference Between If and If Else

| If Statement                         | If Else Statement                      |
| ------------------------------------ | -------------------------------------- |
| Executes only when condition is true | Handles both true and false conditions |
| May execute nothing                  | Always executes one block              |
| Used for single decision             | Used for two possible outcomes         |

---

# Challenge Exercises

### Challenge 1

Check whether a number is even or odd.

---

### Challenge 2

Check whether a person is eligible to vote.

Minimum age = 18.

---

### Challenge 3

Check whether a customer receives a discount.

Minimum purchase = ₹5000.

---

### Challenge 4

Create a login verification system.

---

### Challenge 5

Create an ATM withdrawal application.

---

# Summary

* The if-else statement provides two possible execution paths.
* If the condition is true, the if block executes.
* If the condition is false, the else block executes.
* It is widely used in real-world applications such as banking, shopping, login systems, and ticket booking systems.

---

# Conclusion

The if-else statement is one of the most important decision-making structures in Java. It enables programs to handle both positive and negative outcomes, making applications more interactive, intelligent, and practical.
