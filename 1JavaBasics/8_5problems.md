-> Q. **Panagram** Checking in Java

You are given a string, you need to check if it is Pangram or not. A pangram is a sentence containing every letter in the English alphabet.

Examples:


Input: str = "The quick brown fox jumps over the lazy dog”
Output: true
Explanation: The statement contains all the characters from ‘a’ to ‘z’

Input: str = "abc xyz pqr"
Output: false
Explanation: This string does not contain all the characters from ‘a’ to ‘z’, as some letters are missing.


Approach:

To determine if a given string is a pangram:

Create an Array:
Use an array of size 26 to represent the 26 letters of the English alphabet. Each index corresponds to a letter, where index 0 represents 'a', index 1 represents 'b', and so on.
Iterate Through the String:
Convert all characters in the string to their lowercase or uppercase equivalent (both cases are treated as the same).
For each character in the string, mark its corresponding index in the array as true. For example, the letter 'a' (or 'A') marks index 0, while 'z' (or 'Z') marks index 25.
Check for Missing Letters:
After processing all the characters in the string, check the array to see if any position remains false. If any position is false, the string is not a pangram.
Return the Result:
If all positions are marked true, return true as the string is a pangram. Otherwise, return false.

Here’s the Java implementation of the above approach:
 
```java
import java.util.*;

class GfG {
    
    static boolean isPanagram(String s)
    {
        int n = s.length();
        
        if(n < 26)
            return false;
        
        boolean visited[] = new boolean[26];
        
        for(int i=0; i<n; i++)
        {
            char x = s.charAt(i);
            
            if(x >= 'a' && x <='z')
            {
                visited[x-'a'] = true;
            }
            
            if(x >= 'A' && x <='Z')
            {
                visited[x-'A'] = true;
            }
        }
        
        for(int i =0; i<26; i++)
        {
            if(visited[i] == false)
                return false;
        }
        
        return true;
    }
    
    public static void main(String args[])
    {
        String s = "The quick brown fox jumps over the lazy dog";
        
        System.out.println(isPanagram(s));
    }
}
```

Output
true

-> Q. Pattern Searching

Problem: This is a basic Pattern search problem where a text and a word will be given. The task is to find in what all positions the word is present in the text.

Example: 

Input: text = "geeks for geeks"
       word = "geeks"
Output: 0 10
Explanation: The word "geeks" can be found in two positions 0 & 10.

Input: arr1[] = "Welcome to the world of geeks"
       word = "world"
Output: 15
Explanation: The word "world" can be found at index position 15.


Solution: 
The idea is to use the indexOf() function of the String class in Java. 
 

First, find the first occurrence of the pattern in the text using the indexOf() method. Let's say this position is denoted by pos.
Now, to find all occurrences, what we can do is we can continue finding the occurrence of pattern in the text from (pos+1)th position using the indexOf() method till pos becomes negative.


Implementation:
 
```java
// Java implementation of the above approach
import java.util.*;

class GfG {
    
    static void patSearch(String txt, String pat)
    {
        int pos = txt.indexOf(pat);
        
        while(pos >= 0)
        {
            System.out.print(pos + " ");
            pos = txt.indexOf(pat, pos + 1);
        }
    }
    
    public static void main(String args[])
    {
        String txt = "geeks for geeks";
        String pat = "geeks";
        
        patSearch(txt, pat);
    }
}
```

Output:
0 10


-> Q.2 Pattern Searching
The large numbers which can not be stored in the float or double datatypes are stored as strings.
The problem here is to find the number of digits after the decimal point.

Input: 3949.4324
Output: 4324

Code:
```java
import java.util.Scanner;

class Test{
    public static String digitsAfterDecimal(String no){
        int pos = no.indexOf(".");
        if(pos<0){
            return "";
        }
        else{
            String s= no.substring(pos+1);
            return s;
        }
    }
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the no: ");
        String no = sc.next();
        String str = digitsAfterDecimal(no);
        System.out.println(str);
    }
}
```

-> Q. Find one extra character

Two strings are given of lengths n and n+1. The second string contains all the characters of the first string, but there is one extra character. The task is to find the extra character in the second string.

Note: The characters in strings can be in any order. 

Examples :

Input: str1 = "abcd";
str2 = "cbdae";
Output: e
Explanation: str2 contains all the element of str1 with one extra alphabet 'e'.

