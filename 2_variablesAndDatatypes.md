## Variables in Java
A variable is a name given to a memory location. It is the basic unit of storage in a program.

The value stored in a variable can be changed during program execution.
A variable is only a name given to a memory location, all the operations done on the variable effects that memory location.
In Java, all the variables must be declared before use.

### Variable Naming
Java has specific rules and conventions for naming variables:

Rules
Variable names can include letters (a-z, A-Z), numbers (0-9), underscore (_), and dollar sign ($).
Variable names must not begin with a number.
Reserved keywords (e.g., else, for, while) cannot be used as variable names.

- Syntax of Valid Naming:

    int age; // A simple integer variable

    int _name; // An integer variable starting with an underscore

    double totalAmount; // A double variable for storing decimal values

    String dollar$sign; // A string variable with a dollar sign in the name


- Syntax of Invalid Naming:

    int 123abc; // starts with a number

    int a#name; // contains a disallowed character

    int else; // a reserved keyword


Data Types in Java
Data types are different sizes and values that can be stored in the variable that is made as per convenience and circumstances to cover up all test cases. Also, let us cover up other important ailments that there are majorly two types of languages that are as follows:

First, one is a Statically typed language where each variable and expression type is already known at compile time. Once a variable is declared to be of a certain data type, it cannot hold values of other data types. For example C, C++, and Java.
The other is Dynamically typed languages. These languages can receive different data types over time. For example Ruby, Python
Java is statically typed and also a strongly typed language because, in Java, each type of data (such as integer, character, hexadecimal, packed decimal, and so forth) is predefined as part of the programming language and all constants or variables defined for a given program must be described with one of the data types.

### char datatype

The char data type is a single 16-bit Unicode character.

You must be wondering why is the size of char 2 bytes in Java. 

So, other languages like C/C++ use only ASCII characters, and to represent all ASCII characters 8-bits is enough. But java uses the Unicode system not the ASCII code system and to represent the Unicode system 8 bits is not enough to represent all characters so java uses 2 bytes for characters. Unicode defines a fully international character set that can represent most of the world's written languages. It is a unification of dozens of character sets, such as Latin, Greek, Cyrillic, Katakana, Arabic, and many more.

### Non-Primitive Datatype

Non-primitive types in Java, also known as reference types, include classes, interfaces, and arrays. Unlike primitive types, which directly store values, non-primitive types store references to the memory location where the actual data is kept.

Reference Data Types
The Reference Data Types will contain a memory address of variable values because the reference types won’t store the variable value directly in memory. They are strings, objects, arrays, etc. 

1. A: Strings 
Strings are defined as an array of characters. The difference between a character array and a string in Java is, that the string is designed to hold a sequence of characters in a single variable whereas, a character array is a collection of separate char-type entities. Unlike C/C++, Java strings are not terminated with a null character.

    Syntax: Declaring a string

    <String_Type> <string_variable> = “<sequence_of_string>”;

    Example: 

    // Declare String without using new operator
    String s1 = "GeeksforGeeks";
    // Declare String using new operator
    String s2= new String("GeeksforGeeks");

2. B: Class
A class is a user-defined blueprint or prototype from which objects are created.  It represents the set of properties or methods that are common to all objects of one type. In general, class declarations can include these components, in order: 

    Modifiers: A class can be public or has default access. Refer to access specifiers for classes or interfaces in Java
    Class name: The name should begin with an initial letter (capitalized by convention).
    Superclass(if any): The name of the class's parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.
    Interfaces(if any): A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.
    Body: The class body is surrounded by braces, { }.

3. C: Object
It is a basic unit of Object-Oriented Programming and represents real-life entities.  A typical Java program creates many objects, which as you know, interact by invoking methods. An object consists of :

    State: It is represented by the attributes of an object. It also reflects the properties of an object.
    Behavior: It is represented by the methods of an object. It also reflects the response of an object to other objects.
    Identity: It gives a unique name to an object and enables one object to interact with other objects.

4. D: Interface
Like a class, an interface can have methods and variables, but the methods declared in an interface are by default abstract (only method signature, no body).   

    Interfaces specify what a class must do and not how. It is the blueprint of the class.
    An Interface is about capabilities like a Player may be an interface and any class implementing Player must be able to (or must implement) move(). So it specifies a set of methods that the class has to implement.
    If a class implements an interface and does not provide method bodies for all functions specified in the interface, then the class must be declared abstract.
    A Java library example is Comparator Interface. If a class implements this interface, then it can be used to sort a collection.
