## Binary Search

### Naive Solution
Linear search, not using the fact that the given array is sorted.

### Binary Search
Finding the mid point first, using the start index and end index. 
Compute the mid = (s + e)/2
Case 1: (arr[mid]==x) - The element is at mid index.
Case 2: (arr[mid]> x) - The element is smaller than mid, so e = mid-1.
Case 3: (arr[mid]< x) - The element is bigger than mid, so s = mid+1.

Looping through this logic till s <= e.

```java
class Main {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 45, 67, 78, 79, 89};
        int s = 0;
        int e = arr.length;
        
        int element = 30;
        
        while(s<=e){
            int mid = (s+e)/2;
            if(arr[mid]==element){
                System.out.println("Element is found at index: "+ mid);
                break;
            }
            else if(arr[mid]>element){
                e = mid - 1;
            }
            else{
                s = mid + 1;
            }
        }
        
    }
}
```

| Loop Condition | End (`e`)            | Safe?       | Comment                                    |
| -------------- | -------------------- | ----------- | ------------------------------------------ |
| `s < e`        | `e = arr.length`     | ⚠️ Risky    | Might skip last index, edge-case dependent |
| `s < e`        | `e = arr.length - 1` | ❌ Incorrect | Skips final index; incomplete search       |
| `s <= e`       | `e = arr.length - 1` | ✅ Correct   | Standard and safe                          |