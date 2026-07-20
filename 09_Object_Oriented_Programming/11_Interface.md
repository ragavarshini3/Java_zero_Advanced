# Interface in Java

In the previous lesson, we learned about abstraction using abstract classes.

Java also provides another way to achieve abstraction called an **Interface**.

An interface is used when we want to define a set of rules that different classes must follow.

For example:

- Different payment methods must provide a payment process.
- Different vehicles must provide a start method.
- Different notification systems must provide a send method.
- Different login methods must provide authentication.

The implementation can be different, but the required behavior is common.

--- 

# What is an Interface?

An **Interface** is a blueprint that contains method declarations.

Classes that implement an interface must provide the implementation for its methods.

An interface is mainly used to achieve:

- Abstraction
- Multiple inheritance
- Loose coupling
- Standard rules for classes

---

# Real-World Example

Think of a remote control.

A remote control provides buttons such as:

```text
Power On
Power Off
Volume Up
Volume Down
```

Different TV brands may work differently internally, but they all follow the same remote-control actions.

Similarly, an interface defines common actions, and different classes implement them in their own way.

---

# Why Do We Need Interfaces?

Suppose an application supports different payment methods.

```text
Payment

↓

Card Payment
UPI Payment
Cash Payment
```

Every payment type must have a `pay()` method.

Instead of writing the same rule repeatedly, we create an interface.

```java
interface Payment
{
    void pay();
}
```

Now every payment class must implement `pay()`.

---

# Syntax of an Interface

```java
interface InterfaceName
{
    void methodName();
}
```

A class uses the `implements` keyword.

```java
class ClassName implements InterfaceName
{
    public void methodName()
    {
        // implementation
    }
}
```

---

# Basic Example

```java
interface Animal
{
    void sound();
}

class Dog implements Animal
{
    public void sound()
    {
        System.out.println("Dog barks");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Dog dog = new Dog();

        dog.sound();
    }
}
```

### Output

```text
Dog barks
```

---

# Important Rule: Methods Must Be Public

Interface methods are automatically:

```java
public abstract
```

Therefore, when implementing an interface method, it must be declared as `public`.

❌ Incorrect:

```java
class Dog implements Animal
{
    void sound()
    {
        System.out.println("Dog barks");
    }
}
```

✅ Correct:

```java
class Dog implements Animal
{
    public void sound()
    {
        System.out.println("Dog barks");
    }
}
```

---

# Interface Variables

Variables declared inside an interface are automatically:

```text
public static final
```

This means they are constants.

Example:

```java
interface College
{
    String COLLEGE_NAME = "KGISL Institute of Technology";
}
```

Usage:

```java
public class Main
{
    public static void main(String[] args)
    {
        System.out.println(College.COLLEGE_NAME);
    }
}
```

### Output

```text
KGISL Institute of Technology
```

---

# Example: Interface with Multiple Methods

```java
interface Vehicle
{
    void start();

    void stop();
}

class Car implements Vehicle
{
    public void start()
    {
        System.out.println("Car started");
    }

    public void stop()
    {
        System.out.println("Car stopped");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Car car = new Car();

        car.start();

        car.stop();
    }
}
```

### Output

```text
Car started
Car stopped
```

---

# Real-World Scenario 1: Payment System

```java
interface Payment
{
    void pay(double amount);
}

class CardPayment implements Payment
{
    public void pay(double amount)
    {
        System.out.println("Paid ₹" + amount + " using Card");
    }
}

class UpiPayment implements Payment
{
    public void pay(double amount)
    {
        System.out.println("Paid ₹" + amount + " using UPI");
    }
}

class CashPayment implements Payment
{
    public void pay(double amount)
    {
        System.out.println("Paid ₹" + amount + " using Cash");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Payment payment1 = new CardPayment();
        Payment payment2 = new UpiPayment();
        Payment payment3 = new CashPayment();

        payment1.pay(1500);
        payment2.pay(2500);
        payment3.pay(800);
    }
}
```

### Output

```text
Paid ₹1500.0 using Card
Paid ₹2500.0 using UPI
Paid ₹800.0 using Cash
```

---

# Real-World Scenario 2: Notification System

```java
interface Notification
{
    void send(String message);
}

class EmailNotification implements Notification
{
    public void send(String message)
    {
        System.out.println("Email sent: " + message);
    }
}

class SmsNotification implements Notification
{
    public void send(String message)
    {
        System.out.println("SMS sent: " + message);
    }
}

class PushNotification implements Notification
{
    public void send(String message)
    {
        System.out.println("Push notification sent: " + message);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Notification email = new EmailNotification();
        Notification sms = new SmsNotification();
        Notification push = new PushNotification();

        email.send("Your order has been confirmed");
        sms.send("Your OTP is 123456");
        push.send("New offer available");
    }
}
```

---

# Real-World Scenario 3: Login System

```java
interface Login
{
    boolean authenticate(String username, String password);
}

class AdminLogin implements Login
{
    public boolean authenticate(String username, String password)
    {
        return username.equals("admin") &&
               password.equals("admin123");
    }
}

class StudentLogin implements Login
{
    public boolean authenticate(String username, String password)
    {
        return username.equals("student") &&
               password.equals("student123");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Login admin = new AdminLogin();

        boolean result = admin.authenticate("admin", "admin123");

        System.out.println("Admin Login: " + result);
    }
}
```

---

# Real-World Scenario 4: Vehicle System

