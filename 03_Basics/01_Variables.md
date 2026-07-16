# Variables in Java

Variables are used to store data in a Java program. They act as containers that hold values which can be used and modified during program execution.

Without variables, it would be difficult to store and manipulate information in a program. 

------

## What is a Variable? 

A variable is a named memory location used to store data.

### Syntax

```java
dataType variableName = value;
```
 
### Example

```java
int age = 20;
String name = "John";
double salary = 45000.50;
```

In the above example:

* `int`, `String`, and `double` are data types.
* `age`, `name`, and `salary` are variable names.
* `20`, `"John"`, and `45000.50` are values stored in the variables.

---

## Why Do We Need Variables?

Variables help us:

* Store data
* Reuse values
* Perform calculations
* Make programs dynamic
* Improve code readability

### Example Without Variables

```java
System.out.println("John");
System.out.println(20);
```

### Example With Variables

```java
String name = "John";
int age = 20;

System.out.println(name);
System.out.println(age);
```

Using variables makes programs easier to maintain.

---

## Example Program

```java
public class VariablesExample {
    public static void main(String[] args) {

        String name = "John";
        int age = 20;
        double salary = 45000.50;

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Salary: " + salary);
    }
}
```

### Output

```text
Name: John
Age: 20
Salary: 45000.5
```

---

## Variable Declaration and Initialization

### Declaration

Creating a variable without assigning a value.

```java
int age;
```

### Initialization

Assigning a value to a variable.

```java
age = 20;
```

### Declaration and Initialization Together

```java
int age = 20;
```

---

## Rules for Naming Variables

### Valid Variable Names

```java
age
studentName
totalMarks
salary123
_marks
```

### Invalid Variable Names

```java
1age
student-name
total marks
class
```

### Reasons

* Cannot start with a number.
* Cannot contain spaces.
* Cannot contain special characters except `_` and `$`.
* Cannot use Java keywords.

---

## Java Naming Conventions

Java follows the **camelCase** convention for variable names.

### Good Examples

```java
studentName
totalMarks
employeeSalary
```

### Bad Examples

```java
StudentName
TOTAL_MARKS
student_name
```

---

## Types of Variables in Java

Java provides three main types of variables.

### 1. Local Variables

Declared inside a method.

```java
public class Example {
    public static void main(String[] args) {
        int age = 20;
    }
}
```

Characteristics:

* Created when the method starts.
* Destroyed when the method ends.
* Accessible only within the method.

---

### 2. Instance Variables

Declared inside a class but outside methods.

```java
public class Student {
    String name;
}
```

Characteristics:

* Belong to objects.
* Each object gets its own copy.

---

### 3. Static Variables

Declared using the `static` keyword.

```java
public class Student {
    static String college = "ABC College";
}
```

Characteristics:

* Shared by all objects.
* Only one copy exists.

---

## Changing Variable Values

Variables can be updated during execution.

```java
int marks = 80;

marks = 90;

System.out.println(marks);
```

### Output

```text
90
```

---

## Multiple Variable Declarations

Multiple variables of the same type can be declared together.

```java
int x = 10, y = 20, z = 30;
```

---

## Constants

If a value should never change, use the `final` keyword.

```java
final double PI = 3.14159;
```

Attempting to change the value will cause a compilation error.

---

## Memory Representation

```text
Variable      Value
--------      -----
age           20
name          John
salary        45000.50
```

Variables store data in memory and provide easy access using their names.

---

## Common Mistakes

### Using an Undeclared Variable

❌ Incorrect

```java
age = 20;
```

✅ Correct

```java
int age = 20;
```

---

### Using Reserved Keywords

❌ Incorrect

```java
int class = 10;
```

✅ Correct

```java
int classNumber = 10;
```

---

### Duplicate Variable Names

❌ Incorrect

```java
int age = 20;
int age = 30;
```

A variable cannot be declared twice in the same scope.

---

## Best Practices

* Use meaningful variable names.
* Follow camelCase naming convention.
* Keep names short but descriptive.
* Avoid single-letter names except in loops.
* Use `final` for constants.

---

## Summary

* Variables are containers for storing data.
* Every variable has a data type, name, and value.
* Java supports local, instance, and static variables.
* Variable names must follow Java naming rules.
* Variables make programs flexible and reusable.

---

## Conclusion

Variables are one of the most fundamental concepts in Java programming. They allow programs to store, update, and process data efficiently. Understanding variables is essential before learning data types, operators, and other advanced Java concepts.
