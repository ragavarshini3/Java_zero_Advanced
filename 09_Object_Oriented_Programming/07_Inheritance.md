# Inheritance in Java

In real-world applications, many classes share common properties and behaviors.

For example:

- A Car, Bike, and Bus are all Vehicles.
- A Dog, Cat, and Lion are all Animals.
- A Student and Teacher are both People.
- A Savings Account and Current Account are both Bank Accounts.

Instead of writing the same variables and methods again in every class, Java provides **Inheritance**.

Inheritance allows one class to use the properties and methods of another class.

---

# What is Inheritance?

**Inheritance** is an Object-Oriented Programming concept where one class acquires the properties and behaviors of another class.

The class that gives properties is called the **Parent Class** or **Super Class**.

The class that receives properties is called the **Child Class** or **Sub Class**.

---

# Real-World Example

Consider a Vehicle.

```text
Vehicle
│
├── Car
├── Bike
└── Bus
```

All vehicles may have common properties such as:

- brand
- color
- speed

All vehicles may have common behaviors such as:

- start()
- stop()
- accelerate()

Instead of writing these again in every class, we create them once in the `Vehicle` class.

Then `Car`, `Bike`, and `Bus` can inherit them.

---

# Why Do We Need Inheritance?

Without inheritance:

```text
Car Class
- brand
- color
- start()

Bike Class
- brand
- color
- start()

Bus Class
- brand
- color
- start()
```

The same code is repeated many times.

With inheritance:

```text
Vehicle Class
- brand
- color
- start()

Car Class extends Vehicle
Bike Class extends Vehicle
Bus Class extends Vehicle
```

This reduces duplicate code.

---

# Syntax of Inheritance

```java
class ParentClass
{
    // parent class variables and methods
}

class ChildClass extends ParentClass
{
    // child class variables and methods
}
```

---

# Example 1: Basic Inheritance

```java
class Animal
{
    void eat()
    {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal
{
    void bark()
    {
        System.out.println("Dog is barking");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Dog dog = new Dog();

        dog.eat();

        dog.bark();
    }
}
```

### Output

```text
Animal is eating
Dog is barking
```

---

# Explanation

```text
Animal
│
└── Dog
```

The `Dog` class inherits the `eat()` method from the `Animal` class.

The `Dog` class also has its own method called `bark()`.

---

# Example 2: Vehicle and Car

```java
class Vehicle
{
    String brand = "Toyota";

    void start()
    {
        System.out.println("Vehicle started");
    }
}

class Car extends Vehicle
{
    void drive()
    {
        System.out.println("Car is driving");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Car car = new Car();

        System.out.println("Brand: " + car.brand);

        car.start();

        car.drive();
    }
}
```

### Output

```text
Brand: Toyota
Vehicle started
Car is driving
```

---

# Parent Class and Child Class

| Parent Class | Child Class |
|---|---|
| Gives properties and methods | Receives properties and methods |
| Also called Super Class | Also called Sub Class |
| General class | Specific class |
| Example: Vehicle | Example: Car |

---

# Types of Inheritance in Java

Java supports the following inheritance types:

```text
1. Single Inheritance
2. Multilevel Inheritance
3. Hierarchical Inheritance
```

Java does not support multiple inheritance using classes.

However, multiple inheritance can be achieved using interfaces.

---

# 1. Single Inheritance

Single inheritance means one child class inherits from one parent class.

```text
Animal
│
└── Dog
```

Example:

```java
class Animal
{
    void eat()
    {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal
{
    void bark()
    {
        System.out.println("Dog is barking");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Dog dog = new Dog();

        dog.eat();
        dog.bark();
    }
}
```

---

# 2. Multilevel Inheritance

Multilevel inheritance means a class inherits from another child class.

```text
Animal
│
└── Dog
    │
    └── Puppy
```

Example:

```java
class Animal
{
    void eat()
    {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal
{
    void bark()
    {
        System.out.println("Dog is barking");
    }
}

class Puppy extends Dog
{
    void weep()
    {
        System.out.println("Puppy is weeping");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Puppy puppy = new Puppy();

        puppy.eat();
        puppy.bark();
        puppy.weep();
    }
}
```

### Output

```text
Animal is eating
Dog is barking
Puppy is weeping
```

---

# 3. Hierarchical Inheritance

Hierarchical inheritance means multiple child classes inherit from one parent class.

```text
Vehicle
│
├── Car
├── Bike
└── Bus
```

Example:

```java
class Vehicle
{
    void start()
    {
        System.out.println("Vehicle started");
    }
}

class Car extends Vehicle
{
    void driveCar()
    {
        System.out.println("Car is driving");
    }
}

class Bike extends Vehicle
{
    void rideBike()
    {
        System.out.println("Bike is moving");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Car car = new Car();
        Bike bike = new Bike();

        car.start();
        car.driveCar();

        bike.start();
        bike.rideBike();
    }
}
```

---

# Real-World Scenario 1: Student and Person

A student is a person.

```java
class Person
{
    String name;
    int age;

    void displayPersonDetails()
    {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}

class Student extends Person
{
    String department;

    void displayStudentDetails()
    {
        System.out.println("Department: " + department);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Student student = new Student();

        student.name = "Ragavarshini";
        student.age = 20;
        student.department = "AI & DS";

        student.displayPersonDetails();
        student.displayStudentDetails();
    }
}
```

### Output

```text
Name: Ragavarshini
Age: 20
Department: AI & DS
```

