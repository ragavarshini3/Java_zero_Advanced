# Operators in Java

Operators are special symbols used to perform operations on variables and values.

Just like we use mathematical symbols such as `+`, `-`, `*`, and `/` in everyday calculations, Java uses operators to perform calculations, comparisons, and logical decisions.

---

# Why Do We Need Operators?

Imagine you are building:

* A Banking Application
* An E-Commerce Website
* A Student Management System
* A Payroll System

In all these applications, you need to:

* Add values
* Compare values
* Check conditions
* Make decisions

Operators help us perform these tasks efficiently.

---

# What are Operands?

An operand is the value or variable on which an operator performs an operation.

### Example

```java
int result = 10 + 20;
```

Here:

```text
10  → Operand
20  → Operand
+   → Operator
```

The operator `+` performs addition on the operands `10` and `20`.

---

## Real-World Example

Suppose a customer buys:

* Laptop = ₹50,000
* Mouse = ₹1,000

```java
int laptopPrice = 50000;
int mousePrice = 1000;

int totalBill = laptopPrice + mousePrice;
```

Here:

```text
laptopPrice → Operand
mousePrice  → Operand
+           → Operator
```

The operator adds the two operands to calculate the total bill.

---

## Types of Operands

### Unary Operand (One Operand)

```java
int likes = 100;

likes++;
```

Operator:

```text
++
```

Operand:

```text
likes
```

---

### Binary Operands (Two Operands)

```java
int sum = 10 + 20;
```

Operands:

```text
10 and 20
```

Operator:

```text
+
```

---

### Ternary Operands (Three Operands)

```java
int age = 20;

String result =
(age >= 18) ? "Eligible" : "Not Eligible";
```

Operands:

```text
age >= 18
"Eligible"
"Not Eligible"
```

Operator:

```text
? :
```

---

# Types of Operators in Java

```text
Operators
│
├── Arithmetic Operators
├── Assignment Operators
├── Relational Operators
├── Logical Operators
├── Unary Operators
├── Increment & Decrement Operators
├── Ternary Operator
└── Bitwise Operators
```

---

# 1. Arithmetic Operators

Arithmetic operators are used to perform mathematical calculations.

| Operator | Meaning        |
| -------- | -------------- |
| +        | Addition       |
| -        | Subtraction    |
| *        | Multiplication |
| /        | Division       |
| %        | Modulus        |

---

## Real-World Scenario: Shopping Cart

A customer purchases:

* Laptop = ₹50,000
* Mouse = ₹1,000

```java
public class ShoppingCart {

    public static void main(String[] args) {

        int laptopPrice = 50000;
        int mousePrice = 1000;

        int totalBill = laptopPrice + mousePrice;

        System.out.println("Total Bill = ₹" + totalBill);
    }
}
```

### Output

```text
Total Bill = ₹51000
```

---

## Example: Profit Calculation

```java
int sellingPrice = 1500;
int costPrice = 1200;

int profit = sellingPrice - costPrice;

System.out.println(profit);
```

### Output

```text
300
```

---

## Example: Modulus Operator

Check whether a number is even or odd.

```java
int number = 10;

System.out.println(number % 2);
```

### Output

```text
0
```

If the remainder is 0, the number is even.

---

## Challenge

Create a program to calculate:

* Total Marks
* Average Marks

for 5 subjects.

---

# 2. Assignment Operators

Assignment operators assign values to variables.

---

## Basic Assignment

```java
int age = 20;
```

---

## Compound Assignment Operators

| Operator | Example |
| -------- | ------- |
| +=       | x += 5  |
| -=       | x -= 5  |
| *=       | x *= 5  |
| /=       | x /= 5  |
| %=       | x %= 5  |

---

## Real-World Scenario: Bank Deposit

```java
public class BankAccount {

    public static void main(String[] args) {

        int balance = 10000;

        balance += 5000;

        System.out.println(balance);
    }
}
```

### Output

```text
15000
```

The customer deposited ₹5000.

---

## Challenge

Create a salary system where:

* Initial Salary = ₹30,000
* Bonus = ₹5,000

Update salary using assignment operators.

---

# 3. Relational Operators

Relational operators compare two values.

The result is always:

```text
true
or
false
```

