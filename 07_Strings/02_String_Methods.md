# String Methods in Java

Strings are one of the most frequently used objects in Java.

Java provides many built-in methods that make it easy to manipulate, search, compare, and modify Strings.

Instead of writing complex logic, developers can use these methods to perform common string operations efficiently.

---

# Why Do We Need String Methods?

Imagine an online shopping application.

A customer searches for:

```
Laptop
```

The application needs to:

- Check the length of the text.
- Convert it to uppercase.
- Remove unwanted spaces.
- Compare it with stored product names.
- Split keywords.
- Replace words.
- Search for specific characters.

Java String methods make these operations simple.

---

# Commonly Used String Methods

```text
length()
charAt()
substring()
indexOf()
lastIndexOf()
contains()
equals()
equalsIgnoreCase()
startsWith()
endsWith()
toUpperCase()
toLowerCase()
trim()
replace()
replaceAll()
split()
concat()
isEmpty()
compareTo()
compareToIgnoreCase()
```

---

# 1. length()

Returns the number of characters in a String.

## Syntax

```java
string.length();
```

## Example

```java
public class LengthExample {

    public static void main(String[] args) {

        String language = "Java Programming";

        System.out.println(language.length());

    }

}
```

### Output

```text
16
```

---

# Real-World Scenario

A password must contain at least 8 characters.

```java
String password = "OpenAI123";

if(password.length() >= 8)
{
    System.out.println("Valid Password");
}
```

---

# 2. charAt()

Returns the character at a specified index.

## Syntax

```java
string.charAt(index);
```

## Example

```java
String language = "Java";

System.out.println(language.charAt(2));
```

### Output

```text
v
```

---

# Real-World Scenario

Display the first letter of a customer's name.

```java
String customer = "Ragavarshini";

System.out.println(customer.charAt(0));
```

Output

```text
R
```

---

# 3. substring()

Extracts part of a String.

## Syntax

```java
substring(startIndex)

substring(startIndex,endIndex)
```

## Example

```java
String text = "Programming";

System.out.println(text.substring(3));
```

Output

```text
gramming
```

---

```java
System.out.println(text.substring(0,7));
```

Output

```text
Program
```

---

# Real-World Scenario

Extract the domain from an email.

```java
String email = "user@gmail.com";

System.out.println(email.substring(5));
```

Output

```text
gmail.com
```

---

# 4. indexOf()

Returns the first occurrence of a character or String.

```java
String language = "Programming";

System.out.println(language.indexOf('g'));
```

Output

```text
3
```

---

# Real-World Scenario

Find the position of '@' in an email.

```java
String email = "abc@gmail.com";

System.out.println(email.indexOf('@'));
```

---

# 5. lastIndexOf()

Returns the last occurrence.

```java
String text = "Java Programming";

System.out.println(text.lastIndexOf('a'));
```

Output

```text
13
```

---

# 6. contains()

Checks whether a String contains another String.

```java
String sentence = "Java is powerful";

System.out.println(sentence.contains("power"));
```

Output

```text
true
```

---

# Real-World Scenario

Search product names.

```java
String product = "Gaming Laptop";

if(product.contains("Laptop"))
{
    System.out.println("Product Found");
}
```

---

# 7. equals()

Compares String contents.

```java
String s1 = "Java";
String s2 = "Java";

System.out.println(s1.equals(s2));
```

Output

```text
true
```

---

# 8. equalsIgnoreCase()

Ignores uppercase/lowercase differences.

```java
String username = "Admin";

System.out.println(username.equalsIgnoreCase("admin"));
```

Output

```text
true
```

---

# Real-World Scenario

Login system.

```java
String entered = "ADMIN";

if(entered.equalsIgnoreCase("admin"))
{
    System.out.println("Login Successful");
}
```

---

# 9. startsWith()

Checks the beginning of a String.

```java
String website = "https://openai.com";

System.out.println(website.startsWith("https"));
```

Output

```text
true
```

---

# 10. endsWith()

Checks the ending.

```java
String file = "resume.pdf";

System.out.println(file.endsWith(".pdf"));
```

Output

```text
true
```

---

# Real-World Scenario

Check uploaded file type.