Input: str1 = "kxml";
str2 = "klxml";
Output: l
Explanation: str2 contains all the element of str1 with one extra alphabet 'l'.


Method 1: Sorting
A simple method is to sort both of the arrays, and then start comparing characters one by one from start. If we found a mismatch, then the mismatched character from the second string is the answer as it has one extra character. If we don't find a mismatch, then the last character in the second string is the answer.

Note: Java doesn't provide a sort function for the String class. We need to convert the String to a character array and then use Arrays.sort().

```java
// Importing the Arrays class
import java.util.Arrays;

class GFG {
    public static char findExtra(String s1, String s2) {
        // Convert strings to character arrays
        char[] a1 = s1.toCharArray();
        char[] a2 = s2.toCharArray();
        
        // Sort both arrays
        Arrays.sort(a1);
        Arrays.sort(a2);
        
        // Compare characters
        int n = a1.length; // Length of the smaller string
        for (int i = 0; i < n; i++) {
            if (a1[i] != a2[i]) {
                return a2[i]; // Return the extra character
            }
        }
        
        // If no mismatch, the extra character is the last one
        return a2[n];
    }

    public static void main(String[] args) {
        String s1 = "abcd";
        String s2 = "abcde";
        System.out.println("Extra character: " + findExtra(s1, s2));
    }
}
```

Output
Extra character: e

Time Complexity: O(n*log*n).
Auxiliary Space: O(n).

Method 2: Counting
We can use frequency counting. We have assumed that the input strings have only lowercase English alphabets. 

Create a count array of size 26 to store the frequency of characters (assuming only lowercase alphabets).
Traverse s1 and decrement the count for each character.
Traverse s2 and increment the count for each character.
The character with a count of 1 is the extra character.
Here's the code implementation of above approach:
 
```java
import java.util.*;

class GfG {
    
    static char findExtra(String s1, String s2)
    {
        int count[] = new int[26];
        
        int n = s1.length();
        
        for(int i=0; i<n; i++)
        {
            count[s2.charAt(i) - 'a']++;
            count[s1.charAt(i) - 'a']--;
        }
        
        count[s2.charAt(n) - 'a']++;
        
        for(int i=0; i<26; i++)
        {
            if(count[i] == 1)
                return (char)(i + 'a');
        }
        
        return 0;
    }
    
    public static void main(String args[])
    {
        String s1 = "abcd";
        String s2 = "cbdae";
        
        System.out.println(findExtra(s1, s2));
    }
}
```
Output
e

Time Complexity: O(N).
Auxiliary Space: O(1).

Method 3: Bitwise-XOR Operator
Using Bitwise Operators. If we combine all characters in both of the strings, we can see that every character will appear in multiples of 2 and there is only one character that will not have any duplicates.

Initialize a variable res to store the XOR result.
XOR all characters in s1 and s2.
The result after XORing will be the extra character, as XOR of two identical characters cancels them out.
Here's the code implementation of above approach:
 
```java
import java.util.*;

class GfG {
    
    static char findExtra(String s1, String s2)
    {
        int res = 0;
        
        int n = s1.length();
        
        for(int i=0; i<n; i++)
        {
            res = res^s2.charAt(i)^s1.charAt(i);
        }
        
        res = res^s2.charAt(n);
        
        return (char)res;
    }
    
    public static void main(String args[])
    {
        String s1 = "abcd";
        String s2 = "cbdae";
        
        System.out.println(findExtra(s1, s2));
    }
}
```
Output
e

Time Complexity: O(N).
Auxiliary Space: O(1).


-> Q. Check for Anagram

Given two strings, check whether two strings are an anagram of each other. Two strings are said to be an anagram of each other if they are just permutations of each other. That is, the set of characters in both the strings must be the same, only the order of characters can be different.

Examples:

Input: s1 = "listen"
s2 = "silent"
Output: Yes
Explanation: Both the string have same characters with same frequency. So, they are anagrams.

Input: s1 = "aab"
s2 = "bab"
Output: No
Explanation: Characters in both the strings are not same, so they are not anagrams.


Method 1: Naive Solution
The naive solution involves sorting both strings and comparing the sorted results. If the sorted strings are identical, the two strings are anagrams. This approach is straightforward but not the most efficient due to the sorting step.