| Operator | Meaning                  |
| -------- | ------------------------ |
| ==       | Equal To                 |
| !=       | Not Equal To             |
| >        | Greater Than             |
| <        | Less Than                |
| >=       | Greater Than or Equal To |
| <=       | Less Than or Equal To    |

---

## Real-World Scenario: Voting Eligibility

```java
int age = 20;

System.out.println(age >= 18);
```

### Output

```text
true
```

The person is eligible to vote.

---

## Real-World Scenario: Exam Result

```java
int marks = 35;

System.out.println(marks >= 40);
```

### Output

```text
false
```

The student failed.

---

## Challenge

Create a program that checks whether a student passed or failed.

Passing Marks = 40.

---

# 4. Logical Operators

Logical operators combine multiple conditions.

| Operator | Meaning |
| -------- | ------- |
| &&       | AND     |
| ||       | OR      |
| !        | NOT     |

---

## Real-World Scenario: College Admission

Conditions:

* Marks > 80
* Age >= 17

```java
int marks = 85;
int age = 18;

System.out.println(marks > 80 && age >= 17);
```

### Output

```text
true
```

Student gets admission.

---

## Real-World Scenario: Login System

```java
String username = "admin";
String password = "1234";

System.out.println(
username.equals("admin")
&& password.equals("1234")
);
```

### Output

```text
true
```

Login successful.

---

## Challenge

Create a login system using logical operators.

---

# 5. Unary Operators

Unary operators work on a single operand.

---

## Positive Operator

```java
int x = +10;
```

---

## Negative Operator

```java
int x = -10;
```

---

## NOT Operator

```java
boolean isLoggedIn = true;

System.out.println(!isLoggedIn);
```

### Output

```text
false
```

---

# 6. Increment and Decrement Operators

Used to increase or decrease a value by 1.

---

## Increment (++)

```java
int count = 10;

count++;

System.out.println(count);
```

### Output

```text
11
```

---

## Decrement (--)

```java
int count = 10;

count--;

System.out.println(count);
```

### Output

```text
9
```

---

## Real-World Scenario: Social Media Likes

```java
int likes = 100;

likes++;

System.out.println(likes);
```

### Output

```text
101
```

Every new like increases the count.

---

## Challenge

Create a website visitor counter.

---

# 7. Ternary Operator

The ternary operator is a short form of an if-else statement.

---

## Syntax

```java
condition ? value1 : value2;
```

---

## Real-World Scenario: Pass or Fail

```java
int marks = 75;

String result =
(marks >= 40)
? "Pass"
: "Fail";

System.out.println(result);
```

### Output

```text
Pass
```

---

## Real-World Scenario: Voting Eligibility

```java
int age = 16;

String result =
(age >= 18)
? "Eligible"
: "Not Eligible";

System.out.println(result);
```

### Output

```text
Not Eligible
```

---

## Challenge

Create a program that determines whether a customer gets a discount.

---

# 8. Bitwise Operators

Bitwise operators work at the binary level.

| Operator | Meaning     |
| -------- | ----------- |
| &        | Bitwise AND |
| |        | Bitwise OR  |
| ^        | XOR         |
| ~        | Complement  |

---

## Example

```java
int a = 5;
int b = 3;

System.out.println(a & b);
```

### Output

```text
1
```

---

## Where Are Bitwise Operators Used?

* Embedded Systems
* IoT Devices
* Networking
* Operating Systems
* Device Drivers

---

# Mini Project Challenge

## Online Shopping System

Requirements:

1. Add product prices.
2. Apply discounts.
3. Check free-delivery eligibility.
4. Generate final bill.

Use:

* Arithmetic Operators
* Assignment Operators
* Relational Operators
* Logical Operators

---

# Summary

| Operator Type       | Purpose                     |
| ------------------- | --------------------------- |
| Arithmetic          | Mathematical calculations   |
| Assignment          | Assign values               |
| Relational          | Compare values              |
| Logical             | Combine conditions          |
| Unary               | Single operand operations   |
| Increment/Decrement | Increase or decrease values |
| Ternary             | Short form of if-else       |
| Bitwise             | Binary operations           |

---

# Conclusion

Operators are fundamental building blocks of Java programming. Every calculation, comparison, and decision-making process in Java relies on operators. Understanding operators and operands is essential before learning conditional statements, loops, methods, and object-oriented programming.
