# Data Types in Java

A data type specifies the type of data that a variable can store. Java is a strongly typed language, which means every variable must have a defined data type.

Data types help the compiler allocate memory efficiently and prevent invalid operations.

---

# Why Do We Need Data Types?

Data types help Java determine:

* What kind of value is stored
* How much memory is required
* What operations can be performed

Example:

```java
int age = 20;
double salary = 45000.50;
char grade = 'A';
```

Here:

* `int` stores integers
* `double` stores decimal numbers
* `char` stores a single character

---

# Types of Data Types in Java

Java data types are divided into two categories:

```text
Data Types
│
├── Primitive Data Types
│   ├── byte
│   ├── short
│   ├── int
│   ├── long
│   ├── float
│   ├── double
│   ├── char
│   └── boolean
│
└── Non-Primitive Data Types
    ├── String
    ├── Arrays
    ├── Classes
    └── Objects
```

---

# Primitive Data Types

Primitive data types are predefined by Java and store simple values.

## 1. byte

Stores small integer values.

### Example

```java
byte age = 25;

System.out.println(age);
```

### Output

```text
25
```

### Memory Size

```text
1 Byte
```

### Range

```text
-128 to 127
```

---

## 2. short

Stores integer values larger than byte.

### Example

```java
short population = 25000;

System.out.println(population);
```

### Output

```text
25000
```

### Memory Size

```text
2 Bytes
```

---

## 3. int

Most commonly used integer data type.

### Example

```java
int marks = 95;

System.out.println(marks);
```

### Output

```text
95
```

### Memory Size

```text
4 Bytes
```

---

## 4. long

Used for very large integer values.

### Example

```java
long distance = 9876543210L;

System.out.println(distance);
```

### Output

```text
9876543210
```

### Note

Always use `L` at the end.

---

## 5. float

Stores decimal values.

### Example

```java
float price = 99.99f;

System.out.println(price);
```

### Output

```text
99.99
```

### Note

Always use `f` at the end.

### Memory Size

```text
4 Bytes
```

---

## 6. double

Stores large decimal values with higher precision.

### Example

```java
double salary = 45678.90;

System.out.println(salary);
```

### Output

```text
45678.9
```

### Memory Size

```text
8 Bytes
```

---

## 7. char

Stores a single character.

### Example

```java
char grade = 'A';

System.out.println(grade);
```

### Output

```text
A
```

### Memory Size

```text
2 Bytes
```

---

## 8. boolean

Stores true or false values.

### Example

```java
boolean isPassed = true;

System.out.println(isPassed);
```

### Output

```text
true
```

---

# Primitive Data Types Summary

| Data Type | Size           | Example |
| --------- | -------------- | ------- |
| byte      | 1 Byte         | 10      |
| short     | 2 Bytes        | 200     |
| int       | 4 Bytes        | 5000    |
| long      | 8 Bytes        | 900000L |
| float     | 4 Bytes        | 12.5f   |
| double    | 8 Bytes        | 12.5    |
| char      | 2 Bytes        | 'A'     |
| boolean   | Depends on JVM | true    |

---

# Non-Primitive Data Types

Non-primitive data types are created by programmers or provided by Java libraries.

Examples:

* String
* Arrays
* Classes
* Objects

---

## String Example

```java
String name = "John";

System.out.println(name);
```

### Output

```text
John
```

Unlike `char`, String can store multiple characters.

---

## Array Example

```java
int[] numbers = {10, 20, 30};

System.out.println(numbers[0]);
```

### Output

```text
10
```

---

# Complete Example Program

```java
public class DataTypesExample {

    public static void main(String[] args) {

        byte age = 25;
        short year = 2025;
        int marks = 95;
        long population = 9876543210L;

        float height = 5.8f;
        double salary = 45000.75;

        char grade = 'A';
        boolean passed = true;

        String name = "John";

        System.out.println("Age: " + age);
        System.out.println("Year: " + year);
        System.out.println("Marks: " + marks);
        System.out.println("Population: " + population);
        System.out.println("Height: " + height);
        System.out.println("Salary: " + salary);
        System.out.println("Grade: " + grade);
        System.out.println("Passed: " + passed);
        System.out.println("Name: " + name);
    }
}
```

### Output

```text
Age: 25
Year: 2025
Marks: 95
Population: 9876543210
Height: 5.8
Salary: 45000.75
Grade: A
Passed: true
Name: John
```

---

# Common Mistakes

## Missing 'L' for long

❌ Incorrect

```java
long number = 9876543210;
```

✅ Correct

```java
long number = 9876543210L;
```

---

## Missing 'f' for float

❌ Incorrect

```java
float value = 12.5;
```

✅ Correct

```java
float value = 12.5f;
```

---

## Using Double Quotes for char

❌ Incorrect

```java
char grade = "A";
```

✅ Correct

```java
char grade = 'A';
```

---

# Best Practices

* Use `int` for whole numbers.
* Use `double` for decimal values.
* Use `boolean` for true/false conditions.
* Use meaningful variable names.
* Choose the smallest suitable data type when memory matters.

---

# Summary

* Data types define the type of data a variable can store.
* Java has Primitive and Non-Primitive data types.
* Primitive types store simple values.
* Non-Primitive types store objects and collections of data.
* Choosing the correct data type improves performance and readability.

---

# Conclusion

Data types are the foundation of Java programming. Understanding them helps developers store and manipulate data correctly, making programs efficient, reliable, and easy to maintain.
