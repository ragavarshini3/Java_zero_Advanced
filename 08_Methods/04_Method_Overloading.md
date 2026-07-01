# Method Overloading in Java

As software applications grow larger, developers often need multiple methods that perform the **same task** but work with **different types or numbers of inputs**.

For example:

* A calculator can add two numbers.
* It can also add three numbers.
* It can add integers.
* It can add decimal numbers.

Instead of creating different method names like:

* addTwoNumbers()
* addThreeNumbers()
* addDoubleNumbers()

Java allows us to use the **same method name** with different parameter lists.

This concept is called **Method Overloading**.

---

# What is Method Overloading?

**Method Overloading** is the process of creating multiple methods with the **same name** but with **different parameter lists** within the same class.

The compiler decides which method to execute based on the arguments passed during the method call.

---

# Why Do We Need Method Overloading?

Imagine a calculator application.

Without Method Overloading:

```text
addTwoNumbers()

addThreeNumbers()

addDecimalNumbers()
```

Many method names become difficult to remember.

With Method Overloading:

```text
add()

add()

add()
```

Java automatically selects the correct method.

---

# Advantages of Method Overloading

* Improves code readability
* Reduces unnecessary method names
* Increases code reusability
* Makes programs easier to maintain
* Supports compile-time polymorphism

---

# Rules for Method Overloading

Methods must have:

* Different number of parameters

OR

* Different data types

OR

* Different order of parameters

Changing only the return type is **not allowed**.

---

# Syntax

```java
returnType methodName(parameters)
{
    // code
}
```

---

# Example 1: Different Number of Parameters

```java
public class Calculator {

    static int add(int a, int b)
    {
        return a + b;
    }

    static int add(int a, int b, int c)
    {
        return a + b + c;
    }

    public static void main(String[] args)
    {
        System.out.println(add(10,20));

        System.out.println(add(10,20,30));
    }

}
```

### Output

```text
30

60
```

---

# Example 2: Different Data Types

```java
public class Calculator {

    static int multiply(int a, int b)
    {
        return a * b;
    }

    static double multiply(double a, double b)
    {
        return a * b;
    }

    public static void main(String[] args)
    {

        System.out.println(multiply(5,6));

        System.out.println(multiply(5.5,2.0));

    }

}
```

### Output

```text
30

11.0
```

---

# Example 3: Different Parameter Order

```java
public class Display {

    static void show(int age, String name)
    {
        System.out.println(name + " is " + age + " years old.");
    }

    static void show(String name, int age)
    {
        System.out.println(name + " is " + age + " years old.");
    }

    public static void main(String[] args)
    {

        show("Alice",25);

        show(30,"Bob");

    }

}
```

---

# Invalid Method Overloading

Changing only the return type is **not valid**.

❌ Incorrect

```java
int add(int a, int b)
{
    return a + b;
}

double add(int a, int b)
{
    return a + b;
}
```

Compilation Error

```
Method add(int,int) is already defined
```

---

# How Java Chooses the Correct Method

```text
Method Call

↓

Compiler Checks

↓

Number of Arguments

↓

Data Type

↓

Parameter Order

↓

Correct Method Executes
```

---

# Real-World Scenario 1: Calculator

```java
public class Calculator {

    static int add(int a, int b)
    {
        return a + b;
    }

    static double add(double a, double b)
    {
        return a + b;
    }

    public static void main(String[] args)
    {

        System.out.println(add(15,25));

        System.out.println(add(10.5,20.7));

    }

}
```

---

# Real-World Scenario 2: Employee Salary

```java
public class Employee {

    static double salary(double basic)
    {
        return basic;
    }

    static double salary(double basic,
                         double bonus)
    {
        return basic + bonus;
    }

    public static void main(String[] args)
    {

        System.out.println(salary(35000));

        System.out.println(salary(35000,5000));

    }

}
```

---

# Real-World Scenario 3: Shopping Application

```java
public class Shopping {

    static double total(double price)
    {
        return price;
    }

    static double total(double price,
                        int quantity)
    {
        return price * quantity;
    }

    public static void main(String[] args)
    {

        System.out.println(total(65000));

        System.out.println(total(65000,2));

    }

}
```

---

# Real-World Scenario 4: Student Result

```java
public class Student {

    static void display(String name)
    {
        System.out.println("Student : " + name);
    }

    static void display(String name,
                        int mark)
    {
        System.out.println(name + " scored " + mark);
    }

    public static void main(String[] args)
    {

        display("Ragavarshini");

        display("Rahul",95);

    }

}
```

---

# Method Overloading vs Method Overriding

| Method Overloading        | Method Overriding     |
| ------------------------- | --------------------- |
| Same class                | Parent & Child class  |
| Same method name          | Same method name      |
| Different parameters      | Same parameters       |
| Compile-time polymorphism | Run-time polymorphism |

---

# Common Mistakes

## Changing Only Return Type

❌ Invalid

```java
int display()
```

```java
double display()
```

---

## Same Parameters

❌ Invalid

```java
add(int,int)
```

```java
add(int,int)
```

---

## Correct

```java
add(int,int)
```

```java
add(int,int,int)
```

---

# Real-World Applications

Method Overloading is used in:

* Calculator Applications
* Banking Systems
* Student Management Systems
* Shopping Websites
* Mobile Applications
* Web Development
* AI Applications
* Robotics
* Scientific Calculations
* Enterprise Software

---

# Interview Questions

### What is Method Overloading?

Creating multiple methods with the same name but different parameter lists.

---

### Can methods be overloaded by changing only the return type?

No.

---

### Is Method Overloading Compile-Time or Run-Time?

Compile-Time Polymorphism.

---

### Can Constructors be Overloaded?

Yes.

---

### Can Static Methods be Overloaded?

Yes.

---

# Challenge Exercises

### Challenge 1

Create overloaded methods for subtraction.

---

### Challenge 2

Create overloaded methods for multiplication.

---

### Challenge 3

Create overloaded methods to calculate the area of a square and rectangle.

---

### Challenge 4

Create overloaded methods for displaying employee information.

---

### Challenge 5

Create overloaded methods to calculate shopping bills with and without discounts.

---

# Summary

* Method Overloading allows multiple methods with the same name.
* Methods must differ in parameters.
* Java selects the appropriate method during compilation.
* Return type alone cannot distinguish overloaded methods.
* Method Overloading improves flexibility and readability.

---

# Conclusion

Method Overloading is a powerful feature in Java that allows developers to write cleaner, more reusable, and more maintainable code. It is widely used in real-world applications where the same operation needs to handle different types or numbers of inputs, making programs more flexible and user-friendly.
