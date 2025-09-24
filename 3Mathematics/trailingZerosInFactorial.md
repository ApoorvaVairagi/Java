In a realm where numbers hold secrets, a captivating challenge awaits, which is to, Count Trailing Zeros in Factorial !!! 
Our Task: We are given a number. The task is to find the Number of Trailing Zeros in the factorial of the number.
The Trailing Zeros are the Zeros, which appear at the end of a number(factorial in that case)

We have 2 approaches to solve the problem: Naive Approach & Efficient Approach

1) Naive Approach
A simple method is to first calculate the factorial of n, then count trailing 0s in the result (We can count trailing 0s by repeatedly dividing the factorial by 10 till the remainder is not 0).

But, this method can cause overflow for slightly bigger numbers as the factorial of a number is a big number. So, we prefer the Efficient Approach

2) Efficient Approach
The idea is to consider prime factors of a factorial n. A trailing zero is always produced by prime factors 2 and 5. Our task is done if we can count the number of 5s and 2s. Consider the following examples:

n = 5: There is one 5 and 3 2s in prime factors of 5! (2 * 2 * 2 * 3 * 5). So a count of trailing 0s is 1.
n = 11: There are two 5s and eight 2s in prime factors of 11! (28 * 34 * 52 * 7 * 11). So the count of trailing 0s is 2.
We can easily observe that the number of 2s in prime factors is always more than or equal to the number of 5s. So if we count 5s in prime factors, we are done.

Following is the summarized formula for counting trailing 0s:

```java
// Java program to count
// trailing 0s in n!
import java.io.*;

class GFG {
	// Function to return trailing
	// 0s in factorial of n
	static int findTrailingZeros(int n)
	{
		if (n < 0) // Negative Number Edge Case
			return -1;

		// Initialize result
		int count = 0;

		// Keep dividing n by powers
		// of 5 and update count
		for (int i = 5; n / i >= 1; i *= 5)
			count += n / i;

		return count;
	}

	// Driver Code
	public static void main(String[] args)
	{
		int n = 100;
		System.out.println("Count of trailing 0s in " + n
						+ "! is "
						+ findTrailingZeros(n));
	}
}
```

Time Complexity: O(log5n)
Auxiliary Space: O(1)

## Logic
### Step 1: Trailing zeros come from factors of \(10\).
Each \(10 = 2 \times 5\).  
There are usually more 2’s than 5’s in factorials, so the **number of 5’s** determines the count of trailing zeros.

---

### Step 2: Count factors of 5 in \(25!\).
We use:
\[
\text{Number of 5’s} = \left\lfloor \frac{25}{5} \right\rfloor + \left\lfloor \frac{25}{25} \right\rfloor
\]

- \(\lfloor 25/5 \rfloor = 5\) (multiples of 5 → 5, 10, 15, 20, 25)  
- \(\lfloor 25/25 \rfloor = 1\) (for the extra factor of 5 from \(25 = 5^2\))  

Total factors of 5 = \(5 + 1 = 6\).

---

### ✅ Answer:
The number \(1 \times 2 \times 3 \times \cdots \times 25\) (i.e., \(25!\)) has **6 trailing zeros**.