```java
interface Vehicle
{
    void start();

    void fuelType();
}

class Car implements Vehicle
{
    public void start()
    {
        System.out.println("Car starts using a button");
    }

    public void fuelType()
    {
        System.out.println("Car uses petrol or diesel");
    }
}

class ElectricCar implements Vehicle
{
    public void start()
    {
        System.out.println("Electric car starts silently");
    }

    public void fuelType()
    {
        System.out.println("Electric car uses battery power");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Vehicle car = new Car();
        Vehicle electricCar = new ElectricCar();

        car.start();
        car.fuelType();

        electricCar.start();
        electricCar.fuelType();
    }
}
```

---

# Multiple Inheritance Using Interfaces

Java does not support multiple inheritance with classes.

❌ Not allowed:

```java
class Child extends Parent1, Parent2
{
}
```

But Java supports multiple inheritance using interfaces.

```java
interface Camera
{
    void takePhoto();
}

interface MusicPlayer
{
    void playMusic();
}

class SmartPhone implements Camera, MusicPlayer
{
    public void takePhoto()
    {
        System.out.println("Photo captured");
    }

    public void playMusic()
    {
        System.out.println("Music playing");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        SmartPhone phone = new SmartPhone();

        phone.takePhoto();

        phone.playMusic();
    }
}
```

### Output

```text
Photo captured
Music playing
```

---

# Interface vs Abstract Class

| Interface | Abstract Class |
|---|---|
| Uses `interface` keyword | Uses `abstract class` |
| Uses `implements` keyword | Uses `extends` keyword |
| Supports multiple inheritance | Does not support multiple class inheritance |
| Methods are public by default | Methods can have any access modifier |
| Variables are constants | Variables can be normal instance variables |
| Used to define rules | Used to share common code and behavior |

---

# Default Methods in Interfaces

Java 8 introduced default methods.

A default method has a body inside an interface.

```java
interface Vehicle
{
    void start();

    default void stop()
    {
        System.out.println("Vehicle stopped");
    }
}

class Car implements Vehicle
{
    public void start()
    {
        System.out.println("Car started");
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Car car = new Car();

        car.start();

        car.stop();
    }
}
```

### Output

```text
Car started
Vehicle stopped
```

---

# Static Methods in Interfaces

Interfaces can also contain static methods.

```java
interface Calculator
{
    static int add(int a, int b)
    {
        return a + b;
    }
}

public class Main
{
    public static void main(String[] args)
    {
        System.out.println(Calculator.add(10, 20));
    }
}
```

### Output

```text
30
```

---

# Common Mistakes

## Forgetting to Implement All Methods

```java
interface Vehicle
{
    void start();
    void stop();
}

class Car implements Vehicle
{
    public void start()
    {
        System.out.println("Car started");
    }

    // Error: stop() is not implemented
}
```

A class must implement all interface methods unless the class is declared `abstract`.

---

## Using `extends` Instead of `implements`

❌ Incorrect:

```java
class Dog extends Animal
{
}
```

When `Animal` is an interface, use:

```java
class Dog implements Animal
{
}
```

---

## Trying to Create an Interface Object

❌ Incorrect:

```java
Payment payment = new Payment();
```

Interfaces cannot be instantiated directly.

Correct:

```java
Payment payment = new UpiPayment();
```

---

# Advantages of Interfaces

- Achieves abstraction
- Supports multiple inheritance
- Reduces dependency between classes
- Improves flexibility
- Makes code easier to test
- Defines common rules
- Supports scalable application design

---

# Real-World Applications

Interfaces are widely used in:

- Payment Gateways
- Notification Services
- Authentication Systems
- Database Connections
- Spring Boot Applications
- Android Development
- Web Applications
- Microservices
- AI Applications
- Enterprise Software

---

# Interview Questions

### What is an interface?

An interface is a blueprint that defines method declarations which implementing classes must provide.

---

### Which keyword is used to implement an interface?

```java
implements
```

---

### Can we create an object of an interface?

No.

---

### Can an interface have variables?

Yes. They are automatically `public static final`.

---

### Can an interface have methods with a body?

Yes. It can have `default` and `static` methods.

---

### Does Java support multiple inheritance?

Java supports multiple inheritance through interfaces.

---

### What is the difference between an interface and an abstract class?

An interface defines rules and supports multiple inheritance. An abstract class can share common code and state.

---

# Challenge Exercises

### Challenge 1

Create a `Payment` interface with a `pay()` method.

Implement it using Card, UPI, and Cash payment classes.

---

### Challenge 2

Create a `Vehicle` interface with `start()` and `stop()` methods.

Implement it using Car and Bike classes.

---

### Challenge 3

Create a `Notification` interface with a `send()` method.

Implement it using Email, SMS, and Push Notification classes.

---

### Challenge 4

Create two interfaces:

- `Camera`
- `MusicPlayer`

Create a `SmartPhone` class that implements both.

---

### Challenge 5

Create a `Login` interface and implement Admin Login and Student Login classes.

---

# Summary

- An interface defines a set of rules for classes.
- Classes use `implements` to implement an interface.
- Interface methods are public and abstract by default.
- Interface variables are public, static, and final by default.
- Interfaces support multiple inheritance.
- Java 8 introduced default and static methods in interfaces.
- Interfaces are widely used for abstraction and loose coupling.

---

# Conclusion

Interfaces are an important Java feature used to define common behavior across different classes. They support abstraction, multiple inheritance, and flexible software design. Interfaces are heavily used in real-world Java applications such as payment systems, authentication modules, notification services, database layers, Android apps, Spring Boot applications, and enterprise software.