5. E: Array
An array is a group of like-typed variables that are referred to by a common name. Arrays in Java work differently than they do in C/C++. The following are some important points about Java arrays. 

    In Java, all arrays are dynamically allocated. (discussed below)
    Since arrays are objects in Java, we can find their length using member length. This is different from C/C++ where we find length using size.
    A Java array variable can also be declared like other variables with [] after the data type.
    The variables in the array are ordered and each has an index beginning from 0.
    Java array can also be used as a static field, a local variable, or a method parameter.
    The size of an array must be specified by an int value and not long or short.
    The direct superclass of an array type is Object.
    Every array type implements the interfaces Cloneable and java.io.Serializable.

### Wrapper Classes
A Wrapper class is a class whose object wraps or contains primitive data types. When we create an object to a wrapper class, it contains a field and in this field, we can store primitive data types. In other words, we can wrap a primitive value into a wrapper class object.

They convert primitive data types into objects. Objects are needed if we wish to modify the arguments passed into a method (because primitive types are passed by value).
The classes in java.util package handles only objects and hence wrapper classes help in this case also.
Data structures in the Collection framework, such as ArrayList and Vector, store only objects (reference types) and not primitive types.
An object is needed to support synchronization in multithreading.

### Autoboxing and Unboxing

Autoboxing refers to the conversion of a primitive value into an object of the corresponding wrapper class.
For example, converting int to Integer class. The Java compiler applies autoboxing when a primitive value is: 

Passed as a parameter to a method that expects an object of the corresponding wrapper class.
Assigned to a variable of the corresponding wrapper class.
Unboxing on the other hand refers to converting an object of a wrapper type to its corresponding primitive value. For example conversion of Integer to int. The Java compiler applies to unbox when an object of a wrapper class is: 

Passed as a parameter to a method that expects a value of the corresponding primitive type.
Assigned to a variable of the corresponding primitive type.

Example 1: Autoboxing and Unboxing

```java
// Java program to demonstrate Autoboxing and Unboxing

class GfG {
    public static void main(String[] args) {
        // Autoboxing: Converting int to Integer
        int x1 = 10;
        Integer x2 = x1; // Autoboxing

        // Unboxing: Converting Integer to int
        int x3 = x2; // Unboxing

        // Print values
        System.out.println("x1: " + x1);
        System.out.println("x2: " + x2);
        System.out.println("x3: " + x3);
    }
}
```

Output
x1: 10
x2: 10
x3: 10
 
Example 2: Comparison with Wrapper Classes

```java
// Java program to illustrate behavior with Wrapper Classes

class GfG {
    public static void main(String[] args) {
        Integer x1 = new Integer(10);
        Integer x2 = new Integer(10);

        if (x1 == x2) {
            System.out.println("Same");
        } else {
            System.out.println("Not Same");
        }

        // For small values (cached by Java)
        Integer y1 = 40;
        Integer y2 = 40;

        if (y1 == y2) {
            System.out.println("Same");
        } else {
            System.out.println("Not Same");
        }
    }
}
```

Output
Not Same
Same

### Type Conversion in Java

**Widening or Automatic Type Conversion**
Widening conversion takes place when two data types are automatically converted. This happens when:  

The two data types are compatible.
When we assign a value of a smaller data type to a bigger data type.
For Example, in java, the numeric data types are compatible with each other but no automatic conversion is supported from numeric type to char or boolean. Also, char and boolean are not compatible with each other. 

```java
// Java Program to Illustrate Automatic Type Conversion

// Main class
class GfG {

	// Main driver method
	public static void main(String[] args) {
		int i = 100;

		// Automatic type conversion
		// Integer to long type
		long l = i;

		// Automatic type conversion
		// long to float type
		float f = l;

		// Print and display commands
		System.out.println("Int value " + i);
		System.out.println("Long value " + l);
		System.out.println("Float value " + f);
	}
}
```

**Narrowing or Explicit Conversion**
If we want to assign a value of a larger data type to a smaller data type we perform explicit type casting or narrowing.  

This is useful for incompatible data types where automatic conversion cannot be done.
Here, the target type specifies the desired type to convert the specified value to.

```java
// Java program to illustrate Incompatible data Type
// for Explicit Type Conversion

// Main class
public class GfG {

	// Main driver method
	public static void main(String[] args) {

		// Declaring character variable
		char ch = 'c';
		// Declaring integer variable
		int num = 88;
		// Trying to insert integer to character
		ch = num;
	}
}
```
Output:

./GfG.java:15: error: incompatible types: possible lossy conversion from int to char
		ch = num;
		     ^
1 error


