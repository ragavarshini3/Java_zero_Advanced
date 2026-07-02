# Encapsulation in Java

In real-world applications, data should not always be accessed directly.

For example:

- A bank account balance should not be changed by anyone.
- A student's marks should be updated only by authorized users.
- An employee's salary should be protected.
- A user's password should not be visible to everyone.

To protect data and control access, Java provides **Encapsulation**.

Encapsulation is one of the four main pillars of Object-Oriented Programming.

---

# What is Encapsulation?

**Encapsulation** means wrapping data and methods together inside a single class.

It also means hiding sensitive data from direct access and allowing access through controlled methods.

In Java, encapsulation is usually achieved using:

- `private` variables
- `public` getter methods
- `public` setter methods

---

# Real-World Example

Think about an ATM machine.

You can:

- Check balance
- Withdraw money
- Deposit money

But you cannot directly access or change the bank's internal database.

The internal data is hidden and controlled through specific operations.

This is encapsulation.

---

# Why Do We Need Encapsulation?

Without encapsulation:

```java
account.balance = -50000;
```

Anyone can set an invalid balance.

With encapsulation:

```java
account.setBalance(50000);
```

The program can validate the value before updating it.

---

# How to Achieve Encapsulation

Follow these steps:

1. Declare variables as `private`.
2. Create public getter methods to read values.
3. Create public setter methods to update values.

---

# Syntax

```java
class ClassName
{
    private dataType variableName;

    public dataType getVariableName()
    {
        return variableName;
    }

    public void setVariableName(dataType variableName)
    {
        this.variableName = variableName;
    }
}
```

---

# Example 1: Basic Encapsulation

```java
class Student
{
    private String name;

    public void setName(String name)
    {
        this.name = name;
    }

    public String getName()
    {
        return name;
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Student student = new Student();

        student.setName("Ragavarshini");

        System.out.println(student.getName());
    }
}
```

### Output

```text
Ragavarshini
```

---

# Explanation

```java
private String name;
```

The `name` variable cannot be accessed directly outside the class.

```java
student.name = "Ragavarshini";
```

This will cause an error.

Instead, use:

```java
student.setName("Ragavarshini");
```

To read the value:

```java
student.getName();
```

---

# Getter Method

A getter method is used to read a private variable.

Example:

```java
public String getName()
{
    return name;
}
```

---

# Setter Method

A setter method is used to update a private variable.

Example:

```java
public void setName(String name)
{
    this.name = name;
}
```

---

# Example 2: Student Details

```java
class Student
{
    private String name;
    private int rollNumber;
    private String department;

    public void setName(String name)
    {
        this.name = name;
    }

    public void setRollNumber(int rollNumber)
    {
        this.rollNumber = rollNumber;
    }

    public void setDepartment(String department)
    {
        this.department = department;
    }

    public String getName()
    {
        return name;
    }

    public int getRollNumber()
    {
        return rollNumber;
    }

    public String getDepartment()
    {
        return department;
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Student student = new Student();

        student.setName("Ragavarshini");
        student.setRollNumber(101);
        student.setDepartment("AI & DS");

        System.out.println("Name: " + student.getName());
        System.out.println("Roll Number: " + student.getRollNumber());
        System.out.println("Department: " + student.getDepartment());
    }
}
```

### Output

```text
Name: Ragavarshini
Roll Number: 101
Department: AI & DS
```

---

# Real-World Scenario 1: Banking System

A bank should not allow a negative balance.

```java
class BankAccount
{
    private String customerName;
    private double balance;

    public void setCustomerName(String customerName)
    {
        this.customerName = customerName;
    }

    public String getCustomerName()
    {
        return customerName;
    }

    public void setBalance(double balance)
    {
        if(balance >= 0)
        {
            this.balance = balance;
        }
        else
        {
            System.out.println("Invalid Balance");
        }
    }

    public double getBalance()
    {
        return balance;
    }
}

public class Main
{
    public static void main(String[] args)
    {
        BankAccount account = new BankAccount();

        account.setCustomerName("Rahul");
        account.setBalance(50000);

        System.out.println("Customer: " + account.getCustomerName());
        System.out.println("Balance: ₹" + account.getBalance());
    }
}
```

### Output

```text
Customer: Rahul
Balance: ₹50000.0
```

---

# Real-World Scenario 2: Employee Salary

