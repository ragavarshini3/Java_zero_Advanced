# Type Casting in Java

Type Casting is the process of converting one data type into another data type.

In real-world applications, data often comes in different formats. Sometimes we need to convert data from one type to another to perform calculations or store values correctly.

---

# What is Type Casting?

Suppose a student scored **85 marks** and the marks are stored as an integer.

```java
int marks = 85;
```

If we want to calculate the average as a decimal value, we may need to convert the integer into a floating-point number.

This conversion is called **Type Casting**.

---

# Types of Type Casting

Java supports two types of type casting:

1. Widening Casting (Automatic)
2. Narrowing Casting (Manual)

```text
Type Casting
│
├── Widening Casting
│   └── Automatic
│
└── Narrowing Casting
    └── Manual
```

---

# 1. Widening Casting (Automatic)

Converting a smaller data type into a larger data type.

Java performs this conversion automatically because there is no risk of data loss.

### Flow

```text
byte → short → int → long → float → double
```

---

## Example 1: Student Marks

```java
public class WideningExample {
    public static void main(String[] args) {

        int marks = 85;

        double averageMarks = marks;

        System.out.println("Marks: " + marks);
        System.out.println("Average Marks: " + averageMarks);
    }
}
```

### Output

```text
Marks: 85
Average Marks: 85.0
```

### Explanation

The integer value `85` is automatically converted into `85.0`.

No explicit casting is required.

---

## Real-World Scenario

Imagine a school management system.

Student's total marks:

```java
int totalMarks = 450;
```

Percentage calculation:

```java
double percentage = totalMarks;
```

Java automatically converts the integer into a double because percentage values can contain decimals.

---

# 2. Narrowing Casting (Manual)

Converting a larger data type into a smaller data type.

Java requires explicit casting because data may be lost.

### Flow

```text
double → float → long → int → short → byte
```

---

## Example 2: Product Price

```java
public class NarrowingExample {
    public static void main(String[] args) {

        double price = 199.99;

        int roundedPrice = (int) price;

        System.out.println("Original Price: " + price);
        System.out.println("Rounded Price: " + roundedPrice);
    }
}
```

### Output

```text
Original Price: 199.99
Rounded Price: 199
```

---

## Explanation

The decimal part `.99` is removed.

Data loss occurs.

Therefore Java requires manual casting.

```java
(int) price
```

---

# Real-World Scenario: Online Shopping

Suppose an online store calculates a final bill.

```java
double billAmount = 999.75;
```

For some reporting purposes, only the whole number is required.

```java
int reportValue = (int) billAmount;
```

Result:

```text
999
```

The decimal value is removed.

---

# Example 3: Height Measurement

```java
public class HeightExample {

    public static void main(String[] args) {

        float height = 175.5f;

        int roundedHeight = (int) height;

        System.out.println("Height: " + height);
        System.out.println("Rounded Height: " + roundedHeight);
    }
}
```

### Output

```text
Height: 175.5
Rounded Height: 175
```

---

# Example 4: Banking System

A bank stores account balance.

```java
double balance = 25000.75;
```

For generating a quick summary report:

```java
int summaryBalance = (int) balance;
```

Output:

```text
25000
```

---

# Character Type Casting

Characters are internally stored as numbers using Unicode values.

---

## Example

```java
public class CharacterExample {

    public static void main(String[] args) {

        char grade = 'A';

        int asciiValue = grade;

        System.out.println("Grade: " + grade);
        System.out.println("ASCII Value: " + asciiValue);
    }
}
```

### Output

```text
Grade: A
ASCII Value: 65
```

---

# Converting Integer to Character

```java
public class CharConversion {

    public static void main(String[] args) {

        int value = 66;

        char letter = (char) value;

        System.out.println(letter);
    }
}
```

### Output

```text
B
```

---

# Complete Example Program

```java
public class TypeCastingDemo {

    public static void main(String[] args) {

        int marks = 90;

        double average = marks;

        System.out.println("Automatic Casting:");
        System.out.println(average);

        double price = 299.99;

        int roundedPrice = (int) price;

        System.out.println("Manual Casting:");
        System.out.println(roundedPrice);
    }
}
```

### Output

```text
Automatic Casting:
90.0

Manual Casting:
299
```

---

# Common Mistakes

## Forgetting Manual Cast

❌ Incorrect

```java
double salary = 45000.75;
int amount = salary;
```

Compilation Error

---

✅ Correct

```java
double salary = 45000.75;
int amount = (int) salary;
```

---

# When to Use Type Casting

### Use Widening Casting

* Percentage calculations
* Average calculations
* Scientific calculations

### Use Narrowing Casting

* Report generation
* Rounding values
* Converting decimal data into whole numbers

---

# Summary

| Type      | Conversion   | Casting Required |
| --------- | ------------ | ---------------- |
| Widening  | int → double | No               |
| Narrowing | double → int | Yes              |

---

# Conclusion

Type Casting allows Java programs to convert values between different data types. Widening casting happens automatically because it is safe, while narrowing casting requires manual conversion because data loss may occur. Understanding type casting is essential for handling calculations, user input, banking applications, shopping systems, and many other real-world software applications.
