## String in Java

A string in Java is a sequence of characters stored using UTF-16 encoding, where every character occupies 16 bits. In Java, strings are immutable, meaning once created, their content cannot be changed once created.
 

Creating a String in Java
There are four ways to create a string in Java:

1. Using Character Array / ArrayList - Strings can be created by initializing a character array. For example:

char[] arr = ['g', 'e', 'e', 'k', 's'];

Here, each character of the string is stored in an array format.

2. Using the String Class - The String class creates immutable strings. Once a string is created, its content cannot be modified. Operations like concatenation or changing the case of a string will create a new string object.

String literal
String s = “GeeksforGeeks”;

A literal creates a string in the String Pool.

Using new keyword
String s = new String (“GeeksforGeeks”);

This explicitly creates a new string object in the heap memory.

3. StringBuffer Class - The StringBuffer class creates mutable strings and is thread-safe. It is suitable for multithreaded environments where multiple threads might access the same string object.

StringBuffer s = new StringBuffer("GeeksforGeeks");

With StringBuffer, you can append, insert, or modify the string.

4. StringBuilder Class - The StringBuilder class is similar to StringBuffer but is not thread-safe. It is used in single-threaded environments to avoid the performance overhead of synchronization.

StringBuilder s = new StringBuilder("GeeksforGeeks");

**Examples and Methods**
Here, we explore some key methods provided by the String class in Java along with examples.

- length() : This method returns the number of characters in the string.
- charAt() : The charAt() method returns the character at a specified index. Index starts from 0 (like arrays).
- str.substring(start): Returns the substring from the start index to the end of the string.
- str.substring(start, end) : Returns the substring from the start index to the end - 1 index.

Example:

```java
import java.io.*;

class GFG {
    public static void main (String[] args) {
        String str = "Geeks";
        System.out.println(str.length());
        System.out.println(str.charAt(3));
        System.out.println(str.substring(2));
        System.out.println(str.substring(2, 4));
    }
}
```
Output
5
k
eks
ek

**Create String Objects using String literals**

When strings are created using literals, Java optimizes memory usage by storing them in a String Pool. If two string literals have the same content, they share the same memory location in the pool. However, when strings are created using the new keyword, they are stored in the heap memory, and each object gets a separate memory allocation, even if they have the same content.

```java
import java.io.*;

class GFG {
    public static void main (String[] args) {
        // String creation using literals
        String s1 = "geek";
        String s2 = "geek";

        // Comparing string literals
        if (s1 == s2) 
            System.out.println("Yes");
        else
            System.out.println("No");

        // String creation using the new keyword
        String s3 = new String("geek");

        // Comparing literal with object created using 'new'
        if (s1 == s3) 
            System.out.println("Yes");
        else
            System.out.println("No");
    }
}
```

Output
Yes
No

**More functions on the String Class**

- contains() Method : The contains() method checks if a specific sequence of characters exists within a string. It returns true if the sequence is found, otherwise false.

```java
import java.io.*;

class GFG {
    public static void main (String[] args) {
        String s1 = "geeksforgeeks";
        String s2 = "geeks";

        // Check if s1 contains s2
        System.out.println(s1.contains(s2)); 
    }
}
```
Output
true

- equals() Method : The equals() method compares two strings for equality based on their content. It is case-sensitive.

```java
import java.io.*;

class GFG {
    public static void main (String[] args) {
        String s1 = "GeeksforGeeks";
        String s2 = "GeeksforGeeks";

        // Compare s1 and s2 for equality
        System.out.println(s1.equals(s2));  
    }
}
```
Output
true

- compareTo() Method : The compareTo() method compares two strings lexicographically:

* Returns 0 if both strings are equal.
* Returns a positive value if the first string is lexicographically greater.
* Returns a negative value if the first string is lexicographically smaller.

```java
import java.io.*;

class GFG {
    public static void main (String[] args) {
        String s1 = "geeksforgeeks";
        String s2 = "for";

        // Compare s1 and s2
        int res = s1.compareTo(s2);

        if (res == 0)
            System.out.println("Same");
        else if (res > 0)
            System.out.println("s1 Greater");
        else
            System.out.println("s1 Smaller");
    }
}
```
Output
s1 Greater

- indexOf() Method : The indexOf() method returns the starting index of the first occurrence of a specified substring within the string. If the substring is not found, it returns -1.

```java
import java.io.*;

class GFG {
    public static void main (String[] args) {
        String s1 = "geeksforgeeks";
        String s2 = "geek";

        // Find the starting index of s2 in s1
        System.out.println(s1.indexOf(s2));  
    }
}
```
Output
0

- String Concatenation : String concatenation is the process of joining two or more strings to form a single combined string. In Java, there are multiple ways to achieve string concatenation, including using the + operator and the concat() method.

```java
import java.io.*;

class GFG {
    public static void main (String[] args) {
       String s1 = "geeks";
        // s2 references the same object as s1
        String s2 = s1;  

        // Concatenating "forgeeks" to s1
        s1 = s1 + "forgeeks";  // OR s1 = s1.concat("forgeeks");

        System.out.println(s1);

        System.out.println(s1 == s2);
    }
}
```
Output
geeksforgeeks
false