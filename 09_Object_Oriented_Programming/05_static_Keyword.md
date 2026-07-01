# Static Keyword in Java

In Java, variables and methods normally belong to an object.

This means every time an object is created, a separate copy of its instance variables is created.

However, some information should be shared among all objects.

For example:

- College Name
- Company Name
- Bank Name
- Country Name
- PI Value
- Employee Count

These values are common for every object.

Java provides the **static keyword** to create members that belong to the class instead of individual objects.

---

# What is the static Keyword?

The **static** keyword makes a variable, method, block, or nested class belong to the **class** rather than to individual objects.

A static member is created only once, regardless of how many objects are created.

---

# Why Do We Need static?

Imagine a college.

Every student belongs to the same college.

Without static:

```
Student 1

College = KGISL

Student 2

College = KGISL

Student 3

College = KGISL
```

Each object stores the same value.

This wastes memory.

Using static:

```
Student Class

↓

College = KGISL

↓

Shared by all Students
```

Only one copy exists.

---

# Syntax

## Static Variable

```java
static dataType variableName;
```

Example

```java
static String college = "KGISL Institute of Technology";
```

---

## Static Method

```java
static void display()
{

}
```

---

# Static Variable Example

```java
class Student
{

    String name;

    static String college = "KGISL";

}

public class Main
{

    public static void main(String[] args)
    {

        Student s1 = new Student();

        Student s2 = new Student();

        s1.name = "Ragavarshini";

        s2.name = "Siri";

        System.out.println(s1.name);

        System.out.println(Student.college);

        System.out.println(s2.name);

        System.out.println(Student.college);

    }

}
```

### Output

```text
Ragavarshini
KGISL
Siri
KGISL
```

---

# Explanation

Memory

```
Student Class

↓

college = KGISL

↓

Shared

↓

Student 1

↓

Student 2
```

Only one copy of **college** exists.

---

# Static Method

Static methods belong to the class.

They can be called without creating an object.

---

# Example

```java
class Calculator
{

    static void welcome()
    {
        System.out.println("Welcome to Java");
    }

}

public class Main
{

    public static void main(String[] args)
    {

        Calculator.welcome();

    }

}
```

### Output

```text
Welcome to Java
```

---

# Why is main() Static?

The Java Virtual Machine (JVM) calls

```java
main()
```

without creating an object.

Therefore,

```
main()
```

must be static.

---

# Static Block

A static block executes only once when the class is loaded into memory.

---

# Syntax

```java
static
{

}
```

---

# Example

```java
class Demo
{

    static
    {
        System.out.println("Static Block");
    }

    public static void main(String[] args)
    {
        System.out.println("Main Method");
    }

}
```

### Output

```text
Static Block
Main Method
```

---

# Real-World Scenario 1: Student Management System

```java
class Student
{

    String name;

    static String college = "KGISL";

    Student(String name)
    {
        this.name = name;
    }

    void display()
    {
        System.out.println(name + " - " + college);
    }

}

public class Main
{

    public static void main(String[] args)
    {

        Student s1 = new Student("Ragavarshini");

        Student s2 = new Student("Abhi");

        s1.display();

        s2.display();

    }

}
```

### Output

```text
Ragavarshini - KGISL
Abhi - KGISL
```

---

# Real-World Scenario 2: Banking System

```java
class Bank
{

    static String bankName = "State Bank";

    String customer;

    Bank(String customer)
    {
        this.customer = customer;
    }

    void display()
    {
        System.out.println(customer + " - " + bankName);
    }

}

public class Main
{

    public static void main(String[] args)
    {

        Bank b1 = new Bank("Alice");

        Bank b2 = new Bank("Bob");

        b1.display();

        b2.display();

    }

}
```

---

# Real-World Scenario 3: Employee Counter

```java
class Employee
{

    static int count = 0;

    Employee()
    {
        count++;
    }

}

public class Main
{

    public static void main(String[] args)
    {

        new Employee();

        new Employee();

        new Employee();

        System.out.println(Employee.count);

    }

}
```

### Output

```text
3
```

---

# Static Method vs Instance Method

| Static Method | Instance Method |
|---------------|-----------------|
| Belongs to class | Belongs to object |
| Called using class name | Called using object |
| Cannot access instance variables directly | Can access all members |
| Memory allocated once | Memory allocated for every object |

---

# Static Variable vs Instance Variable

| Static Variable | Instance Variable |
|-----------------|-------------------|
| Shared by all objects | Separate copy for each object |
| Created once | Created every time an object is created |
| Belongs to class | Belongs to object |

---

# Rules of static

- Static methods cannot use **this** keyword.
- Static methods cannot directly access instance variables.
- Static methods can access static variables and static methods.
- Static variables are initialized when the class is loaded.

---

# Common Mistakes

## Accessing Instance Variable Inside Static Method

❌ Incorrect

```java
class Student
{

    String name;

    static void display()
    {
        System.out.println(name);
    }

}
```

Compilation Error

---

## Correct

```java
class Student
{

    static String college = "KGISL";

    static void display()
    {
        System.out.println(college);
    }

}
```

---

# Advantages of static

- Saves memory
- Easy access without objects
- Shared data
- Better performance
- Useful for utility methods

---

# Real-World Applications

The static keyword is used in:

- Math Utility Classes
- Banking Systems
- Student Management Systems
- Logging Frameworks
- Configuration Classes
- Database Connections
- Enterprise Applications
- Android Development
- Spring Boot Projects
- AI Applications

---

# Interview Questions

### What is the static keyword?

It makes a member belong to the class instead of an object.

---

### Can static methods access instance variables?

No.

---

### Why is main() static?

Because the JVM calls it without creating an object.

---

### Can constructors be static?

No.

---

### Can static methods be overloaded?

Yes.

---

### Can static methods be overridden?

No. They are hidden, not overridden.

---

# Challenge Exercises

### Challenge 1

Create a Student class with a static college name.

---

### Challenge 2

Create a static method to calculate the square of a number.

---

### Challenge 3

Create an Employee class that counts the number of employees using a static variable.

---

### Challenge 4

Create a Bank class with a static bank name shared by all customers.

---

### Challenge 5

Create a utility class with static methods for addition, subtraction, multiplication, and division.

---

# Summary

- The static keyword belongs to the class, not the object.
- Static variables are shared among all objects.
- Static methods can be called without creating an object.
- Static blocks execute only once when the class is loaded.
- Static members improve memory efficiency and code organization.

---

# Conclusion

The **static** keyword is an important feature of Java that allows developers to create class-level variables and methods shared by all objects. It is widely used for constants, utility methods, counters, configuration values, and application-wide resources. Understanding static is essential for writing efficient, scalable, and professional Java applications.