```java
String fileName = "photo.jpg";

if(fileName.endsWith(".jpg"))
{
    System.out.println("Image File");
}
```

---

# 11. toUpperCase()

Converts to uppercase.

```java
String language = "java";

System.out.println(language.toUpperCase());
```

Output

```text
JAVA
```

---

# 12. toLowerCase()

```java
String language = "JAVA";

System.out.println(language.toLowerCase());
```

Output

```text
java
```

---

# Real-World Scenario

Search systems convert user input to lowercase before comparison.

---

# 13. trim()

Removes spaces from beginning and end.

```java
String text = "   Java   ";

System.out.println(text.trim());
```

Output

```text
Java
```

---

# Real-World Scenario

User accidentally enters spaces while logging in.

---

# 14. replace()

Replaces characters or words.

```java
String text = "I like Java";

System.out.println(text.replace("Java","Python"));
```

Output

```text
I like Python
```

---

# 15. replaceAll()

Uses regular expressions.

```java
String text = "abc123xyz";

System.out.println(text.replaceAll("[0-9]",""));
```

Output

```text
abcxyz
```

---

# 16. split()

Splits a String.

```java
String fruits = "Apple,Banana,Mango";

String[] array = fruits.split(",");

for(String fruit : array)
{
    System.out.println(fruit);
}
```

Output

```text
Apple
Banana
Mango
```

---

# Real-World Scenario

Reading CSV files.

---

# 17. concat()

Joins Strings.

```java
String first = "Java";

String second = " Programming";

System.out.println(first.concat(second));
```

Output

```text
Java Programming
```

---

# 18. isEmpty()

Checks whether a String is empty.

```java
String text = "";

System.out.println(text.isEmpty());
```

Output

```text
true
```

---

# Real-World Scenario

Validate registration forms.

---

# 19. compareTo()

Compares alphabetically.

```java
String a = "Apple";
String b = "Banana";

System.out.println(a.compareTo(b));
```

Output

```text
Negative Value
```

---

# 20. compareToIgnoreCase()

Ignores uppercase/lowercase.

```java
String a = "JAVA";
String b = "java";

System.out.println(a.compareToIgnoreCase(b));
```

Output

```text
0
```

---

# Mini Project: User Registration Validation

```java
public class Registration {

    public static void main(String[] args) {

        String username = " Ragavarshini ";

        username = username.trim();

        if(username.length() >= 5)
        {
            System.out.println("Valid Username");
        }

        System.out.println(username.toUpperCase());

    }

}
```

Output

```text
Valid Username
RAGAVARSHINI
```

---

# Real-World Applications

String methods are used in:

- Login Systems
- Banking Applications
- Email Validation
- Search Engines
- Chat Applications
- File Handling
- Student Management Systems
- Inventory Systems
- Data Cleaning
- Web Development

---

# Common Mistakes

### Forgetting String Immutability

❌

```java
String text = "java";

text.toUpperCase();

System.out.println(text);
```

Output

```text
java
```

---

✅ Correct

```java
text = text.toUpperCase();

System.out.println(text);
```

Output

```text
JAVA
```

---

# Challenge Exercises

### Challenge 1

Accept a user's name and display its length.

---

### Challenge 2

Display the first and last character.

---

### Challenge 3

Convert a sentence to uppercase.

---

### Challenge 4

Replace all spaces with underscores.

---

### Challenge 5

Split a comma-separated list of subjects.

---

### Challenge 6

Check whether an email contains '@'.

---

### Challenge 7

Check whether a filename ends with ".pdf".

---

### Challenge 8

Compare two usernames ignoring case.

---

### Challenge 9

Extract the domain from an email address.

---

### Challenge 10

Remove leading and trailing spaces from user input.

---

# Summary

- Java provides many built-in String methods.
- String methods simplify text processing.
- They are used for searching, comparing, extracting, replacing, splitting, and validating text.
- String methods are heavily used in almost every Java application.

---

# Conclusion

String methods are among the most powerful features of Java. They allow developers to efficiently process textual data with minimal code. Mastering these methods is essential for building real-world applications such as login systems, search engines, banking software, web applications, and data processing tools.
