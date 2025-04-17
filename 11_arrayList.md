## ArrayList in Java

ArrayList is a part of collection framework and is present in java.util package. It provides us with dynamic arrays in Java. Though, it may be slower than standard arrays but can be helpful in programs where lots of manipulation in the array is needed. This class is found in java.util package. 

```java
// Java program to demonstrate the 
// working of ArrayList in Java 

import java.io.*; 
import java.util.*; 

class ArrayListExample { 
    public static void main(String[] args) 
    { 
        // Size of the 
        // ArrayList 
        int n = 5; 

        // Declaring the ArrayList with 
        // initial size n 
        ArrayList<Integer> arrli 
            = new ArrayList<Integer>(n); 

        // Appending new elements at 
        // the end of the list 
        for (int i = 1; i <= n; i++) 
            arrli.add(i); 

        // Printing elements 
        System.out.println(arrli); 

        // Remove element at index 3 
        arrli.remove(3); 

        // Displaying the ArrayList 
        // after deletion 
        System.out.println(arrli); 

        // Printing elements one by one 
        for (int i = 0; i < arrli.size(); i++) 
            System.out.print(arrli.get(i) + " "); 
    } 
}
```

Since ArrayList is a dynamic array and we do not have to specify the size while creating it, the size of the array automatically increases when we dynamically add and remove items. Though the actual library implementation may be more complex, the following is a very basic idea explaining the working of the array when the array becomes full and if we try to add an item:

* Creates a bigger-sized memory on heap memory (for example memory of double size).
* Copies the current memory elements to the new memory.
* New item is added now as there is bigger memory available now.
* Delete the old memory.

Important Features:
* ArrayList inherits AbstractList class and implements the List interface.
* ArrayList is initialized by the size. However, the size is increased automatically if the collection grows or shrinks if the objects are removed from the collection.
* Java ArrayList allows us to randomly access the list.
* ArrayList can not be used for primitive types, like int, char, etc. We need a wrapper class for such cases.
* ArrayList in Java can be seen as a vector in C++.
* ArrayList is not Synchronized. Its equivalent synchronized class in Java is Vector.

