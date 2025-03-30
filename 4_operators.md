## Operators
### Arithmetic Operator
When you have more than one operator, you have precedence which decides which operator has to be performed first.

```java
class Test{
    public static void main(String[] args){
        int x = 10, y = 20;
        System.out.println(x+y);
        System.out.println(x*y);
        System.out.println(y/x);
        int z = (x+y*10);
        System.out.println(z);
        z = x++ // Unary operator -> z = x, x = x+1
        System.out.println(z);
        z = ++x; // Unary operator -> x = x+1, z = x
        System.out.println(z);
    }
}
```
---
### Assignment Operators
Assigning the value of a variable to another variable.

```java
class Test{
    public static void main(String[] args){
        int x = 10, y = 5, z;
        x += y; // x = x+y
        System.out.println(x);
        x %= y; // x = x%y
        System.out.println(x);
        z = x = y; // Right to left Associativity of assignment operator. (z = (x = y))
        System.out.println(z);
    }
}
```

Best way is to use bracket. This way your code is also readable by others as well.

---

### Ternary operator
Ternary operator is a shorthand version of the if-else statement. It has three operands and hence the name ternary.

The general format is:

**condition ? if true : if false**

The above statement means that if the condition evaluates to true, then execute the statements after the '?' else execute the statements after the ':'.

```java
// Java program to illustrate
// max of three numbers using
// ternary operator.
public class GfG {
    public static void main(String[] args) {
        int a = 20, b = 10, c = 30, result;

        // result holds max of three
        // numbers
        result
            = ((a > b) ? (a > c) ? a : c : (b > c) ? b : c);
        System.out.println("Max of three numbers = "
                           + result);
    }
}
```
---
### Logical Operators
(&&, ||, !)
These operator takes two boolean expressions.
&& -> If both the expression are true than it returns true.
|| -> If any one of them is true it returns true.
! -> It changes true to false and vice versa.

```java
class Test{
    public static void main(String[] args){
        String usr="geek", pwd="GEEK";
        Scanner sc = new Scanner(System.in);
        String iu = sc.next();
        String ip = sc.next();
        if(user.equals(iu) && pwd.equals(ip)){
            System.out.println("Welcome");
        }
        else{
            System.out.println("Try again");
        }
    }
}
```

#### **Short Circuiting in Logical Operators**

if(x && y) -> If the first expression results in false than there is no point executing the second expression as the result will be false only.

if(x || y) -> If the first expression results in true than there is no point executing the second expression as the result will be true only.

Example of short circuiting: -
String s;
String getting modified in the program.


if(s!= null && s.length()<100)
    System.out.println("Invalid");
else
    System.out.println("Valid");

Now, length() function can give null pointer exception because we cannot access anything on null. But you will never get this exception as the Logical operator is there, the first condition becomes false if the string is null which results to short circuiting.

---
### Relational Operators
These operators are also called Comparision operators, genrally compares two values and returns true or false.

These operators are used to check for relations like equality, greater than, and less than. They return boolean results after the comparison and are extensively used in looping statements as well as conditional if-else statements. The general format is, 

variable relation_operator value
Some of the relational operators are- 
==, Equal to returns true if the left-hand side is equal to the right-hand side.
!=, Not Equal to returns true if the left-hand side is not equal to the right-hand side.
<, less than: returns true if the left-hand side is less than the right-hand side.
<=, less than or equal to returns true if the left-hand side is less than or equal to the right-hand side.
>, Greater than: returns true if the left-hand side is greater than the right-hand side.
>=, Greater than or equal to returns true if the left-hand side is greater than or equal to the right-hand side.

--- 
### Bitwise Operators in java
### Bitwise AND
It works similar to AND gate of electronics.
The output is 1 only when both the inputs are 1.
32 bit representation in java.

```java
public class Test{
    public static void main(String[] args){
        int x=3, y=6;
        System.out.println(x&y);
    }
}
```

### Bitwise OR
Your output is 1 when any of the inputs have 1.

```java
public class Test{
    public static void main(String[] args){
        int x=3, y=6;
        System.out.println(x|y);
    }
}
```

### Bitwise XOR
Your output returns 1 when two input bits are different. It produces 0 when input bits are same.

```java
public class Test{
    public static void main(String[] args){
        int x=3, y=6;
        System.out.println(x^y);
    }
}
```

### Bitwise NOT
Changes the bit, 0 to 1, 1 to 0.
In java, negative numbers are stored in 2's complement.
Representation of -x = 2^32 - x.

```java
class Test{
    public static void main(String[] args){
        int x = 5
        System.out.println(~x);
    }
}
```

- **2^32 - 1 = 1111111111111111111111111**

x: 0000.....1
~x: 11111......10 (2^32 - 1 -1 ) -> 2^32 - 2
Now compare this two values 2^32 - 2 and 2^32 - x.
The value of x is 2. 
So, the representation of x=1 in 2's completement in -2.

For x = 5.
x = 000000.....101

~x = 111111.....1010 -> 2^32 - 1 - 5

So, on screen you will get -6.

### Bitwise Complement (~)

This operator is a unary operator, denoted by '~.' It returns the one's complement representation of the input value, i.e., with all bits inverted, which means it makes every 0 to 1, and every 1 to 0. 

Example:

a = 5 = 0101 (In Binary)

Bitwise Complement Operation of 5

~ 0101
________
1010 = 10 (In decimal)

Note: Compiler will give 2's complement of that number, i.e., 2's complement of 10 will be -6.

### Left Shift Operator <<

It shifs the binary bits y the number of times its mentio
n in this operator.

