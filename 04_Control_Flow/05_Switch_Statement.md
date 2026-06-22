# Switch Statement in Java

In programming, we often need to choose one option from many possible options.

For example:

* ATM Menu Selection
* Restaurant Menu Ordering
* Calculator Operations
* Day of the Week Display
* Traffic Signal Systems

Using multiple if-else statements for such situations can make the code lengthy and difficult to read.

Java provides the **Switch Statement** to handle multiple choices efficiently.

---

# What is a Switch Statement?

A Switch Statement is a decision-making statement that allows a program to execute one block of code from multiple available options.

Instead of checking multiple conditions using if-else-if, switch directly matches a value with available cases.

---

# Syntax

```java
switch(expression)
{
    case value1:
        // code
        break;

    case value2:
        // code
        break;

    case value3:
        // code
        break;

    default:
        // code
}
```

---

# How Switch Works

1. Evaluate the expression.
2. Compare the value with each case.
3. Execute the matching case.
4. Stop execution when break is encountered.
5. If no match is found, execute the default block.

---

# Flow Diagram

```text
Expression
     ↓
 Match Case?
     ↓
   Yes
     ↓
 Execute Case
     ↓
    Break

     OR

 No Match
     ↓
 Execute Default
```

---

# Real-World Scenario 1: ATM Menu

### Problem

ATM provides options:

```text
1 → Check Balance
2 → Deposit Money
3 → Withdraw Money
4 → Exit
```

---

## Example

```java
public class ATMMenu {

    public static void main(String[] args) {

        int choice = 2;

        switch(choice)
        {
            case 1:
                System.out.println("Check Balance");
                break;

            case 2:
                System.out.println("Deposit Money");
                break;

            case 3:
                System.out.println("Withdraw Money");
                break;

            case 4:
                System.out.println("Exit");
                break;

            default:
                System.out.println("Invalid Choice");
        }
    }
}
```

### Output

```text
Deposit Money
```

---

# Real-World Scenario 2: Day of the Week

### Problem

Display day name based on number.

```text
1 → Monday
2 → Tuesday
3 → Wednesday
...
```

---

## Example

```java
public class WeekDay {

    public static void main(String[] args) {

        int day = 3;

        switch(day)
        {
            case 1:
                System.out.println("Monday");
                break;

            case 2:
                System.out.println("Tuesday");
                break;

            case 3:
                System.out.println("Wednesday");
                break;

            case 4:
                System.out.println("Thursday");
                break;

            case 5:
                System.out.println("Friday");
                break;

            case 6:
                System.out.println("Saturday");
                break;

            case 7:
                System.out.println("Sunday");
                break;

            default:
                System.out.println("Invalid Day");
        }
    }
}
```

### Output

```text
Wednesday
```

---

# Real-World Scenario 3: Restaurant Menu

### Problem

A customer selects a menu item.

```text
1 → Pizza
2 → Burger
3 → Pasta
4 → Sandwich
```

---

## Example

```java
public class Restaurant {

    public static void main(String[] args) {

        int item = 1;

        switch(item)
        {
            case 1:
                System.out.println("Pizza Ordered");
                break;

            case 2:
                System.out.println("Burger Ordered");
                break;

            case 3:
                System.out.println("Pasta Ordered");
                break;

            case 4:
                System.out.println("Sandwich Ordered");
                break;

            default:
                System.out.println("Item Not Available");
        }
    }
}
```

### Output

```text
Pizza Ordered
```

---

# Real-World Scenario 4: Calculator

### Problem

Perform operations based on user choice.

```java
public class Calculator {

    public static void main(String[] args) {

        int a = 10;
        int b = 5;

        char operation = '+';

        switch(operation)
        {
            case '+':
                System.out.println(a + b);
                break;

            case '-':
                System.out.println(a - b);
                break;

            case '*':
                System.out.println(a * b);
                break;

            case '/':
                System.out.println(a / b);
                break;

            default:
                System.out.println("Invalid Operation");
        }
    }
}
```

### Output

```text
15
```

---

# Importance of Break Statement

The break statement stops execution after a case is completed.

Without break, Java executes the next cases as well.

---

## Example Without Break

```java
int day = 1;

switch(day)
{
    case 1:
        System.out.println("Monday");

    case 2:
        System.out.println("Tuesday");

    case 3:
        System.out.println("Wednesday");
}
```

### Output

```text
Monday
Tuesday
Wednesday
```

This is called **Fall Through**.

---

# Default Case

The default block executes when no case matches.

```java
int month = 15;

switch(month)
{
    case 1:
        System.out.println("January");
        break;

    default:
        System.out.println("Invalid Month");
}
```

### Output

```text
Invalid Month
```

---

# Using Switch with Strings

Java allows String values inside switch.

```java
public class LoginRole {

    public static void main(String[] args) {

        String role = "Admin";

        switch(role)
        {
            case "Admin":
                System.out.println("Full Access");
                break;

            case "User":
                System.out.println("Limited Access");
                break;

            default:
                System.out.println("Guest Access");
        }
    }
}
```

### Output

```text
Full Access
```

---

# Switch vs If Else

| Switch                  | If Else                          |
| ----------------------- | -------------------------------- |
| Multiple fixed choices  | Complex conditions               |
| Cleaner code            | More flexible                    |
| Faster for menu systems | Better for ranges                |
| Easy to read            | Suitable for logical expressions |

---

# Real-World Applications

Switch statements are commonly used in:

* ATM Systems
* Calculator Applications
* Restaurant Ordering Systems
* Traffic Signal Controllers
* Banking Menus
* Mobile App Menus
* Game Menus

---

# Challenge Exercises

### Challenge 1

Create an ATM menu.

```text
1 → Balance
2 → Deposit
3 → Withdraw
4 → Exit
```

---

### Challenge 2

Create a calculator using switch.

Operations:

```text
+
-
*
/
```

---

### Challenge 3

Create a month display system.

```text
1 → January
2 → February
...
12 → December
```

---

### Challenge 4

Create a student portal menu.

```text
1 → View Marks
2 → View Attendance
3 → View Fees
4 → Logout
```

---

# Summary

* Switch is used when there are multiple fixed choices.
* Each case represents one possible value.
* Break prevents fall-through.
* Default executes when no case matches.
* Switch makes menu-driven programs easier to build.

---

# Conclusion

The Switch Statement is a powerful decision-making tool that simplifies handling multiple choices. It is widely used in real-world applications such as ATM systems, calculators, menu-driven programs, and management systems.
