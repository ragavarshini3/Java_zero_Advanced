# String Manipulation Problems in Java

String manipulation is one of the most important topics in Java. Almost every software application processes text in some form, such as usernames, passwords, emails, search queries, file names, and messages. 

Practicing string problems helps improve logical thinking and prepares you for coding interviews.

---

# Basic String Problems 

These problems help you understand fundamental string operations.

---

# Problem 1: Reverse a String

## Problem Statement

Write a Java program to reverse a given string.

### Input

```text
Java
```

### Output

```text
avaJ
```

### Solution

```java
public class ReverseString {

    public static void main(String[] args) {

        String text = "Java";

        for(int i = text.length() - 1; i >= 0; i--)
        {
            System.out.print(text.charAt(i));
        }

    }

}
```

### Explanation

The loop starts from the last character and prints each character until the first character.

---

# Problem 2: Check Palindrome

## Problem Statement

Check whether a given string is a palindrome.

A palindrome reads the same forward and backward.

### Input

```text
madam
```

### Output

```text
Palindrome
```

### Solution

```java
public class Palindrome {

    public static void main(String[] args) {

        String text = "madam";

        String reverse = "";

        for(int i = text.length()-1; i>=0; i--)
        {
            reverse += text.charAt(i);
        }

        if(text.equals(reverse))
        {
            System.out.println("Palindrome");
        }
        else
        {
            System.out.println("Not Palindrome");
        }

    }

}
```

### Real-World Scenario

Used in puzzle games and interview coding questions.

---

# Problem 3: Count Vowels

## Problem Statement

Count the number of vowels in a string.

### Input

```text
Programming
```

### Output

```text
3
```

### Solution

```java
public class CountVowels {

    public static void main(String[] args) {

        String text = "Programming";

        int count = 0;

        text = text.toLowerCase();

        for(int i = 0; i < text.length(); i++)
        {
            char ch = text.charAt(i);

            if(ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u')
            {
                count++;
            }
        }

        System.out.println("Vowels = " + count);

    }

}
```

### Real-World Scenario

Useful in text analysis and language processing.

---

# Problem 4: Count Words

## Problem Statement

Count the number of words in a sentence.

### Input

```text
Java is easy to learn
```

### Output

```text
5
```

### Solution

```java
public class CountWords {

    public static void main(String[] args) {

        String sentence = "Java is easy to learn";

        String[] words = sentence.split(" ");

        System.out.println("Words = " + words.length);

    }

}
```

### Real-World Scenario

Used in document editors and blogging platforms.

---

# Problem 5: Remove Spaces

## Problem Statement

Remove all spaces from a string.

### Input

```text
Java Programming
```

### Output

```text
JavaProgramming
```

### Solution

```java
public class RemoveSpaces {

    public static void main(String[] args) {

        String text = "Java Programming";

        text = text.replace(" ", "");

        System.out.println(text);

    }

}
```

### Real-World Scenario

Useful when validating usernames or processing user input.

---

# Advanced String Problems

These problems are commonly asked in coding interviews.

---

# Problem 6: Check Anagram

## Problem Statement

Check whether two strings are anagrams.

Two strings are anagrams if they contain the same characters in a different order.

### Input

```text
listen
silent
```

### Output

```text
Anagram
```

### Solution

```java
import java.util.Arrays;

public class Anagram {

    public static void main(String[] args) {

        String s1 = "listen";
        String s2 = "silent";

        char[] a = s1.toCharArray();
        char[] b = s2.toCharArray();

        Arrays.sort(a);
        Arrays.sort(b);

        if(Arrays.equals(a,b))
        {
            System.out.println("Anagram");
        }
        else
        {
            System.out.println("Not Anagram");
        }

    }

}
```

### Real-World Scenario

Used in word games and search engines.

---

# Problem 7: Character Frequency

## Problem Statement

Find the frequency of every character in a string.

### Input

```text
banana
```

### Output

```text
b = 1
a = 3
n = 2
```

### Solution

```java
public class Frequency {

    public static void main(String[] args) {

        String text = "banana";

        int[] freq = new int[256];

        for(int i = 0; i < text.length(); i++)
        {
            freq[text.charAt(i)]++;
        }

        for(int i = 0; i < freq.length; i++)
        {
            if(freq[i] > 0)
            {
                System.out.println((char)i + " = " + freq[i]);
            }
        }

    }

}
```

---

# Problem 8: Remove Duplicate Characters

## Problem Statement

Remove duplicate characters from a string.

### Input

```text
programming
```

### Output

```text
progamin
```

### Solution

```java
public class RemoveDuplicate {

    public static void main(String[] args) {

        String text = "programming";

        String result = "";

        for(int i = 0; i < text.length(); i++)
        {
            char ch = text.charAt(i);

            if(result.indexOf(ch) == -1)
            {
                result += ch;
            }
        }

        System.out.println(result);

    }

}
```

### Real-World Scenario

Useful in data cleaning and preprocessing.

---

# Problem 9: Longest Word

## Problem Statement

Find the longest word in a sentence.

### Input

```text
Java programming language
```

### Output

```text
programming
```

### Solution

```java
public class LongestWord {

    public static void main(String[] args) {

        String sentence = "Java programming language";

        String[] words = sentence.split(" ");

        String longest = "";

        for(String word : words)
        {
            if(word.length() > longest.length())
            {
                longest = word;
            }
        }

        System.out.println(longest);

    }

}
```

### Real-World Scenario

Used in document analysis and NLP applications.

---

# Problem 10: Capitalize Every Word

## Problem Statement

Capitalize the first letter of every word.

### Input

```text
java programming language
```

### Output

```text
Java Programming Language
```

### Solution

```java
public class CapitalizeWords {

    public static void main(String[] args) {

        String sentence = "java programming language";

        String[] words = sentence.split(" ");

        String result = "";

        for(String word : words)
        {
            result += Character.toUpperCase(word.charAt(0))
                    + word.substring(1) + " ";
        }

        System.out.println(result.trim());

    }

}
```

### Real-World Scenario

Used in report generation, document formatting, and content management systems.

---

# Practice Challenges

Try solving these without referring to the solutions.

1. Reverse each word in a sentence.
2. Count consonants in a string.
3. Check whether two strings are rotations of each other.
4. Find the first non-repeating character.
5. Find the first repeating character.
6. Reverse the order of words in a sentence.
7. Check whether a string contains only digits.
8. Count uppercase and lowercase letters separately.
9. Find the shortest word in a sentence.
10. Compress a string (Example: `aaabbcc → a3b2c2`).

---

# Summary

* Basic problems help you understand String traversal and manipulation.
* Advanced problems improve logical thinking and interview preparation.
* These problems use important Java concepts like loops, arrays, methods, and built-in String functions.

---

# Conclusion

Mastering String manipulation is essential for Java programming and technical interviews. These problems cover the most commonly asked concepts and provide a strong foundation for advanced topics such as regular expressions, collections, and text processing.
