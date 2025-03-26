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
### Logical Operators
(&&, ||, !)
These operator takes two boolean expressions.
&& -> If both the expression are true than it returns true.
|| -> If any one of them is true it returns true.
! -> It chnages true to false and vice versa.

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

#### Short Circuiting in Logical Operators

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

It shifs the binary bits y the number of times its mentio
n in this operator.

- Signed Right Shift: It treats negatives and positive numbers differently.
In case, of positive it fills the leading bits with 0.
In case, of negative it fills the leading bits with 1, to keep the sign.

x: 000000000000.....0011
(x>>1): *0*00000000000.......011

(x>>2): *0*00000.......011

(x>>4): *0*0000000.....011

y: 11111.......10
(y>>1): *1*1111111...........1
 
- Unsigned Right Shift  >>>
This also shift the bits to the right according to the number of poitions given, here we fill the **leading bits with 0 for the negative numbers too.**

It considers filling 0 for both negative and positive numbers.

x: 1111.......10
(x>>>1): 01111..........11 -> 2^31 - 1
(x>>>2): 001111.......11 -> 2^30 - 1


#### Questions
-> Sum of N numbers - Use n*(n+1)/2 formula.
-> Find the last digit of a number - Take modulus of the number with 10. 123%10 = 3. Also take the absoulte value of the number to remove the sign.
-> Day before N days - Two inputs d and n, d for on which day you are and n for the days you have to go back in time.
ans = n%7
ans > 0? ans: ans+7;

-> nth term of AP
Use a + (n-1)*d Formula.
a = first term of the A.P.
n = nth term of the A.P.
d = difference of the terms of the A.P.

-> nth term of GP
2, 4, 8, 16, 32......

4/2=2, 8/4=2, 16/8=2

formula -> a*r^(n-1)

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