x: 000000000000.....0011
(x<<1): 00000000000.......0110

(x<<2): 0000.......01100

(x<<4):00000.....0110000

```java
class Test{
    public static void main(String[] args){
        int x=3;
        System.out.println(x<<1);
        System.out.println(x<<2);
        int y=4;
        int z = (x<<y);
        System.out.println(z);
    }
}
```

what if you leftshift -1.

2^32 -1 = 11111......1111

-1 << 1 -> 1111111.....1110

Its 2^32 - 1 - 1 which is 2^32 - 2.

So, its -2.

### Right Shift Operator >>, >>>

In C/C++ there is only one right shift operator '>>' which should be used only for positive integers or unsigned integers. Use of the right shift operator for negative numbers is not recommended in C/C++, and when used for negative numbers, the output is compiler dependent. Unlike C++, Java supports following two right shift operators.

Here we will be discussing both of right shift operators as listed:

**Signed right shift ">>"**
**Unsigned right shift ">>>"**

It shifs the binary bits y the number of times its mention in this operator.

- **Signed Right Shift >>**: **It treats negatives and positive numbers differently.**
**In case, of positive it fills the leading bits with 0.**
**In case, of negative it fills the leading bits with 1, to keep the sign.**

x: 000000000000.....0011
(x>>1): *0*00000000000.......011

(x>>2): *0*00000.......011

(x>>4): *0*0000000.....011

y: 11111.......10
(y>>1): *1*1111111...........1

```java
// Java Program to Illustrate Signed Right Shift Operator

// Main class
class GfG {

    // Main driver method
    public static void main(String args[]) {

        int x = -4;
        System.out.println(x >> 1);

        int y = 4;
        System.out.println(y >> 1);
    }
}
```

Output
-2
2
Explanation:
Negative Number (x = -4):
Binary representation of -4 (in 8-bit, 2's complement): 11111100.
When shifted right by 1: 11111110 (sign bit 1 is preserved).
Decimal value: -2.
Positive Number (y = 4):
Binary representation of 4 (in 8-bit): 00000100.
When shifted right by 1: 00000010.
Decimal value: 2.

 
- **Unsigned Right Shift  >>>**
This also shift the bits to the right according to the number of poitions given, here we fill the **leading bits with 0 for the negative numbers too.**

It considers filling 0 for both negative and positive numbers.

x: 1111.......10
(x>>>1): 01111..........11 -> 2^31 - 1
(x>>>2): 001111.......11 -> 2^30 - 1


In Java, the operator '>>>' denotes unsigned right shift operator and always fill 0 irrespective of the sign of the number.

Example:
```java
// Java Program to Illustrate Unsigned Right Shift Operator

// Main class
class GfG {

    // main driver method
    public static void main(String args[]) {

        // x is stored using 32 bit 2's complement form.
        // Binary representation of -1 is all 1s (111..1)
        int x = -1;

        // The value of 'x>>>29' is 00...0111
        System.out.println(x >>> 29);

        // The value of 'x>>>30' is 00...0011
        System.out.println(x >>> 30);

        // The value of 'x>>>31' is 00...0001
        System.out.println(x >>> 31);
    }
}
```
Output
7
3
1
Explanation:
Initial Value (x = -1):
Binary representation of -1 (32-bit): 11111111111111111111111111111111.
Right Shift by 29 Positions (x >>> 29):
Resulting binary: 00000000000000000000000000000111 (last 3 bits remain).
Decimal value: 7.
Right Shift by 30 Positions (x >>> 30):
Resulting binary: 00000000000000000000000000000011 (last 2 bits remain).
Decimal value: 3.
Right Shift by 31 Positions (x >>> 31):
Resulting binary: 00000000000000000000000000000001 (last 1 bit remains).
Decimal value: 1.


#### Questions
-> Sum of N numbers - Use n*(n+1)/2 formula.
Efficient Approach – O(1) Time and O(1) Space
The above program causes overflow, even if the result is not beyond the integer limit. We can avoid overflow up to some extent by dividing first.

```java
// Efficient JAVA program to find sum of first
// n natural numbers that avoids overflow if
// result is going to be within limits.
import java.io.*;

class GfG {
    public static void main(String args[]) {
        int n = 5;
        int sum;
        if (n % 2 == 0)
            sum = (n / 2) * (n + 1);
        // If n is odd, (n+1) must be even
        else
            sum = ((n + 1) / 2) * n;
        System.out.println(sum);
    }
}
```
Output
15

-> Find the last digit of a number - Take modulus of the number with 10. 123%10 = 3. Also take the absoulte value of the number to remove the sign.

-> Day before N days - Two inputs d and n, d for on which day you are and n for the days you have to go back in time.
ans = n%7
ans > 0? ans: ans+7;

-> nth term of AP
Use **a + (n-1)*d Formula**.
a = first term of the A.P.
n = nth term of the A.P.
d = difference of the terms of the A.P.

-> nth term of GP
2, 4, 8, 16, 32......
^
4/2=2, 8/4=2, 16/8=2

**formula -> a*r^(n-1)**.

```java
public static int nth_term(int a, int r, int n){
    int n = a*(int)(Math.pow(r, n-1)); // Math.pow() gives answer in double. So, it is converted into an integer. 
    return n;
}

public static void main(String[] args){
    Scanner sc = new Scanner(System.in);
    int a  = s.nextInt();
    int r = s.nextInt();
    int n = s.nextInt();

    System.out.print(nth_term(a,r,n));
}
```

![Alt text](https://media.geeksforgeeks.org/wp-content/uploads/operators.png)
