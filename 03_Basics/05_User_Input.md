# User Input in Java

Most real-world applications do not work with fixed values. Instead, they accept input from users and process that data.

For example:

* ATM machines ask for PIN numbers.
* Online shopping websites ask for quantity.
* Student management systems ask for marks.
* Banking applications ask for deposit amounts.

To accept input from users, Java provides the **Scanner** class.

---

# Why Do We Need User Input?

Without user input:

```java
int age = 20;
```

The value is fixed.

With user input:

```java
Enter your age: 20
```

The user can provide any value during program execution.

This makes programs dynamic and interactive.

---

# Scanner Class

The Scanner class is used to read input from the keyboard.

Before using Scanner, import it:

```java
import java.util.Scanner;
```

---

# Creating a Scanner Object

```java
Scanner sc = new Scanner(System.in);
```

### Explanation

| Part          | Meaning                |
| ------------- | ---------------------- |
| Scanner       | Class Name             |
| sc            | Object Name            |
| new Scanner() | Creates Scanner Object |
| System.in     | Reads Keyboard Input   |

---

# First User Input Program

## Example: Read a Name

```java
import java.util.Scanner;

public class UserInputExample {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your name: ");

        String name = sc.nextLine();

        System.out.println("Welcome " + name);

        sc.close();
    }
}
```

### Output

```text
Enter your name: John
Welcome John
```

---

# Reading Integer Input

## Real-World Scenario: Student Age

```java
import java.util.Scanner;

public class StudentAge {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your age: ");

        int age = sc.nextInt();

        System.out.println("Your age is " + age);

        sc.close();
    }
}
```

### Output

```text
Enter your age: 20
Your age is 20
```

---

# Reading Double Values

## Real-World Scenario: Bank Deposit

```java
import java.util.Scanner;

public class BankDeposit {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter deposit amount: ");

        double amount = sc.nextDouble();

        System.out.println("Amount Deposited: ₹" + amount);

        sc.close();
    }
}
```

### Output

```text
Enter deposit amount: 5000
Amount Deposited: ₹5000.0
```

---

# Reading Character Input

Scanner does not directly provide a method for reading a single character.

Use:

```java
char grade = sc.next().charAt(0);
```

---

## Example

```java
import java.util.Scanner;

public class GradeInput {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Grade: ");

        char grade = sc.next().charAt(0);

        System.out.println("Grade: " + grade);

        sc.close();
    }
}
```

### Output

```text
Enter Grade: A
Grade: A
```

---

# Reading Boolean Values

```java
import java.util.Scanner;

public class BooleanInput {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Are you a student? (true/false): ");

        boolean isStudent = sc.nextBoolean();

        System.out.println(isStudent);

        sc.close();
    }
}
```

### Output

```text
Are you a student? (true/false): true
true
```

---

# Scanner Methods

| Method        | Purpose          |
| ------------- | ---------------- |
| nextInt()     | Read Integer     |
| nextDouble()  | Read Decimal     |
| nextFloat()   | Read Float       |
| nextLong()    | Read Long        |
| nextBoolean() | Read Boolean     |
| next()        | Read Single Word |
| nextLine()    | Read Full Line   |

---

# Difference Between next() and nextLine()

## next()

Reads only one word.

```java
String name = sc.next();
```

Input:

```text
John Smith
```

Output:

```text
John
```

---

## nextLine()

Reads the entire line.

```java
String name = sc.nextLine();
```

Input:

```text
John Smith
```

Output:

```text
John Smith
```

---

# Real-World Example: Student Information System

```java
import java.util.Scanner;

public class StudentInfo {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Student Name: ");
        String name = sc.nextLine();

        System.out.print("Enter Age: ");
        int age = sc.nextInt();

        System.out.print("Enter Marks: ");
        double marks = sc.nextDouble();

        System.out.println("\n----- Student Details -----");
        System.out.println("Name : " + name);
        System.out.println("Age  : " + age);
        System.out.println("Marks: " + marks);

        sc.close();
    }
}
```

### Sample Output

```text
Enter Student Name: John
Enter Age: 20
Enter Marks: 85.5

----- Student Details -----
Name : John
Age  : 20
Marks: 85.5
```

---

# Real-World Example: Shopping Bill Calculator

```java
import java.util.Scanner;

public class ShoppingBill {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Product Price: ");
        double price = sc.nextDouble();

        System.out.print("Enter Quantity: ");
        int quantity = sc.nextInt();

        double totalBill = price * quantity;

        System.out.println("Total Bill = ₹" + totalBill);

        sc.close();
    }
}
```

### Sample Output

```text
Enter Product Price: 1000
Enter Quantity: 3

Total Bill = ₹3000.0
```

---

# Common Mistakes

## Forgetting Import Statement

❌ Incorrect

```java
Scanner sc = new Scanner(System.in);
```

Compilation Error

---

✅ Correct

```java
import java.util.Scanner;
```

---

## Forgetting to Create Scanner Object

❌ Incorrect

```java
int age = sc.nextInt();
```

---

✅ Correct

```java
Scanner sc = new Scanner(System.in);

int age = sc.nextInt();
```

---

## Forgetting to Close Scanner

```java
sc.close();
```

Always close the scanner after use.

---

# Challenge Exercises

### Challenge 1

Create a program that asks the user:

* Name
* Age

Display both values.

---

### Challenge 2

Create a program that accepts:

* Two numbers

Display:

* Sum
* Difference
* Product
* Quotient

---

### Challenge 3

Create a simple ATM application that accepts:

* Account Holder Name
* Deposit Amount

Display the entered details.

---

# Summary

* User input makes programs interactive.
* Java uses the Scanner class to read keyboard input.
* Scanner provides methods for different data types.
* next() reads a single word.
* nextLine() reads an entire line.
* Always close the Scanner object after use.

---

# Conclusion

User input is an essential concept in Java programming because most real-world applications require data from users. The Scanner class provides a simple and efficient way to accept input and build interactive applications such as banking systems, shopping carts, student management systems, and many other software solutions.
