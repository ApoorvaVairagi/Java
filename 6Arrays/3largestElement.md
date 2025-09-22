## Largest Element
Given an array arr of size N, the task is to find the largest element in the given array. 

Example: 

Input: arr[] = {10, 20, 4}
Output: 20

Input : arr[] = {20, 10, 20, 4, 100}
Output : 100

```java
//Approach 1 - Naive Method:
import java.io.*;
import java.lang.*;
import java.math.*;
import java.util.*;

class GFG {
    static int getlargest(int arr[], int n)
    {
        for (int i = 0; i < n; ++i) {
            boolean flag = true;
            for (int j = i; j < n; ++j) {
                if (arr[j] > arr[i]) {
                    flag = false;
                    break;
                }
            }
            if (flag == true) {
                return arr[i];
            }
        }
        return -1;
    }
    public static void main(String[] args)
        throws IOException
    {
        int arr[] = { 5, 8, 20, 15 };
        System.out.println("Largest in given array is "+getlargest(arr, 4));
    }
}
```

Output
Largest in given array is 20


Approach 2 – Linear Traversal: One of the most simplest and basic approach to solve this problem is to simply traverse the whole list and find the maximum among them. 

Follow the steps below to implement this idea:

- Create a local variable max to store the maximum among the list
- Initialize max with the first element initially, to start the comparison.
- Then traverse the given array from second element till end, and for each element:
    - Compare the current element with max
    - If the current element is greater than max, then replace the value of max with the current element.
- At the end, return and print the value of the largest element of array stored in max.

Below is the implementation of the above approach:
```java
// Java Program to find maximum in arr[]
class Test
{
	static int arr[] = {10, 324, 45, 90, 9808};
	
	// Method to find maximum in arr[]
	static int largest()
	{
		int i;
		
		// Initialize maximum element
		int max = arr[0];
		
		// Traverse array elements from second and
		// compare every element with current max
		for (i = 1; i < arr.length; i++)
			if (arr[i] > max)
				max = arr[i];
		
		return max;
	}
	
	// Driver method
	public static void main(String[] args)
	{
		System.out.println("Largest in given array is " + largest());
		}
}
``` 

## Second Largest Element

Given an array of integers, our task is to write a program that efficiently finds the second largest element present in the array. 

Example:

Input: arr[] = {12, 35, 1, 10, 34, 1}
Output: The second largest element is 34.
Explanation: The largest element of the 
array is 35 and the second 
largest element is 34

Input: arr[] = {10, 5, 10}
Output: The second largest element is 5.
Explanation: The largest element of 
the array is 10 and the second 
largest element is 5

Input: arr[] = {10, 10, 10}
Output: The second largest does not exist.
Explanation: Largest element of the array 
is 10 there is no second largest element
Efficient Solution:

Approach: Find the second largest element in a single traversal. 
Below is the complete algorithm for doing this:  

1) Initialize the first as 0(i.e, index of arr[0] element
2) Start traversing the array from array[1],
   a) If the current element in array say arr[i] is greater
      than first. Then update first and second as,
      second = first
      first = arr[i]
   b) If the current element is in between first and second,
      then update second to store the value of current variable as
      second = arr[i]
3) Return the value stored in second.

```java
// JAVA Code for Find Second largest
// element in an array
class GFG {

	/* Function to print the second largest
	elements */
	public static void print2largest(int arr[],
									int arr_size)
	{
		int i, first, second;

		/* There should be atleast two elements */
		if (arr_size < 2) {
			System.out.print(" Invalid Input ");
			return;
		}

		first = second = Integer.MIN_VALUE;
		for (i = 0; i < arr_size; i++) {
			/* If current element is greater than
			first then update both first and second */
			if (arr[i] > first) {
				second = first;
				first = arr[i];
			}

			/* If arr[i] is in between first and
			second then update second */
			else if (arr[i] > second && arr[i] != first)
				second = arr[i];
		}

		if (second == Integer.MIN_VALUE)
			System.out.print("There is no second largest"
							+ " element\n");
		else
			System.out.print("The second largest element"
							+ " is " + second);
	}

	/* Driver program to test above function */
	public static void main(String[] args)
	{
		int arr[] = { 12, 35, 1, 10, 34, 1 };
		int n = arr.length;
		print2largest(arr, n);
	}
}
```

Complexity Analysis:

- Time Complexity: O(n). 
    Only one traversal of the array is needed.
- Auxiliary space: O(1). 
    As no extra space is required.