```java
class Employee
{
    private String employeeName;
    private double salary;

    public void setEmployeeName(String employeeName)
    {
        this.employeeName = employeeName;
    }

    public String getEmployeeName()
    {
        return employeeName;
    }

    public void setSalary(double salary)
    {
        if(salary > 0)
        {
            this.salary = salary;
        }
        else
        {
            System.out.println("Salary must be greater than zero");
        }
    }

    public double getSalary()
    {
        return salary;
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Employee employee = new Employee();

        employee.setEmployeeName("Alice");
        employee.setSalary(45000);

        System.out.println("Employee: " + employee.getEmployeeName());
        System.out.println("Salary: ₹" + employee.getSalary());
    }
}
```

---

# Real-World Scenario 3: Login System

Passwords should not be displayed directly.

```java
class User
{
    private String username;
    private String password;

    public void setUsername(String username)
    {
        this.username = username;
    }

    public String getUsername()
    {
        return username;
    }

    public void setPassword(String password)
    {
        if(password.length() >= 8)
        {
            this.password = password;
        }
        else
        {
            System.out.println("Password must contain at least 8 characters");
        }
    }

    public boolean login(String enteredPassword)
    {
        return password.equals(enteredPassword);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        User user = new User();

        user.setUsername("ragavarshini");
        user.setPassword("Java1234");

        if(user.login("Java1234"))
        {
            System.out.println("Login Successful");
        }
        else
        {
            System.out.println("Invalid Password");
        }
    }
}
```

---

# Real-World Scenario 4: Product Price Validation

```java
class Product
{
    private String productName;
    private double price;

    public void setProductName(String productName)
    {
        this.productName = productName;
    }

    public String getProductName()
    {
        return productName;
    }

    public void setPrice(double price)
    {
        if(price > 0)
        {
            this.price = price;
        }
        else
        {
            System.out.println("Price must be greater than zero");
        }
    }

    public double getPrice()
    {
        return price;
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Product product = new Product();

        product.setProductName("Laptop");
        product.setPrice(65000);

        System.out.println("Product: " + product.getProductName());
        System.out.println("Price: ₹" + product.getPrice());
    }
}
```

---

# Advantages of Encapsulation

- Protects sensitive data
- Improves security
- Controls how data is updated
- Prevents invalid values
- Makes code easier to maintain
- Supports modular programming
- Improves flexibility

---

# Encapsulation vs Direct Access

| Direct Access | Encapsulation |
|---|---|
| Variables are public | Variables are private |
| No validation | Validation is possible |
| Less secure | More secure |
| Data can be changed by anyone | Data is controlled through methods |

---

# Common Mistakes

## Making Variables Public

❌ Incorrect:

```java
public double balance;
```

Anyone can modify it directly.

✅ Better:

```java
private double balance;
```

Use methods to control access.

---

## Setter Without Validation

❌ Weak design:

```java
public void setAge(int age)
{
    this.age = age;
}
```

Better:

```java
public void setAge(int age)
{
    if(age >= 0)
    {
        this.age = age;
    }
}
```

---

# Interview Questions

### What is Encapsulation?

Encapsulation is the process of wrapping data and methods into a single class and controlling access to data.

---

### How is Encapsulation achieved in Java?

Using private variables with public getter and setter methods.

---

### Why are variables declared private?

To prevent direct access and protect sensitive data.

---

### What is a getter method?

A method used to read a private variable.

---

### What is a setter method?

A method used to update a private variable.

---

### Is Encapsulation used for security?

Yes. It protects data by restricting direct access and allowing controlled updates.

---

# Challenge Exercises

### Challenge 1

Create a `Book` class with private variables:

- title
- author
- price

Create getter and setter methods.

---

### Challenge 2

Create a `BankAccount` class that does not allow negative balance.

---

### Challenge 3

Create an `Employee` class that does not allow salary less than zero.

---

### Challenge 4

Create a `Student` class that validates marks between 0 and 100.

---

### Challenge 5

Create a `User` class that validates password length before saving it.

---

# Summary

- Encapsulation protects data from direct access.
- Use `private` variables to hide data.
- Use getter methods to read values.
- Use setter methods to update values.
- Validation can be added inside setter methods.
- Encapsulation improves security and maintainability.

---

# Conclusion

Encapsulation is an important OOP concept used to protect data and control how it is accessed or modified. It is widely used in banking systems, login systems, employee management, shopping applications, and enterprise software. By using private variables with getter and setter methods, Java programs become safer, cleaner, and easier to maintain.
