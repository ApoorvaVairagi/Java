The integer entered by the user is stored in the variable n. Then the while loop is iterated until the test expression n != 0 is evaluated to 0 (false).   We will consider 3456 as the input integer.  

After the first iteration, the value of n will be updated to 345 and the count is incremented to 1.
After the second iteration, the value of n will be updated to 34 and the count is incremented to 2.
After the third iteration, the value of n will be updated to 3 and the count is incremented to 3.
In the fourth iteration, the value of n will be updated to zero and the count will be incremented to 4.  
Then the test expression is evaluated ( n!=0 ) as false and the loop terminates with final count as 4.

```java
// JAVA Code to count number of
// digits in an integer
import java.util.*;

class GFG {

	static int countDigit(long n)
	{
		if (n/10 == 0)
			return 1;
		return 1 + countDigit(n / 10);
	}

	/* Driver code */
	public static void main(String[] args)
	{
		long n = 345289467;
		System.out.print("Number of digits : "
						+ countDigit(n));
	}
}
```

```java
class Main {
    public static void main(String[] args) {
        long n = 345289467;
        int digits = 0;
        while(n!=0){
            digits++;
            n = n/10;
        }
        
        System.out.print(digits);
    }
}
```

Time Complexity : O(log10(n)) or θ(num digits)
Auxiliary Space: O(1) or constant