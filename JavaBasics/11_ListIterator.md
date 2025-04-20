## List Iterator in Java

The ListIterator works only with the List interface in Java and it is inherited from the Iterator interface. So, it includes all functionalities of the iterator interface. 
 

It works only with Lists like ArrayList, Vector, LinkedList.
It is inherited from the Iterator interface. So, it includes all functionalities of the iterator interface.

In addition to next(), hashNext() and remove(), it provides the below methods:

* hasPrevious() - It is used to check if we have a previous item for the item pointed by the current iterator or not.
* previous() - It returns the previous element of the list, and moves the iterator one position back.
* add() - It is used to add an item while iterating through the List.
* set() - replaces the element returned by either next() or previous() with the specified element
* nextIndex() returns the index of the element that the next() method will return
* previousIndex() - returns the index of the element that the previous() method will return

Forward traversal using Iterator
```java
import java.util.*;

class Gfg{
    public static void main (String[] args) {
        
        // Create a List
        List<Integer> list = new ArrayList<Integer>();
    
        // Add element to List
        list.add(10);
        list.add(20);
        list.add(30);
        
        // Iterator pointing to position just before 
        // first element
        ListIterator<Integer> it = list.listIterator();
        
        // While there is a next element of the 
        // current iterator
        while(it.hasNext())
        {   
            // Print the next element and increment
            // iterator by one position
            System.out.println(it.next());
        }
    }
}
```

-> Q. List of smaller numbers

```java
// Java Program to return a List of integer
// with values less than K

import java.util.*;

class Test{
    
    static List<Integer> getSmaller(int arr[], int k)
    {
        List<Integer> al = new ArrayList<Integer>();
        
        for(int i=0; i<arr.length; i++)
        {
            if(arr[i] < k)
                al.add(arr[i]);
        }
        
        return al;
    }
    
    public static void main (String[] args) {
        
        // Create a ArrayList
        int arr[] = {10, 40, 80, 30, 20, 15};
        
        List<Integer> al = getSmaller(arr, 30);
        
        for(Integer x: al)
            System.out.println(x);
    }
}
```