This error is generated as an integer variable takes 4 bytes while character datatype requires 2 bytes. We are trying to plot data from 4 bytes into 2 bytes which is not possible.

How to do Explicit Conversion? 

```java
// Java program to Illustrate Explicit Type Conversion

// Main class
public class GfG {

	// Main driver method
	public static void main(String[] args) {

		// Double datatype
		double d = 100.04;

		// Explicit type casting by forcefully getting
		// data from long datatype to integer type
		long l = (long)d;

		// Explicit type casting
		int i = (int)l;

		// Print statements
		System.out.println("Double value " + d);

		// While printing we will see that
		// fractional part lost
		System.out.println("Long value " + l);

		// While printing we will see that
		// fractional part lost
		System.out.println("Int value " + i);
	}
}
```

Output
Double value 100.04
Long value 100
Int value 100

Note:

While assigning value to byte type the fractional part is lost and is reduced to modulo 256 (range of byte). 

Example:
```java
// Java Program to Illustrate Conversion of
// Integer and Double to Byte

// Main class
class GfG {

	// Main driver method
	public static void main(String args[]) {
		// Declaring byte variable
		byte b;

		// Declaring and initializing integer and double
		int i = 257;
		double d = 323.142;

		// Display message
		System.out.println("Conversion of int to byte.");

		// i % 256
		b = (byte)i;

		// Print commands
		System.out.println("i = " + i + ", b = " + b);
		System.out.println(
			"\nConversion of double to byte.");

		// d % 256
		b = (byte)d;

		// Print commands
		System.out.println("d = " + d + ", b= " + b);
	}
}
```
Output
Conversion of int to byte.
i = 257, b = 1

Conversion of double to byte.
d = 323.142, b= 67

### Variable Scope

Loop Variables (Block Scope) 
A variable declared inside pair of brackets "{" and "}" in a method has scope within the brackets only.
```java
public class GfG {
    public static void main(String args[]) {
        {
            // The variable x has scope within
            // brackets
            int x = 10;
            System.out.println(x);
        }
        
        // Uncommenting below line would produce
        // error since variable x is out of scope.

        // System.out.println(x); 
    }
}
```
Output
10

As another example, consider the following program with a for loop. 
```java
class GfG {
    public static void main(String args[]) {
        for (int x = 0; x < 4; x++) {
            System.out.println(x);
        }

        // Will produce error
        System.out.println(x);
    }
}
```
Output: 

./GfG.java:8: error: cannot find symbol
        System.out.println(x);
                           ^
  symbol:   variable x
  location: class GfG
1 error

The right way of doing the above is, 
```java
// Above program after correcting the error
class GfG {
    public static void main(String args[]) {
        int x;
        for (x = 0; x < 4; x++) {
            System.out.println(x);
        }

       System.out.println(x);
    }
}
```
Output
0
1
2
3
4

Let's look at a tricky example of loop scope. Predict the output of the following program. You may be surprised if you are a regular C/C++ programmer. 
```java
class GfG {
    public static void main(String args[]) {
        int a = 5;
        for (int a = 0; a < 5; a++) {
            System.out.println(a);
        }
    }
}
```
Output :

./GfG.java:4: error: variable a is already defined in method main(String[])
        for (int a = 0; a < 5; a++) {
                 ^
1 error

Note:- In C++, it will run. But in java, it is an error because, in java, the name of the variable of the inner and outer loop must be different.
A similar program in C++ works. See this.

As an exercise, predict the output of the following Java program. 
```java
class GfG {
    public static void main(String args[]) {
        {
            int x = 5;
            {
                int x = 10;
                System.out.println(x);
            }
        }
    }
}
```
Output :-

./GfG.java:6: error: variable x is already defined in method main(String[])
                int x = 10;
                    ^
1 error
Q. From the above knowledge, tell whether the below code will run or not.
```java
class GfG {
    public static void main(String args[]) {
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
        }
        int i = 20;
        System.out.println(i);
    }
}
```
Output
1
2
3
4
5
6
7
8
9
10
20

Yes, it will run! 
See the program carefully, the inner loop will terminate before the outer loop variable is declared. So the inner loop variable is destroyed first and then the new variable of the same name has been created.

Some Important Points about Variable scope in Java:  

In general, a set of curly brackets { } defines a scope.
In Java, we can usually access a variable as long as it was defined within the same set of brackets as the code we are writing or within any curly brackets inside of the curly brackets where the variable was defined.
Any variable defined in a class outside of any method can be used by all member methods.
When a method has the same local variable as a member, "this" keyword can be used to reference the current class variable.
For a variable to be read after the termination of a loop, It must be declared before the body of the loop.