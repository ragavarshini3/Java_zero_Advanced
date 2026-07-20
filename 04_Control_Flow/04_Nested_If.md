# Nested If Statement in Java
 
In real-world applications, a single condition is often not enough to make a decision.

For example:

* An ATM first checks whether the PIN is correct, then checks whether sufficient balance is available.
* A college first checks marks, then checks attendance. 
* A company first checks qualifications, then checks experience.
 
In such situations, we use **Nested If Statements**. 

---
# What is a Nested If Statement?

A Nested If Statement means placing one `if` statement inside another `if` statement.

The inner condition is checked only if the outer condition is true.

---

# Syntax

```java
if(condition1)
{
    if(condition2)
    {
        // code
    }
}
```

---

# Flow Diagram

```text
Condition 1
      ↓
   True?
      ↓
 Condition 2
      ↓
   True?
      ↓
 Execute Code
```

If Condition 1 is false, Condition 2 is never checked.

---

# Why Do We Need Nested If?

Imagine an ATM system.

The ATM must verify:

1. Is the PIN correct?
2. Does the account have sufficient balance?

Only after both conditions are true can money be withdrawn.

This is a perfect example of a Nested If Statement.

---

# Real-World Scenario 1: ATM Withdrawal System

### Problem

A customer wants to withdraw money.

Requirements:

* PIN must be correct.
* Balance must be sufficient.

---

## Example

```java
public class ATM {

    public static void main(String[] args) {

        int enteredPin = 1234;
        int actualPin = 1234;

        double balance = 10000;
        double withdrawAmount = 5000;

        if(enteredPin == actualPin)
        {
            if(balance >= withdrawAmount)
            {
                System.out.println("Withdrawal Successful");
            }
        }
    }
}
```

### Output

```text
Withdrawal Successful
```

---

## Explanation

Step 1:

```java
enteredPin == actualPin
```

Result:

```text
true
```

Step 2:

```java
balance >= withdrawAmount
```

Result:

```text
true
```

Both conditions are true.

Therefore:

```text
Withdrawal Successful
```

---

# Real-World Scenario 2: College Admission

### Problem

A student can get admission only if:

* Marks ≥ 75
* Attendance ≥ 80%

---

## Example

```java
public class CollegeAdmission {

    public static void main(String[] args) {

        int marks = 85;
        int attendance = 90;

        if(marks >= 75)
        {
            if(attendance >= 80)
            {
                System.out.println("Admission Granted");
            }
        }
    }
}
```

### Output

```text
Admission Granted
```

---

# Real-World Scenario 3: Employee Promotion

### Problem

An employee gets promoted only if:

* Experience ≥ 5 years
* Performance Score ≥ 90

---

## Example

```java
public class Promotion {

    public static void main(String[] args) {

        int experience = 6;
        int performance = 92;

        if(experience >= 5)
        {
            if(performance >= 90)
            {
                System.out.println("Promotion Approved");
            }
        }
    }
}
```

### Output

```text
Promotion Approved
```

---

# Real-World Scenario 4: Online Exam Eligibility

### Problem

A student can attend the final exam only if:

* Attendance ≥ 75%
* Internal Marks ≥ 40

---

## Example

```java
public class ExamEligibility {

    public static void main(String[] args) {

        int attendance = 80;
        int internalMarks = 45;

        if(attendance >= 75)
        {
            if(internalMarks >= 40)
            {
                System.out.println("Eligible for Final Exam");
            }
        }
    }
}
```

### Output

```text
Eligible for Final Exam
```

---

# Real-World Scenario 5: Online Shopping Premium Offer

### Problem

A customer receives a premium discount if:

* Purchase Amount ≥ ₹10,000
* Customer is a Premium Member

---

## Example

```java
public class ShoppingOffer {

    public static void main(String[] args) {

        double purchaseAmount = 15000;
        boolean premiumMember = true;

        if(purchaseAmount >= 10000)
        {
            if(premiumMember)
            {
                System.out.println("Premium Discount Applied");
            }
        }
    }
}
```

### Output

```text
Premium Discount Applied
```

---

# Nested If with User Input

```java
import java.util.Scanner;

public class VotingSystem {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Age: ");
        int age = sc.nextInt();

        System.out.print("Enter Citizenship Status (1 for Citizen): ");
        int citizen = sc.nextInt();

        if(age >= 18)
        {
            if(citizen == 1)
            {
                System.out.println("Eligible to Vote");
            }
        }

        sc.close();
    }
}
```

### Sample Output

```text
Enter Age: 21
Enter Citizenship Status (1 for Citizen): 1

Eligible to Vote
```

---

# Nested If with Else

```java
public class LoginSystem {

    public static void main(String[] args) {

        String username = "admin";
        String password = "1234";

        if(username.equals("admin"))
        {
            if(password.equals("1234"))
            {
                System.out.println("Login Successful");
            }
            else
            {
                System.out.println("Incorrect Password");
            }
        }
        else
        {
            System.out.println("User Not Found");
        }
    }
}
```

### Output

```text
Login Successful
```

---

# Difference Between If and Nested If

| If Statement           | Nested If Statement                  |
| ---------------------- | ------------------------------------ |
| Checks one condition   | Checks multiple dependent conditions |
| Simple decision making | Complex decision making              |
| Easier structure       | Multi-level structure                |

---

# Common Mistakes

## Mistake 1: Incorrect Braces

❌ Incorrect

```java
if(age >= 18)
    if(citizen == 1)
        System.out.println("Eligible");
```

Hard to read and maintain.

---

✅ Better

```java
if(age >= 18)
{
    if(citizen == 1)
    {
        System.out.println("Eligible");
    }
}
```

---

## Mistake 2: Deep Nesting

Avoid too many levels.

❌

```java
if(a)
{
    if(b)
    {
        if(c)
        {
            if(d)
            {
                // code
            }
        }
    }
}
```

This becomes difficult to understand.

---

# Real-World Applications

Nested If Statements are commonly used in:

* ATM Machines
* Banking Systems
* Login Authentication
* College Admission Systems
* Employee Promotion Systems
* Online Shopping Platforms
* Hospital Management Systems
* Loan Approval Systems

---

# Challenge Exercises

### Challenge 1

Create an ATM system.

Requirements:

* Verify PIN
* Verify Balance
* Allow Withdrawal

---

### Challenge 2

Create a College Admission System.

Requirements:

* Marks ≥ 75
* Attendance ≥ 80

---

### Challenge 3

Create a Loan Approval System.

Requirements:

* Salary ≥ ₹30,000
* Credit Score ≥ 700

---

### Challenge 4

Create a Login Authentication System.

Requirements:

* Verify Username
* Verify Password

---

# Summary

* Nested If means placing an if statement inside another if statement.
* The inner condition executes only if the outer condition is true.
* Useful when multiple dependent conditions must be checked.
* Widely used in banking, authentication, admissions, and approval systems.

---

# Conclusion

Nested If Statements are powerful decision-making structures used when multiple conditions depend on one another. They help developers build secure and intelligent applications such as ATM systems, login portals, admission systems, and banking software.
