## Variables and Primitive datatypes

Variable is a way to store and use the data.
To represent different type of data we have different data types.

```java
class Test{
    public static void main(String [] args){
        int age = 32;
        String name = "Sandeep";
        float weight = 70.5;
        System.out.println(age);
        System.out.println(name);
        System.out.println(weight);
    }
}

```

In Java, we have to specify the datatype of a variable before using it. In python, its not necessary.

Java, C++, C are called Statically typed languages.
Python is called dynamically typed languages.

Statically typed languages are faster.

### Variable Naming Convention

a-z, A-Z, _, $, 0-9 -> These are allowed in vairable naming.

But, the variable name cannot start with numerics.

Valid names - ab, AB, aBC, a1, a12, _a, a_b, ab$, $a

Invalid names - a3, a!, else, do, 1ab

Constant -> final int MAX_AGE = 200;
final int MAX_PLAYERS = 20;

### Types of Variables

Primitive - int, char, float, double
Non-Primitive - Object of classes. Array is also an object in Java.

### Primitive datatypes

| Datatype | Details |
|----------|---------|
| Boolean  | true or false |
| Byte     | -128 to 127 or -2^7 to 2^7 -1 (1 bit for sign, remaining 7 bits for values up to -2^7 to 2^7 -1 including 0. Negative numbers are stored in 2's complement representation.) |
| Short    | -32768 to 32767 (or -2^15 to 2^15 -1)  |
| Int      | -2147483648 to 2147483647 (or -2^31 to 2^31 -1) |
| Long     |  -2^63 to 2^63 -1 |
| Float    | Single precision 32 bit |
| Double   | Double precision 32 bit |
| Char     | 16 but unicode characters ('\u000' to '\uffff')

---

```java
class Test{
    public static void main(String[] args){
        bool isValid = true;
        byte marks = 90;
        float pi = 3.14;
        float div = 15.0f/4.0f;
        long view = 10000000000;
        char gender = 'M';
    }
}
```

### Non-Primitive datatypes
Non-primitve datatypes are the classe, can be user defined or pre-defined class.
We create variable of non-primitve datatype by using new operator, we access the members of the non-primitve datatype by using . operator.

```java
class Point{
    int x;
    int y;
}

class Test{
    public static void main(String[] args){
        Point p1 = new Point();
        p1.x = 10;
        p1.y = 20;
        Point p2 = p1;
        System.out.println(p1.x);
        System.out.println(p2.x);
    }
}
```
### Primitive VS Non-Primitive datatypes

1. Non-primitive types are always refernces.
It holds the memory location where the values are stored. eg. p1 and p2 are refering to the same memory location,it means if you change p2.x as 30 it will also be refelected for p1.
non-primitive are stored in heap and primitives in the stack.
Non-primitive types are dynamic

If you do not initialize the value of non-primitive tyopes they got default values.

3. Member of non-primitive types get default value, for primitive types they give a compile error if not initialized. 

---

### Wrapper Classes

In java, every primitive datatype have a non-primitive type.
There are built in classes in java where such class for primitive type.

What is the need of Wrapper classes?
The datatype implemenetation is not very clean in java, if we compare it to python, in it every variable is a reference. And if your programming language is a oop language you would like to dela with objects only. And thats why we have Wrapper classes.
eg. Generics, in this datatype is passed as an argument and you can create your object of particular datatype, whole java collection(ArrayList, Stack) framework are generics based and they expect a object to be there.

Why having primitive type than?
To keep the legacy of C,C++. Also to simply create the variables without more space complexity.

---

### Autoboxing and Unboxing

Concept related to the Wrapper classes.


```java
class Test{
    public static void main(String[] args){
        int x1 = 10;
        Integer x2 = x1;    //Autoboxing
        int x3 = x2;    //Auto-Unboxing
        System.out.println(x1);
        System.out.println(x2);
        System.out.println(x3);
    }
}
```


```java
class Test{
    public static void main(String[] args){
        Integer x1=400, x2=400;
        if(x1==x2){
            System.out.println("Same");
        }
        else{
            System.out.println("Not Same");
        }
    }
}
```
output -> Not Same
As these both are two different objects, but java works strangly in some cases if you have a smaller value the Output can be same the reason for that is, Java caches some literals. What can happen in case of smaller value is it caches the value and when you create more refernce to the value, instead of creating a new object, it makes those reference to the same literal.

### Type Conversion

Primitive type Conversion
Widening or Implicit Conversion

byte -> short -> int -> long -> float -> double
You might loose the precision from long to float, but float can store more than long.


Narrowing or Explicit Conversion

High chances of lossing data, can not be done implicitly this has to be done.

```java
double d = 65.4;
int i = (int)d;
char c = (char)i;
System.out.println(i);
System.out.println(c);
```
Output -> 
65
A