Check if the lengths of the two strings are equal. If not, return false.
Convert both strings into character arrays and sort them.
Convert the sorted arrays back into strings and compare them.
If the sorted strings are identical, the original strings are anagrams.
After sorting, we can use the equals() method to check if both of the strings are equal or not and return true or false accordingly. 

Here's the code implementation of above approach:

```java
import java.util.Arrays;

class GFG {
    public static boolean areAnagramNaive(String s1, String s2) {
        // Check if lengths of both strings are equal
        if (s1.length() != s2.length()) {
            return false;
        }
        // Convert first strings to character arrays and sort
        char[] a1 = s1.toCharArray();
        Arrays.sort(a1);
        s1 = new String(a1);
        // Convert second strings to character arrays and sort
        char[] a2 = s2.toCharArray();
        Arrays.sort(a2);
        s2 = new String (a2);
        // Compare sorted arrays
        return s1.equals(s2);
    }
    public static void main(String[] args) {
        String s1 = "abaac";
        String s2 = "aacba";

        System.out.println(areAnagramNaive(s1, s2));
    }
}
```
Output
true

Time Complexity: O(N*logN)
Auxiliary Space: O(1)

Method 2: Efficient Solution

A more efficient solution uses a frequency count to compare the characters of both strings. This approach avoids sorting and works in linear time.

Initialize a count array of size 256 to represent all possible ASCII characters.
Iterate through both strings simultaneously:
Increment the count for characters in the first string.
Decrement the count for characters in the second string.
After iterating, check if all values in the count array are zero. If any value is non-zero, the strings are not anagrams.
Here's the code implementation of above approach:
 
```java
import java.util.*;

class GfG {
    
    static final int CHAR = 256;
    
    static boolean areAnagram(String s1, String s2)
    {
        if(s1.length() != s2.length())
            return false;
            
        int count[] = new int[CHAR];
        
        for(int i=0; i<s1.length(); i++)
        {
            count[s1.charAt(i)]++;
            count[s2.charAt(i)]--;
        }
        
        for(int i=0; i<CHAR; i++)
        {
            if(count[i] != 0)
                return false;
        }
        
        return true;
    }
    
    public static void main(String args[])
    {
        String s1 = "aabca";
        String s2 = "acaba";
        
        System.out.println(areAnagram(s1, s2));
    }
}
```
Output
true

Time Complexity: O(N)
Auxiliary Space: O(256)

-> Check for Palindrome

```java
import java.util.Scanner;

class Main {
    public static boolean checkPalindrome(String s){
        int start = 0;
        int end = s.length() - 1;
        
        while(start<end){
            if(s.charAt(start)!= s.charAt(end)){
                return false;
            }
            start++;
            end--;
        }
        return true;
    }
    
    public static void main(String[] args) {
        System.out.println("Enter a String: ");
        Scanner sc = new Scanner(System.in);
        String s = sc.next();
        
        if(checkPalindrome(s)){
            System.out.println("String "+s+" is a palindrome.");
        }
        else{
            System.out.println("Not a palindrome.");
        }
    }
}
```

-> Q. Reverse String

```java
Scanner sc = new Scanner(System.in);
String a = sc.nextline();
String b = "";
int ptr = a.length()-1;
while(ptr>=0){
    b = b + a.charAt(ptr);
    ptr--;
}

System.out.println(b);
```

-> Q. Decimal to Binary Conversion

int i=10;
binary representation = 1010

Divide by 2 to get the binary representation.

10/2 = 5 -> 0
5/2 = 2 -> 1
2/2 = 1 -> 0

taking this in reverse order 1010.

```java
public static void decimalToBinary(int n ){
    String s = "";
    while(n>0){
        s = (n%2)+s;
        n=n/2;
    }
    System.out.print(s);
}
```

-> Q. Binary to Decimal Conversion
Input: '110'
Output: 6

1*2^2 + 1*2^1 + 0*2^0 = 6

```java
public static void bintoDec(String s){
    int m=0;
    int k=1;
    for(int i=s.length()-1; i>=0; i--){
        m+=(s.charAt(i)-'0')*k;
        k*=2;
    }
    System.out.print(m);
}
```
- '0' is subtracted to convert the char to int value.