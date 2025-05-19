## BigInteger Class

The BigInteger class in Java is a powerful tool used to handle large integer values that exceed the limits of primitive data types. This class is part of the java.math package and provides methods for various mathematical operations.


Why Use BigInteger?
When working with extremely large numbers, such as factorials of large numbers (e.g., 100!), the standard integer types like int and long are insufficient. For example:

5! = 120
10! = 3,628,800
15! = 1.307 × 10¹²
These calculations require a data type that can handle arbitrarily large values, and BigInteger fits this purpose.

----

**Initialization of BigInteger**
You can initialize BigInteger objects in the following ways:

Using String: This initializes a BigInteger using a string value directly.
BigInteger A = new BigInteger("54");

Using String Variable: You can also initialize a BigInteger using a string stored in a variable.

String b = "1234567";
BigInteger B = new BigInteger(b);

**Using Primitive Types**: This initializes a BigInteger using a primitive data type, such as an int.
int c = 12467;

BigInteger C = BigInteger.valueOf(c);


**Different Operations on BigInteger**

Arithmetic Operations:

**Addition**: Adds two BigInteger values.
BigInteger A = new BigInteger("54");

BigInteger B = new BigInteger("10");

BigInteger C = A.add(B); // Result: 64

**Subtraction, Multiplication, Division**
These operations are similar: subtract(), multiply(), divide().
BigInteger C = A.subtract(B);

BigInteger C = A.multiply(B);

BigInteger C = A.divide(B);

**Comparison**:
Using compareTo: Compares two BigInteger values.
if (A.compareTo(B) > 0) {

System.out.println("A is greater than B");

}

**Equality Check**: Checks if two BigInteger values are equal.
if (A.equals(B)) {

System.out.println("A is equal to B");

}

**Conversion**:

Convert to int: Converts BigInteger to an int. (Ensure the value fits within int limits.)
int a = A.intValue();

Convert to long: Converts BigInteger to a long.
long b = A.longValue();

Convert to String: Converts BigInteger to a String.
String z = A.toString();


**BigInteger Methods**

| Method                          | Description                                                       |
|---------------------------------|-------------------------------------------------------------------|
| `add(BigInteger val)`          | Returns a BigInteger whose value is `(this + val)`.              |
| `subtract(BigInteger val)`     | Returns a BigInteger whose value is `(this - val)`.              |
| `multiply(BigInteger val)`     | Returns a BigInteger whose value is `(this * val)`.              |
| `divide(BigInteger val)`       | Returns a BigInteger whose value is `(this / val)`.              |
| `remainder(BigInteger val)`    | Returns a BigInteger whose value is `(this % val)`.              |
| `pow(int exponent)`            | Returns a BigInteger whose value is `(this^exponent)`.           |
| `compareTo(BigInteger val)`    | Compares this BigInteger with the specified BigInteger.          |
| `mod(BigInteger m)`            | Returns a BigInteger whose value is `(this mod m)`.              |
| `isProbablePrime(int certainty)` | Tests if this BigInteger is probably prime.                    |


**Factorial Calculation Using BigInteger**
Factorial of a number N is the product of all positive integers less than or equal to N. For large values of N, the factorial becomes too large to store in primitive data types like int or long. The BigInteger class in Java allows us to handle such large numbers effectively.

```java
import java.math.BigInteger;

public class GfG {
    public static BigInteger factorial(int N) {
        BigInteger f = BigInteger.ONE;
        for (int i = 2; i <= N; i++) {
            BigInteger x = BigInteger.valueOf(i);
            f = f.multiply(x);
        }
        return f;
    }

    public static void main(String[] args) {
        int N = 100; // Calculate 100!
        System.out.println(factorial(N));
    }
}
```

-> Q. Checking if a number is prime or what's the next prime after that number.

```java
import java.math.BigInteger;

public class GfG {
    public static boolean isPrime(int n) {
        BigInteger b = BigInteger.valueOf(n);
        return b.isProbabalePrime(1);
    }

    public static int nextPrime(int n) {
        BigInteger b = BigInteger.valueOf(n);
        String a = b.nextProbablePrime().toString();
        return Integer.ParseInt(a);
    }
}
```