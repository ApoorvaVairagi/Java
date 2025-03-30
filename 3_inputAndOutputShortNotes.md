## Input and Output

### Input
There are two ways to read an input from a user or a file: -
1. BufferedReader - is a simple class that is used to read a character or a sequence of characters. It has function read which reads a character, another read which reads an array of characters and a readline function which reads a line.
2. Scanner - advanced way. can read formatted inputs. It has different functions for differnt types of datatypes, a function to read an integer, function to read character and other datatypes as well. 


BufferedReader Example 
```java
import java.io.*;
class Test{
    public static void main(String[] args){
        BufferredReader br = new BufferredReader(new InputStreamReader(System.in));
        System.out.println("Enter a String");
        String s = br.readLine();
        System.out.println("You entered" + s);
    }
}
```
System.in -> is a input stream. That gives you a stream of bytes.
InputStreamReader -> Converts this stream of byte into a stream of character. Characters are 2 byte in java.
Bufferedreader -> expects a stream of character to read data from.

Bufferedreader to read an integer
```java
import java.io.*;
class Test{
    public static void main(String[] args) throws IOException{
        BufferredReader br = new BufferredReader(new InputStreamReader(System.in));
        System.out.println("Enter an Integer");
        int i = Integer.parseInt(br.readline());
        System.out.println("You entered" + i);
    }
}
```

BufferedReader throws a checked exception.
Exceptions are some unwanted conditions that can happen while the code execution. You have to handle them by writing code.

This java.io.*  indicated that we want to use all the classes in IO package.
Packages in java are a way to organize your software, your classes contains the related functions and on the top of those classes you have packages.
Packages contains related classes together, and the best of java is the packages also define folder structure. java folder has io folder inside it and in that all the classes are defined.

Scanner Class -> Its much easier to use as compared to BufferedReader.

```java
import java.util.Scanner;
class test{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        String s = sc.readLine();
        System.out.println("You entered string" + s);
        int x = sc.nextInt();
        System.out.println("You entered integer" + x);
        float f = sc.nextInt();
        System.out.println("You entered float" + f);
    }
}
```

BufferedReader is genrally faster than Scanner.
Scanner does a lots of post processing for parsing the input. On the other hand BufferedReader only reads the character stream.
Also BufferedReader is more flexible you can specify the buffer size that you want to read at a time. BufferedReader also has larger buffer to read from as compared to Scanner.

These advantages of BufferedReader are only there if you want to read a large input.
BufferedReader is syncchronized, when you are using multiple threads than it should be preffred.

---
### Output

There are mainly four methods to produce something on the screen. The methods are:-
System.out.print()
System.out.println()
System.out.format() or System.out.printf()

The above to are same and below two are almost same.
1. print, prints your output without appending the new line and println appends a new line always.
These two are used for strings and numbers or there mixture. They are written to handle primitive also there are multiple versions which handles primitive types and then there are version that only handle string type.

2. Format function are useful for formatted output, when you have inputs like floating point numbers or dates or times. Especially used formatting numbers - floating points, date and times.

```java
class Test{
    public static void main(String[] args){
        int x=10, y=20;
        char z = 'G';
        String str = "GFG";
        System.out.println(x);
        System.out.println(x+y);
        System.out.println(x+" "+y);
        System.out.print(str+" ");
        System.out.print("Courses\n");
    }
}
```

The printf word is derived from the C language, and the syntax is also similar. The first parameter in this format function or printf is a format string, which contains some characters and some placeholders. And this placeholders are replaced by the value that are specified in the remaining parameters.

```java
class Test{
    public static void main(String[] args){
        int x=100, y=200;
        System.out.format("Value of x is %d\n", x); // %d is the palceholder of an integer, %c is a placeholder of a character, %s is a placeholder of a string, %f for floating point.
        float y = Math.PI;
        System.out.format("Value of PI = %.2f\n", y); // .2f is to print the 2 point values after the point.
        System.out.format("Value of PI = %5.2f\n", y); // .2f is same as above, this 5 represents that atleast five characters has to be printed. The point is also counted as a character.
        System.out.format("Value of PI = %05.2f\n", y); // if you specify the 0 it means do not fill the remaining character by space but rather with 0.
        System.out.printf("x = %d, y=%d", x, y);
    }
}
```

### Escape Sequence in java
How to print the below String in java?
Welcome to "Geeks"

The below line will cause compile time error: Expected ')'.
System.out.println("Welcome to "Geeks"");

To solve this problem we have escape sequences.
System.out.println("Welcome to \"Geeks\"");

\n will print the next line.
System.out.println("Hi, \nWelcome");

System.out.println("Let us use \ in the String");
Output: Error: illegal escape character

If you want to print the \ you have to write it like \\.

The valid escape sequences are: \t, \b, \n, \r, \f, \', \", \\.

```java

```