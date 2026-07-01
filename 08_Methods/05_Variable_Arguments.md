# Variable Arguments (Varargs) in Java

In the previous lessons, we learned how to create methods with fixed parameters.

However, in many real-world applications, we don't know how many values a user will provide.

For example:

* A calculator may add 2, 3, 5, or 10 numbers.
* A shopping cart may contain any number of products.
* A teacher may enter marks for different numbers of students.
* A company may calculate bonuses for multiple employees.

Instead of creating many overloaded methods, Java provides **Variable Arguments (Varargs)**.

---

# What are Variable Arguments?

Variable Arguments (Varargs) allow a method to accept **zero or more arguments** of the same data type.

Varargs are represented using three dots (`...`).

---

# Why Do We Need Varargs?

Without Varargs:

```java
add(int a, int b)

add(int a, int b, int c)

add(int a, int b, int c, int d)

add(int a, int b, int c, int d, int e)
```

Many overloaded methods are required.

With Varargs:

```java
add(int... numbers)
```

One method can handle any number of integers.

---

# Syntax

```java
returnType methodName(dataType... variableName)
{
    // code
}
```

Example

```java
static void display(String... names)
{
    // code
}
```

---

# How Varargs Work

When Java receives variable arguments, it internally converts them into an array.

Example

```java
add(10,20,30,40);
```

Internally becomes

```java
int[] numbers = {10,20,30,40};
```

---

# Example 1: Display Numbers

```java
public class VarargsExample {

    static void display(int... numbers)
    {
        for(int number : numbers)
        {
            System.out.println(number);
        }
    }

    public static void main(String[] args)
    {

        display(10,20);

        display(10,20,30);

        display(10,20,30,40);

    }

}
```

### Output

```text
10
20

10
20
30

10
20
30
40
```

---

# Example 2: Sum of Numbers

```java
public class Addition {

    static int add(int... numbers)
    {
        int sum = 0;

        for(int number : numbers)
        {
            sum += number;
        }

        return sum;
    }

    public static void main(String[] args)
    {

        System.out.println(add(10,20));

        System.out.println(add(10,20,30));

        System.out.println(add(10,20,30,40));

    }

}
```

### Output

```text
30
60
100
```

---

# Example 3: Find Maximum Number

```java
public class Maximum {

    static int max(int... numbers)
    {
        int max = numbers[0];

        for(int number : numbers)
        {
            if(number > max)
            {
                max = number;
            }
        }

        return max;
    }

    public static void main(String[] args)
    {

        System.out.println(max(15,22,5,90,18));

    }

}
```

### Output

```text
90
```

---

# Example 4: Display Student Names

```java
public class Student {

    static void students(String... names)
    {
        for(String name : names)
        {
            System.out.println(name);
        }
    }

    public static void main(String[] args)
    {

        students("Ragavarshini","Rahul","Alice","John");

    }

}
```

### Output

```text
Ragavarshini
Rahul
Alice
John
```

---

# Rules for Varargs

* Only one varargs parameter is allowed in a method.
* Varargs must be the **last parameter**.

Correct

```java
static void display(String department,
                    int... marks)
{
}
```

Incorrect

```java
static void display(int... marks,
                    String department)
{
}
```

Compilation Error.

---

# Varargs with Normal Parameters

```java
public class Employee {

    static void salary(String department,
                       double... salaries)
    {

        System.out.println("Department : " + department);

        for(double salary : salaries)
        {
            System.out.println(salary);
        }

    }

    public static void main(String[] args)
    {

        salary("IT",45000,50000,55000);

    }

}
```

---

# Real-World Scenario 1: Shopping Cart

A customer can buy any number of products.

```java
public class Shopping {

    static void products(String... items)
    {
        System.out.println("Shopping Cart");

        for(String item : items)
        {
            System.out.println(item);
        }

    }

    public static void main(String[] args)
    {

        products("Laptop","Mouse","Keyboard","Monitor");

    }

}
```

---

# Real-World Scenario 2: Student Marks

```java
public class Marks {

    static int total(int... marks)
    {
        int sum = 0;

        for(int mark : marks)
        {
            sum += mark;
        }

        return sum;
    }

    public static void main(String[] args)
    {

        System.out.println("Total Marks : " + total(85,90,78,88,95));

    }

}
```

---

# Real-World Scenario 3: Restaurant Billing

```java
public class Restaurant {

    static double bill(double... prices)
    {
        double total = 0;

        for(double price : prices)
        {
            total += price;
        }

        return total;
    }

    public static void main(String[] args)
    {

        System.out.println("Total Bill : ₹" + bill(120,250,180,90));

    }

}
```

---

# Real-World Scenario 4: Company Bonus

```java
public class Company {

    static void bonus(double... bonusAmounts)
    {
        for(double bonus : bonusAmounts)
        {
            System.out.println("Bonus : ₹" + bonus);
        }
    }

    public static void main(String[] args)
    {

        bonus(5000,8000,6000,9000);

    }

}
```

---

# Varargs vs Array

| Varargs                          | Array                      |
| -------------------------------- | -------------------------- |
| Easy to use                      | Must create array manually |
| Accepts multiple values directly | Requires array object      |
| Converted into array internally  | Already an array           |
| Cleaner syntax                   | More code                  |

---

# Common Mistakes

## Varargs Not Last

❌ Incorrect

```java
static void display(int... numbers,
                    String name)
{
}
```

---

## Multiple Varargs

❌ Incorrect

```java
static void show(int... marks,
                 double... salary)
{
}
```

Only one varargs parameter is allowed.

---

# Real-World Applications

Variable Arguments are used in:

* Calculator Applications
* Shopping Carts
* Student Result Systems
* Banking Software
* Payroll Systems
* Report Generation
* Data Analytics
* AI Applications
* Robotics
* Enterprise Software

---

# Interview Questions

### What are Variable Arguments?

A feature that allows a method to accept zero or more arguments.

---

### What symbol is used for Varargs?

```java
...
```

---

### Can a method have two Varargs?

No.

---

### Where should Varargs be placed?

As the last parameter.

---

### How are Varargs stored internally?

As an array.

---

# Challenge Exercises

### Challenge 1

Create a method to calculate the sum of any number of integers.

---

### Challenge 2

Create a method to find the average of multiple marks.

---

### Challenge 3

Create a method to display any number of employee names.

---

### Challenge 4

Create a shopping bill calculator using variable arguments.

---

### Challenge 5

Create a method to find the smallest number from multiple inputs.

---

# Summary

* Variable Arguments allow methods to accept any number of values.
* Varargs reduce the need for multiple overloaded methods.
* Java internally converts Varargs into arrays.
* Only one Varargs parameter is allowed, and it must be the last parameter.
* Varargs make methods flexible and reusable.

---

# Conclusion

Variable Arguments simplify Java programming by allowing methods to handle a flexible number of inputs without creating multiple overloaded methods. They are widely used in real-world applications such as calculators, billing systems, report generation, and enterprise software, making code cleaner, more reusable, and easier to maintain.
