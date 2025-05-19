## Java Functions

A method is a collection of statements that perform specific task and return result to the caller. A method can perform some specific task without returning anything. Methods allow us to reuse the code without retyping the code. In Java, every method must be part of some class that is different from languages like C, C++, and Python. 

### Method in Java
#### Method Declaration

In general, method declarations have six components :

- **Modifier**: Defines access type of the method, i.e., from where it can be accessed in your application. In Java, there are 4 types of access specifiers:
  - **public**: Accessible in all classes in your application.
  - **protected**: Accessible within the class in which it is defined and in its subclass(es).
  - **private**: Accessible only within the class in which it is defined.
  - **default (declared/defined without using any modifier)**: Accessible within the same class and package within which its class is defined.


- **The return type**: The data type of the value returned by the method or void if does not return a value.
- **Method Name**: The rules for field names apply to method names as well, but the convention is a little different.
- **Parameter list**: Comma-separated list of the input parameters is defined, preceded by their data type, within the enclosed parenthesis. If there are no parameters, you must use empty parentheses ().
- **Exception list**: The exceptions you expect by the method can throw, you can specify these exception(s).
- **Method body**: It is enclosed between braces. The code you need to be executed to perform your intended operations.
- **Method signature**: It consists of method name and parameter list (number of parameters, type of the parameters and order of the parameters). Return type and exceptions are not considered as part of it.


- Methods with Object References
When objects are passed as arguments, changes made inside the method affect the original object.

```java
// Java Program to show
// Methods with Object References
import java.math.*;
import java.io.*;
import java.util.*;

class Point {
    // Declaring two integer fields for x and y coordinates
    int x;
    int y;
}

public class Gfg { 
    public static void main(String[] args) { 
        // Creating a Point object
        Point p = new Point();
        
        // Assigning values to the coordinates
        p.x = 5; 
        p.y = 10;

        // Calling the fun method and passing the Point object
        fun(p);
        
        // Printing the updated coordinates of p
        System.out.println(p.x + " " + p.y);
    } 
    
    // fun method that modifies the fields of the passed Point object
    public static void fun(Point p) {
        // Modifying the fields of Point object p
        p.x = 10; 
        p.y = 10;
    }
}

```
Output
10 10
This example shows how methods can modify the state of objects passed as arguments.

- Passing Objects by Reference vs. Reassigning Objects
If an object reference is reassigned inside a method, it does not affect the original object.

```java
// Java Program to show
// Passing Objects by Reference vs. Reassigning Objects
import java.io.*;
import java.math.*;
import java.util.*;

class Point {
    // Declaring two integer fields for x and y coordinates
    int x;
    int y;
}

public class Gfg {
    public static void main(String[] args) {
        // Creating a Point object
        Point p = new Point();

        // Assigning values to the coordinates
        p.x = 5;
        p.y = 10;

        // Calling the fun method and passing the Point
        // object
        fun(p);

        // Printing the unchanged coordinates of p
        System.out.println(p.x + " " + p.y);
    }

    // fun method that creates a new Point object and
    // modifies it
    public static void fun(Point p) {
        // Creating a new Point object
        p = new Point();

        // Modifying the new Point object
        p.x = 10;
        p.y = 10;
    }
}
```
Output
5 10
In this case, the original object remains unchanged because the reassignment inside fun() only affects the local reference.

### Command Line Arguments in Java

Java command-line arguments are inputs passed to the program at the time of execution. These arguments are specified in the command line, and they can be received and processed by the Java program as input. The arguments are passed to the main() method as a string array.
To pass command-line arguments, they should be provided as space-separated values. Both strings and primitive data types (int, double, float, char, etc.) can be passed as arguments. Internally, these arguments are automatically converted into a string array by the JVM and passed to the main() function as the args[] parameter.

When command-line arguments are supplied to the JVM, they are wrapped into the args[] array. This can be verified by checking the length of the array using args.length. The JVM stores the first command-line argument at args[0], the second at args[1], the third at args[2], and so on.

Example:

```java
// Java Program to Check for Command Line Arguments

// Class
class GfG {

    // Main driver method
    public static void main(String[] args) {

        // Checking if length of args array is
        // greater than 0
        if (args.length > 0) {
            System.out.println("Arguments are");
          
            // Iterating the args array
            // using for each loop
            for (String x : args)
                // Printing command line arguments
                System.out.print(x + " ");
        }
        else {
            System.out.println("No Arguments");
        }
    }
}
```
Steps to Run the Above Program are:

Save the program as GfG.java.
Open the command prompt and navigate to the program's directory.
Compile the program:
javac GfG.java

Run the program with arguments:
java GfG arg1 arg2 arg3

Example:
java GfG Geeks at GeeksforGeeks

-----

- Q. First digit of a Number

public static int giveFirst(int n){
  while(n>10{
  n=n/10;
  }
  return n;
}

**Approch 2**
- To get the value of the power of 10 from which we have to divide the number.
  
public static int giveFirst(int n){
  double power = Math.log10(n);
  int p = (int)power;
  int a = Math.pow(10, p);
  int ans = n/a;
  return ans;
}

- Q. Prime Factorization.
We have to give the prime factors of a number.
Input - 50
Output - 2, 5, 5

Input - 20
Output - 2, 2, 5

Input - 13
Output - 13
