### Print 1 to N using Recursion

#### Method 1
```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

class GFG
{
	// Prints numbers from 1 to n
	static void printNos(int n)
	{
		if(n > 0)
		{
			printNos(n - 1);
			System.out.print(n + " ");
		}
		return;
	}

	// Driver Code
	public static void main(String[] args)
	{
		printNos(10);
	}
}
```

What they do?
- java.io.* → gives access to classes for input/output (e.g., BufferedReader, File, etc.).
- java.util.* → data structures like ArrayList, HashMap, etc.
- java.text.* → formatting dates/numbers.
- java.math.* → big numbers (BigInteger, BigDecimal).
- java.util.regex.* → regular expressions.
- The * means “import everything from that package”.

#### Method 2
```java
import java.io.*;

class GFG {
	public static void main(String[] args)
	{
		printNos(1, 10);
	}
	public static void printNos(int initial, int last)
	{
		if (initial <= last) {
			System.out.print(initial + " ");
			printNos(initial + 1, last);
		}
	}
}
```