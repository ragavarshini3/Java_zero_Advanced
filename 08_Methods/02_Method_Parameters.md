 # Method Parameters in Java

In the previous lesson, we learned how to create and call methods.

However, many real-world applications require methods to work with different values every time they are called.

For example:

* Add two numbers
* Calculate employee salary
* Display student details
* Transfer money between accounts
* Calculate product discounts

Instead of creating multiple methods for different values, Java allows us to pass data to methods using **Parameters**.

---

# What are Method Parameters?

A **Parameter** is a variable declared inside the method definition that receives values when the method is called.

The values passed to a method are called **Arguments**.

---

# Real-World Example

Imagine a calculator.

Instead of creating:

```text
add10And20()

add50And30()

add100And200()
```

We create one method:

```text
add(int a, int b)
```

Now it can add any two numbers.

---

# Why Do We Need Parameters?

Without Parameters

```java
static void display()
{
    System.out.println("Welcome Ragavarshini");
}
```

This always prints the same name.

With Parameters

```java
display("Ragavarshini");
display("John");
display("Alice");
```

The same method works for different users.

---

# Syntax

```java
accessModifier returnType methodName(dataType parameter)
{
    // code
}
```

Example

```java
static void display(String name)
{
    System.out.println(name);
}
```

---

# Parameters vs Arguments

| Parameter              | Argument                  |
| ---------------------- | ------------------------- |
| Variable inside method | Actual value passed       |
| Declared in method     | Passed during method call |
| Receives data          | Sends data                |

Example

```java
static void greet(String name)
```

Here,

```text
name
```

is the **parameter**.

Calling

```java
greet("Ragavarshini");
```

Here,

```text
"Ragavarshini"
```

is the **argument**.

---

# Example 1: Display Student Name

```java
public class Student {

    static void display(String name)
    {
        System.out.println("Student Name : " + name);
    }

    public static void main(String[] args)
    {
        display("Ragavarshini");
        display("Rahul");
        display("Priya");
    }

}
```

### Output

```text
Student Name : Ragavarshini
Student Name : Rahul
Student Name : Priya
```

---

# Example 2: Addition of Two Numbers

```java
public class Addition {

    static void add(int a, int b)
    {
        System.out.println("Sum = " + (a + b));
    }

    public static void main(String[] args)
    {
        add(10,20);
        add(100,50);
        add(7,8);
    }

}
```

### Output

```text
Sum = 30
Sum = 150
Sum = 15
```

---

# Example 3: Product Price

```java
public class Product {

    static void displayProduct(String product, double price)
    {
        System.out.println("Product : " + product);
        System.out.println("Price : ₹" + price);
    }

    public static void main(String[] args)
    {
        displayProduct("Laptop",65000);
        displayProduct("Mouse",1200);
    }

}
```

### Output

```text
Product : Laptop
Price : ₹65000.0

Product : Mouse
Price : ₹1200.0
```

---

# Multiple Parameters

A method can receive multiple parameters.

Example

```java
static void employee(String name, int age, double salary)
{
    System.out.println(name);
    System.out.println(age);
    System.out.println(salary);
}
```

Calling

```java
employee("Alice",25,45000);
```

---

# Example 4: Employee Details

```java
public class Employee {

    static void employeeDetails(String name,
                                int age,
                                double salary)
    {
        System.out.println("Name : " + name);
        System.out.println("Age : " + age);
        System.out.println("Salary : ₹" + salary);
    }

    public static void main(String[] args)
    {
        employeeDetails("Alice",25,45000);
        employeeDetails("Bob",30,52000);
    }

}
```

---

# Pass by Value in Java

Java always uses **Pass by Value**.

This means a copy of the value is passed to the method.

Changes inside the method do not affect the original variable.

---

# Example

```java
public class PassByValue {

    static void change(int number)
    {
        number = 100;

        System.out.println("Inside Method : " + number);
    }

    public static void main(String[] args)
    {
        int value = 50;

        change(value);

        System.out.println("Outside Method : " + value);
    }

}
```

### Output

```text
Inside Method : 100
Outside Method : 50
```

---

# Explanation

Original Variable

```text
value = 50
```

Method receives

```text
number = 50
```

Changing

```text
number
```

does not change

```text
value
```

---

# Real-World Scenario 1: ATM Withdrawal

```java
public class ATM {

    static void withdraw(String customer,
                         double amount)
    {
        System.out.println(customer +
                " withdrew ₹" + amount);
    }

    public static void main(String[] args)
    {
        withdraw("Rahul",5000);
        withdraw("Priya",2000);
    }

}
```

---

# Real-World Scenario 2: Banking System

```java
public class Bank {

    static void transfer(String sender,
                         String receiver,
                         double amount)
    {
        System.out.println(sender +
                " transferred ₹" +
                amount +
                " to " +
                receiver);
    }

    public static void main(String[] args)
    {
        transfer("Alice",
                 "Bob",
                 15000);
    }

}
```

---

# Real-World Scenario 3: Student Marks

```java
public class Marks {

    static void displayMarks(String student,
                             int mark)
    {
        System.out.println(student +
                " scored " +
                mark);
    }

    public static void main(String[] args)
    {
        displayMarks("Ragavarshini",95);
        displayMarks("Rahul",88);
    }

}
```

---

# Real-World Scenario 4: Online Shopping

```java
public class Shopping {

    static void order(String product,
                      int quantity)
    {
        System.out.println(quantity +
                " x " +
                product +
                " Ordered");
    }

    public static void main(String[] args)
    {
        order("Laptop",2);
        order("Keyboard",3);
    }

}
```

---

# Common Mistakes

## Incorrect Number of Arguments

❌ Incorrect

```java
add(10);
```

Method expects

```java
add(int a, int b)
```

This causes a compilation error.

---

## Wrong Data Type

❌ Incorrect

```java
add("Java",20);
```

If the method expects integers, passing a String results in an error.

---

# Advantages of Parameters

* Makes methods reusable
* Reduces duplicate code
* Accepts different inputs
* Improves flexibility
* Simplifies program design

---

# Real-World Applications

Method parameters are used in:

* Banking Applications
* ATM Systems
* Student Management Systems
* E-Commerce Websites
* Hospital Management Systems
* Payroll Systems
* Robotics Applications
* AI Applications
* Inventory Management
* Mobile Apps

---

# Challenge Exercises

### Challenge 1

Create a method to display your name using a parameter.

---

### Challenge 2

Create a method to calculate the area of a rectangle using length and breadth.

---

### Challenge 3

Create a method to display employee details using three parameters.

---

### Challenge 4

Create a method to calculate the total price of products.

---

### Challenge 5

Create a method that accepts student name and marks, then displays the result.

---

# Summary

* Parameters receive data inside methods.
* Arguments are the actual values passed during method calls.
* A method can have one or more parameters.
* Java uses Pass by Value.
* Parameters make methods reusable and flexible.

---

# Conclusion

Method parameters allow Java programs to handle dynamic data efficiently. Instead of creating multiple methods for different values, developers can create one reusable method that accepts parameters. This concept is widely used in real-world applications such as banking systems, e-commerce platforms, robotics, AI applications, and enterprise software.
