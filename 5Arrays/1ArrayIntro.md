An array is a collection of items of the same variable type stored that are stored at contiguous memory locations. It’s one of the most popular and simple data structures and is often used to implement other data structures. Each item in an array is indexed starting with 0.

### Implementing Arrays in Java
Arrays in Java are used to store a group of elements of same data type at contiguous memory locations.

The general form of Array declaration in Java is:

type array-name[];

OR

type[] array-name;


An array declaration has two components: the type and the name. Type declares the element type of the array. The element type determines the data type of each element that comprises the array. Like an array of type int, we can also create an array of other primitive data types such as char, float, double..etc, or user-defined data type(objects of a class). Thus, the element type for the array determines what type of data the array will hold.

For Example:
// both are valid declarations
int intArray[]; 
or int[] intArray; 

byte byteArray[];
short shortsArray[];
boolean booleanArray[];
long longArray[];
float floatArray[];
double doubleArray[];
char charArray[];

#### Instantiating an Array: When an array is declared, only a reference of the array is created. To actually create or give memory to the array, you create an array like this:

array-name = new type [size];

Example:
int intArray[];    //declaring array
intArray = new int[20];  // allocating memory to array


OR
int[] intArray = new int[20]; // combining both statements in one

## ArrayList in Java

ArrayList is a part of the collection framework and is present in java.util package. It provides us dynamic arrays in Java. Though it may be slower than standard arrays, it can be helpful in programs where a lot of array manipulation is needed.

Constructors in Java ArrayList:
- ArrayList(): This constructor is used to build an empty array list.
- ArrayList(Collection c): This constructor is used to build an array list initialized with the elements from collection c.
- ArrayList(int capacity): This constructor is used to build an array list with the specified initial capacity.


Creating a generic integer ArrayList:
ArrayList arrli = new ArrayList();

## Vector Class in Java

The Vector class implements a growable array of objects. Vectors basically falls in legacy classes but now it is fully compatible with collections.
Vector implements a dynamic array that means it can grow or shrink as required. Like an array, it contains components that can be accessed using an integer index.
They are very similar to ArrayList but Vector is synchronized and has some legacy method, which the collection framework does not contain.
It extends AbstractList and implements List interfaces.


Constructor:
Vector(): Creates a default vector of initial capacity 10.
Vector(int size): Creates a vector whose initial capacity is specified by size.
Vector(int size, int incr): Creates a vector whose initial capacity is specified by size and the increment is specified by incr. It specifies the number of elements to allocate each time a vector is resized upwards.
Vector(Collection c): Creates a vector that contains the elements of collection c.

```java
// Java code to illustrate Vector 

import java.util.*; 
class Vector_demo { 
    public static void main(String[] arg) 
    { 
        // Create a vector 
        Vector<Integer> v = new Vector<Integer>(); 
    
        // Insert elements in the Vector
        v.add(1); 
        v.add(2); 
        v.add(3); 
        v.add(4); 
        v.add(3); 
    
        // Print the Vector
        System.out.println("Vector is " + v); 
    } 
}
```