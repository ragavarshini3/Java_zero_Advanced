# Return Type in Java

In the previous lessons, we learned about methods and method parameters.

However, many methods not only perform a task but also **return a result** to the calling method.

For example:

* A calculator returns the sum of two numbers.
* A banking application returns the account balance.
* An online shopping application returns the total bill.
* A student management system returns the average marks.

To return values from a method, Java uses the **return type**.

---

# What is a Return Type?

A **Return Type** specifies the type of value that a method sends back to the caller after completing its execution.

If a method returns a value, the return type must match the data type of the returned value.

---

# Why Do We Need Return Types?

Imagine a calculator.

Instead of printing the result directly:

```java
System.out.println(10 + 20);
```

We can create a reusable method.

```java
int result = add(10,20);
```

Now the returned value can be:

* Printed
* Stored
* Used in another calculation
* Sent to another method

---

# Syntax

```java
accessModifier static returnType methodName(parameters)
{
    // code

    return value;
}
```

Example

```java
static int add(int a, int b)
{
    return a + b;
}
```

---

# How Return Works

```text
main()

↓

Calls add(10,20)

↓

Method Calculates

↓

return 30

↓

main() Receives 30

↓

Displays Result
```

---

# Types of Return Values

A method can return:

* int
* double
* float
* long
* char
* boolean
* String
* Objects

If a method does not return anything, use

```java
void
```

---

# Example 1: Returning an Integer

```java
public class Addition {

    static int add(int a, int b)
    {
        return a + b;
    }

    public static void main(String[] args)
    {

        int result = add(10,20);

        System.out.println(result);

    }

}
```

### Output

```text
30
```

---

# Explanation

The method:

```java
add()
```

returns

```text
30
```

The returned value is stored in

```java
result
```

---

# Example 2: Returning a Double

```java
public class Circle {

    static double area(double radius)
    {
        return 3.14 * radius * radius;
    }

    public static void main(String[] args)
    {

        double answer = area(5);

        System.out.println(answer);

    }

}
```

### Output

```text
78.5
```

---

# Example 3: Returning a String

```java
public class Welcome {

    static String message()
    {
        return "Welcome to Java";
    }

    public static void main(String[] args)
    {

        String text = message();

        System.out.println(text);

    }

}
```

### Output

```text
Welcome to Java
```

---

# Example 4: Returning a Boolean

```java
public class Voting {

    static boolean canVote(int age)
    {
        return age >= 18;
    }

    public static void main(String[] args)
    {

        System.out.println(canVote(20));

        System.out.println(canVote(15));

    }

}
```

### Output

```text
true

false
```

---

# Example 5: Returning a Character

```java
public class Grade {

    static char grade()
    {
        return 'A';
    }

    public static void main(String[] args)
    {

        char result = grade();

        System.out.println(result);

    }

}
```

### Output

```text
A
```

---

# Returning User Information

```java
public class Student {

    static String studentName()
    {
        return "Ragavarshini";
    }

    public static void main(String[] args)
    {

        System.out.println(studentName());

    }

}
```

---

# Real-World Scenario 1: Banking Application

A customer wants to know the available balance.

```java
public class Bank {

    static double checkBalance()
    {
        return 50000.50;
    }

    public static void main(String[] args)
    {

        System.out.println(
                "Balance : ₹" +
                checkBalance());

    }

}
```

### Output

```text
Balance : ₹50000.5
```

---

# Real-World Scenario 2: Calculator

```java
public class Calculator {

    static int multiply(int a, int b)
    {
        return a * b;
    }

    public static void main(String[] args)
    {

        int answer = multiply(15,6);

        System.out.println(answer);

    }

}
```

### Output

```text
90
```

---

# Real-World Scenario 3: Employee Salary

```java
public class Employee {

    static double calculateSalary()
    {
        return 55000;
    }

    public static void main(String[] args)
    {

        System.out.println(
                "Salary : ₹" +
                calculateSalary());

    }

}
```

---

# Real-World Scenario 4: Shopping Website

```java
public class Shopping {

    static double totalBill(double price,
                            int quantity)
    {
        return price * quantity;
    }

    public static void main(String[] args)
    {

        double total =
                totalBill(65000,2);

        System.out.println(
                "Total Bill : ₹" +
                total);

    }

}
```

### Output

```text
Total Bill : ₹130000.0
```

---

# Difference Between void and Return Type

| void                         | Return Type                   |
| ---------------------------- | ----------------------------- |
| Returns nothing              | Returns a value               |
| Used for display methods     | Used for calculations         |
| No return statement required | return statement is mandatory |

---

Example

### void Method

```java
static void display()
{
    System.out.println("Hello");
}
```

---

### int Method

```java
static int square(int number)
{
    return number * number;
}
```

---

# Returning Expressions

Java allows returning expressions directly.

```java
static int square(int number)
{
    return number * number;
}
```

---

# Returning Boolean Expressions

```java
static boolean isEven(int number)
{
    return number % 2 == 0;
}
```

---

# Common Mistakes

## Missing Return Statement

❌ Incorrect

```java
static int add()
{
}
```

Compilation Error

```
Missing return statement
```

---

## Wrong Return Type

❌ Incorrect

```java
static int display()
{
    return "Java";
}
```

Error

```
Incompatible Types
```

---

## Correct

```java
static String display()
{
    return "Java";
}
```

---

# Real-World Applications

Methods with return types are widely used in:

* Banking Applications
* Payroll Systems
* Student Management Systems
* Shopping Websites
* Hospital Management Systems
* AI Applications
* Robotics
* Mobile Apps
* Web Applications
* Data Analytics

---

# Challenge Exercises

### Challenge 1

Create a method that returns your name.

---

### Challenge 2

Create a method that returns the square of a number.

---

### Challenge 3

Create a method that returns the largest of two numbers.

---

### Challenge 4

Create a method that returns the average of three marks.

---

### Challenge 5

Create a method that returns whether a person is eligible to vote.

---

### Challenge 6

Create a method that calculates the total bill of a shopping cart.

---

### Challenge 7

Create a method that returns the area of a rectangle.

---

### Challenge 8

Create a method that checks whether a number is positive.

---

# Summary

* A return type specifies the value returned by a method.
* The returned value must match the declared return type.
* The `return` keyword sends the result back to the caller.
* Methods can return primitive data types, Strings, objects, or boolean values.
* Use `void` when no value needs to be returned.

---

# Conclusion

Return types make Java methods more powerful and reusable by allowing them to produce results that can be stored, processed, or passed to other methods. They are essential for building real-world applications such as calculators, banking systems, e-commerce platforms, and enterprise software.
