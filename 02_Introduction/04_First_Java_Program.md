# First Java Program

Now that Java is installed, let's write and run our first Java program.

---

## Hello World Program

Create a file named `HelloWorld.java` and write the following code:

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

---

## Understanding the Program

### 1. Class Declaration

```java
public class HelloWorld
```

* `public` means the class can be accessed from anywhere.
* `class` is a keyword used to create a class.
* `HelloWorld` is the name of the class.

> The filename and class name must be the same.

---

### 2. Main Method

```java
public static void main(String[] args)
```

This is the entry point of every Java application.

* `public` → Accessible from anywhere.
* `static` → Can be called without creating an object.
* `void` → Does not return any value.
* `main()` → Method where program execution starts.
* `String[] args` → Stores command-line arguments.

---

### 3. Print Statement

```java
System.out.println("Hello, Java!");
```

Used to display output on the console.

---

## Compile the Program

Open Terminal or Command Prompt and navigate to the file location.

Run:

```bash
javac HelloWorld.java
```

If compilation is successful, a file named `HelloWorld.class` will be generated.

---

## Run the Program

Execute the program using:

```bash
java HelloWorld
```

---

## Output

```text
Hello, Java!
```

---

## Program Flow

```text
HelloWorld.java
        ↓
      javac
        ↓
HelloWorld.class
        ↓
       JVM
        ↓
      Output
```

---

## Common Errors

### Class Name and File Name Mismatch

❌ Incorrect:

```java
public class Test
```

File Name:

```text
HelloWorld.java
```

✅ Correct:

```java
public class HelloWorld
```

File Name:

```text
HelloWorld.java
```

---

### Missing Semicolon

❌

```java
System.out.println("Hello")
```

✅

```java
System.out.println("Hello");
```

---

## Key Points

* Every Java program starts execution from the `main()` method.
* Java source files use the `.java` extension.
* Compilation generates bytecode (`.class` file).
* The JVM executes the bytecode.

---

## Conclusion

The Hello World program is the first step in learning Java. It introduces the basic structure of a Java program, including classes, methods, and output statements.
