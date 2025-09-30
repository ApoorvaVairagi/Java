## BinarySearch using Built-in Methods in Java

If you are a Java programmer, you must have used built-in methods in Java at some point for basic operations like sorting, reversing etc. Java also provides us methods to perform Binary Search on both Arrays and Collection classes. The most commonly used methods in Java to perform Binary Search are:

- Arrays.binarySearch()
- Collections.binarySearch()
Let's look at each of the above two methods in details:

### Arrays.binarySearch()
Arrays.binarySearch() is the simplest and most efficient method to find an element in a sorted array in Java.

Declaration:
```java 
public static int binarySearch(data_type arr, data_type key)
```
Where data_type can be any of the primitive data types: byte, char, double, int, float, short, long and Object as well.

Description: This method searches the specified array of the given data type for the specified value using the binary search algorithm. **The array must be sorted prior to making this call.** If it is not sorted, the results are undefined. If the array contains multiple elements with the specified value, there is no guarantee which one will be found.

Parameters:
arr - the array to be searched
key - the value to be searched for

Return Value: It returns the index of the search key, if it is contained in the array; otherwise, (-(insertion point) - 1). **The insertion point is defined as the point at which the key would be inserted into the array: the index of the first element greater than the key, or a.length if all elements in the array are less than the specified key.** Note that this guarantees that the return value will be >= 0 if and only if the key is found.

Examples:

Searching for 35 in byteArr[] = {10, 20, 15, 22, 35}:
Step 1: Sort the array: {10, 15, 20, 22, 35}.
Step 2: Perform binary search for 35.
Result: The result will be 4 because 35 is located at index 4.

Example:
Searching for 35 in byteArr[] = {10, 20, 15, 22, 35}
will give result as 4 as it is the index of 35.
Searching for 'g' in charArr[] = {'g', 'p', 'q', 'c', 'i'}:
Step 1: Sort the array: {'c', 'g', 'i', 'p', 'q'}.
Step 2: Perform binary search for 'g'.
Result: The result will be 1 because 'g' is located at index 1.

Example:
Searching for 'g' in charArr[] = {'g', 'p', 'q', 'c', 'i'}
will give result as 1 as it is the index of 'g'.
Searching for 22 in intArr[] = {10, 20, 15, 22, 35}:
Step 1: Sort the array: {10, 15, 20, 22, 35}.
Step 2: Perform binary search for 22.
Result: The result will be 3 because 22 is located at index 3.

Example:
Searching for 22 in intArr[] = {10, 20, 15, 22, 35}
will give result as 3 as it is the index of 22.
Searching for 1.5 in doubleArr[] = {10.2, 15.1, 2.2, 3.5}:
Step 1: Sort the array: {2.2, 3.5, 10.2, 15.1}.
Step 2: Perform binary search for 1.5.
Result: Since 1.5 is not in the array, the result will be -1, indicating the insertion point.

Example:
Searching for 1.5 in doubleArr[] = {10.2, 15.1, 2.2, 3.5}
will give result as -1 as it is the insertion point of 1.5.
Searching for 35.0 in floatArr[] = {10.2f, 15.1f, 2.2f, 3.5f}:
Step 1: Sort the array: {2.2f, 3.5f, 10.2f, 15.1f}.
Step 2: Perform binary search for 35.0.
Result: Since 35.0 is not in the array, the result will be -5, indicating the insertion point.

Example:
Searching for 35.0 in floatArr[] = {10.2f, 15.1f, 2.2f, 3.5f}
will give result as -5 as it is the insertion point of 35.0.
Searching for 5 in shortArr[] = {10, 20, 15, 22, 35}:
Step 1: Sort the array: {10, 15, 20, 22, 35}.
Step 2: Perform binary search for 5.
Result: Since 5 is not in the array, the result will be -1, indicating the insertion point.

Example:
Searching for 5 in shortArr[] = {10, 20, 15, 22, 35}
will give result as -1 as it is the insertion point of 5.

```java
// Java program to demonstrate working of Arrays.
// binarySearch() in a sorted array

import java.util.Arrays;

public class GFG
{
    public static void main(String[] args)
    {
        byte byteArr[] = {10,20,15,22,35};
        char charArr[] = {'g','p','q','c','i'};
        int intArr[] = {10,20,15,22,35};
        double doubleArr[] = {10.2,15.1,2.2,3.5};
        float floatArr[] = {10.2f,15.1f,2.2f,3.5f};
        short shortArr[] = {10,20,15,22,35};

        Arrays.sort(byteArr);
        Arrays.sort(charArr);
        Arrays.sort(intArr);
        Arrays.sort(doubleArr);
        Arrays.sort(floatArr);
        Arrays.sort(shortArr);

        byte byteKey = 35;
        char charKey = 'g';
        int intKey = 22;
        double doubleKey = 1.5;
        float floatKey = 35;
        short shortKey = 5;

        System.out.println(byteKey + " found at index = "
                           +Arrays.binarySearch(byteArr,byteKey));
        System.out.println(charKey + " found at index = "
                           +Arrays.binarySearch(charArr,charKey));
        System.out.println(intKey + " found at index = "
                           +Arrays.binarySearch(intArr,intKey));
        System.out.println(doubleKey + " found at index = "
                           +Arrays.binarySearch(doubleArr,doubleKey));
        System.out.println(floatKey + " found at index = "
                           +Arrays.binarySearch(floatArr,floatKey));
        System.out.println(shortKey + " found at index = "
                           +Arrays.binarySearch(shortArr,shortKey));
    }
}
```

#### Important Points:

- If input list is not sorted, the results are undefined.
- If there are duplicates, there is no guarantee which one will be found.