---

# Real-World Scenario 2: Employee and Manager

A manager is an employee.

```java
class Employee
{
    String employeeName;
    double salary;

    void displayEmployee()
    {
        System.out.println("Employee: " + employeeName);
        System.out.println("Salary: ₹" + salary);
    }
}

class Manager extends Employee
{
    String department;

    void displayManager()
    {
        System.out.println("Department: " + department);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Manager manager = new Manager();

        manager.employeeName = "Alice";
        manager.salary = 65000;
        manager.department = "Human Resources";

        manager.displayEmployee();
        manager.displayManager();
    }
}
```

---

# Real-World Scenario 3: Bank Account

A savings account is a type of bank account.

```java
class BankAccount
{
    String customerName;
    double balance;

    void displayBalance()
    {
        System.out.println("Customer: " + customerName);
        System.out.println("Balance: ₹" + balance);
    }
}

class SavingsAccount extends BankAccount
{
    double interestRate;

    void calculateInterest()
    {
        double interest = balance * interestRate / 100;

        System.out.println("Interest: ₹" + interest);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        SavingsAccount account = new SavingsAccount();

        account.customerName = "Rahul";
        account.balance = 50000;
        account.interestRate = 5;

        account.displayBalance();
        account.calculateInterest();
    }
}
```

---

# Real-World Scenario 4: Online Shopping

A mobile phone is a product.

```java
class Product
{
    String productName;
    double price;

    void displayProduct()
    {
        System.out.println("Product: " + productName);
        System.out.println("Price: ₹" + price);
    }
}

class Mobile extends Product
{
    String brand;
    String model;

    void displayMobileDetails()
    {
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Mobile mobile = new Mobile();

        mobile.productName = "Smartphone";
        mobile.price = 35000;
        mobile.brand = "Samsung";
        mobile.model = "Galaxy S24";

        mobile.displayProduct();
        mobile.displayMobileDetails();
    }
}
```

---

# Advantages of Inheritance

- Reduces duplicate code
- Improves code reusability
- Makes programs easier to maintain
- Supports hierarchical relationships
- Improves readability
- Allows extension of existing classes
- Supports polymorphism

---

# Important Rules of Inheritance

- Use the `extends` keyword to inherit a class.
- A child class can access public and protected members of the parent class.
- Private members cannot be accessed directly by the child class.
- Constructors are not inherited.
- A class can inherit only one class directly.
- Java supports multiple inheritance through interfaces, not classes.

---

# Private Members in Inheritance

Private variables cannot be accessed directly in child classes.

```java
class Parent
{
    private String name = "Java";
}

class Child extends Parent
{
    void display()
    {
        // System.out.println(name);
        // Error: name is private
    }
}
```

To access private data, use getter and setter methods.

---

# Inheritance vs Composition

| Inheritance | Composition |
|---|---|
| Represents an "is-a" relationship | Represents a "has-a" relationship |
| Car is a Vehicle | Car has an Engine |
| Uses `extends` | Uses object reference |
| Reuses parent class features | Uses another class object |

---

# Common Mistakes

## Forgetting `extends`

❌ Incorrect:

```java
class Dog Animal
{
}
```

✅ Correct:

```java
class Dog extends Animal
{
}
```

---

## Accessing Private Variables Directly

❌ Incorrect:

```java
class Parent
{
    private int value = 10;
}

class Child extends Parent
{
    void show()
    {
        System.out.println(value);
    }
}
```

Use getter methods instead.

---

## Creating Parent Object to Call Child Method

❌ Incorrect:

```java
Animal animal = new Animal();

animal.bark();
```

The parent class object cannot access child-specific methods.

---

# Interview Questions

### What is inheritance?

Inheritance is the process where one class acquires the properties and methods of another class.

---

### Which keyword is used for inheritance?

```java
extends
```

---

### What is the parent class?

The class whose properties and methods are inherited.

---

### What is the child class?

The class that inherits properties and methods from another class.

---

### Are constructors inherited?

No. Constructors are not inherited.

---

### Does Java support multiple inheritance using classes?

No. Java supports multiple inheritance using interfaces.

---

### What are the types of inheritance supported by Java?

- Single inheritance
- Multilevel inheritance
- Hierarchical inheritance

---

# Challenge Exercises

### Challenge 1

Create a `Vehicle` class with:

- brand
- color
- start()

Create a `Car` class that inherits from `Vehicle`.

---

### Challenge 2

Create an `Animal` class with an `eat()` method.

Create a `Dog` class that inherits from `Animal` and adds a `bark()` method.

---

### Challenge 3

Create a `Person` class with name and age.

Create a `Student` class that inherits from `Person` and adds department.

---

### Challenge 4

Create an `Employee` class.

Create a `Manager` class that inherits from `Employee`.

---

### Challenge 5

Create a multilevel inheritance example using:

```text
Vehicle → Car → ElectricCar
```

---

# Summary

- Inheritance allows one class to acquire properties and methods from another class.
- The parent class is also called the super class.
- The child class is also called the sub class.
- Use the `extends` keyword to create inheritance.
- Inheritance reduces duplicate code and improves reusability.
- Java supports single, multilevel, and hierarchical inheritance using classes.

---

# Conclusion

Inheritance is one of the most important concepts in Java Object-Oriented Programming. It allows developers to reuse existing code and build specialized classes from general classes. Inheritance is widely used in real-world applications such as banking systems, student management systems, e-commerce platforms, robotics, and enterprise software.
