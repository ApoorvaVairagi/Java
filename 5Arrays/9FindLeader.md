## Find Leader by finding suffix maximum:
The idea is to scan all the elements from right to left in an array and keep track of the maximum till now. When the maximum changes its value, print it.

Follow the below illustration for a better understanding

Illustration:

Let the array be arr[] = {16, 17, 4, 3, 5, 2}

arr[] = {16, 17, 4, 3, 5, 2} , max_from_right = 2 , ans[] = { 2 }
arr[] = {16, 17, 4, 3, 5, 2} , max_from_right = 5 , ans[] = { 2, 5 }
arr[] = {16, 17, 4, 3, 5, 2} , max_from_right = 5 , ans[] = { 2, 5 } 
arr[] = {16, 17, 4, 3, 5, 2} , max_from_right = 5 , ans[] = { 2, 5 }
arr[] = {16, 17, 4, 3, 5, 2} , max_from_right = 17 , ans[] = { 2, 5, 17 }
arr[] = {16, 17, 4, 3, 5, 2} , max_from_right = 17 , ans[] = { 2, 5, 17 }

Follow the steps mentioned below to implement the idea:

- We start from the last index position. The last position is always a leader, as there are no elements towards its right. 
- And then we iterate on the array till we reach index position = 0.
- Each time we keep a check on the maximum value
- Every time we encounter a maximum value than the previous maximum value encountered, we either print or store the value as it is the leader
- Below is the implementation of the above approach.

```java
class LeadersInArray
{
    /* Java Function to print leaders in an array */
    void printLeaders(int arr[], int size)
    {
        int max_from_right = arr[size-1];
​
        /* Rightmost element is always leader */
        System.out.print(max_from_right + " ");
    
        for (int i = size-2; i >= 0; i--)
        {
            if (max_from_right < arr[i])
            {       
            max_from_right = arr[i];
            System.out.print(max_from_right + " ");
            }
        }
    }
​
    /* Driver program to test above functions */
    public static void main(String[] args)
    {
        LeadersInArray lead = new LeadersInArray();
        int arr[] = new int[]{16, 17, 4, 3, 5, 2};
        int n = arr.length;
        lead.printLeaders(arr, n);
    }
}
```

Output

2 5 17 
Time Complexity: O(n)
Auxiliary Space: O(1)