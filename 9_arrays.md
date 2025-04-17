## Arrays in Java

### Arrays Introduction
An array is a collection of items of same data type stored at contiguous memory locations. 

This makes it easier to calculate the position of each element by simply adding an offset to a base value, i.e., the memory location of the first element of the array (generally denoted by the name of the array). The base value is index 0 and the difference between the two indexes is the offset.

For simplicity, we can think of an array as a fleet of stairs where on each step is placed a value (let's say one of your friends). Here, you can identify the location of any of your friends by simply knowing the count of the step they are on. 
Remember: Location of next index depends on the data type we use. 

Ways to Create Array in Java
Here are four different ways to create an array of size 3 with elements 10, 20, and 30 in Java:

1. Declare and Allocate Memory Separately:

    In this method, first, you declare an array, then allocate memory for it, and finally assign values to its elements.

    // Declare array

    int a[];

    // Allocate memory for 3 elements

    a = new int[3];
    a[0] = 10;
    a[1] = 20;
    a[2] = 30;

2. Declare and Allocate Memory in One Statement:

    In this method, both the array declaration and memory allocation are done in a single statement.

    // Declare and allocate memory for 3 elements

    int[] a = new int[3];
    a[0] = 10;
    a[1] = 20;
    a[2] = 30;

3. Initialize the Array Inline:

    Here, you can directly initialize the array with values during the declaration.

    // Declare and initialize array with values

    int[] a = { 10, 20, 30 };

4. Use a Loop to Assign Values:

    In this method, the array is declared and memory is allocated first, then a loop is used to assign values to the array elements.

    // Declare and allocate memory for 3 elements

    int[] a = new int[3];
    for (int i = 0; i < a.length; i++) {
    a[i] = (i + 1) * 10;
    }

What are the different operations on the array?
Arrays allow random access to elements. This makes accessing elements by position faster. Hence operation like searching, insertion, and access becomes really efficient. Array elements can be accessed using the loops.

1. Insertion in Array:

    We try to insert a value to a particular array index position, as the array provides random access it can be done easily using the assignment operator.

    Pseudo Code:

    // to insert a value= 10 at index position 2;

    arr[ 2 ] = 10;

    Time Complexity: 

    O(1) to insert a single element
    O(n) to insert all the array elements [where n is the size of the array]

2. Access elements in Array:

    Accessing array elements become extremely important, in order to perform operations on arrays.

    Pseudo Code:

    // to access array element at index position 2, we simply can write

    return arr[ 2 ] ;

    Time Complexity: O(1)


3. Searching in Array: 

    We try to find a particular value in the array, in order to do that we need to access all the array elements and look for the particular value.

    Pseudo Code:

    // searching for value 2 in the array;

    Loop from i = 0 to 5:
        check if  arr[i] = 2:
            return true;

    Time Complexity: O(n), where n is the size of the array.

    Here is the code for working with an array in Java:

```java
class GfG {
    public static void main(String[] args) {

        // Creating an integer array
        // named arr of size 10.
        int[] arr = new int[10];

        // accessing element at 0 index
        // and setting its value to 5.
        arr[0] = 5;

        // access and print value at 0
        // index we get the output as 5.
        System.out.println(arr[0]);
    }
}
```
Output
5

- Unlike C++, arrays are first class objects in Java. For example, in the following program, size of array is accessed using length which is a member of arr[] object. 

```java
// file name: Main.java
public class Main {
    public static void main(String args[]) {
       int arr[] = {10, 20, 30, 40, 50};
       for(int i=0; i < arr.length; i++)
       {
             System.out.print(" " + arr[i]);              
       }
    }
}
```
Output: 
10 20 30 40 50

### Jagged Array in Java

A jagged array is an array of arrays such that member arrays can be of different sizes, i.e., we can create a 2-D array but with a variable number of columns in each row.

Declaration and Initialization of Jagged array :

data_type array_name[][] = new data_type[n][];
array_name[] = new data_type[n1]
array_name[] = new data_type[n2]
array_name[] = new data_type[n3]
.
.
.
array_name[] = new data_type[nk]
where n = Total number of rows and ni = number of columns in i-th row

 

Alternative, ways to Initialize a Jagged array :

int arr_name[][] = new int[][] { new int[] { 10, 20, 30, 40 },
new int[] { 50, 60, 70, 80, 90, 100 },
new int[] { 110, 120 } };

OR

int[][] arr_name = { new int[] { 10, 20, 30, 40 },
new int[] { 50, 60, 70, 80, 90, 100 },
new int[] { 110, 120 } };

OR

int[][] arr_name = { { 10, 20, 30, 40 },
{ 50, 60, 70, 80, 90, 100 },
{ 110, 120 } };

Following is example where i'th row has i columns, i.e., the first row has 1 element, the second row has two elements and so on.

```java
// Program to demonstrate 2-D jagged array in Java
class GfG {
    public static void main(String[] args) {
        int m = 3;

        // Declaring 2-D array with 3 rows
        int arr[][] = new int[m][];
        
        // Creating a 2D array such that first row
        // has 1 element, second row has two
        // elements and so on.
        for (int i = 0; i < arr.length; i++) {
            arr[i] = new int[i + 1];

            for (int j = 0; j < arr[i].length; j++) {
                arr[i][j] = i;

                System.out.print(arr[i][j] + " ");
            }

            System.out.println();
        }
    }
}
```
Output
0 
1 1 
2 2 2 


### Multidimensional Arrays

Multidimensional Arrays can be defined in simple words as **array of arrays**. Data in multidimensional arrays are stored in tabular form (in row major order). 

Syntax:

data_type[1st dimension][2nd dimension][]..[Nth dimension] array_name = new data_type[size1][size2]....[sizeN]; 

where:

data_type: Type of data to be stored in the array. For example: int, char, etc.
dimension: The dimension of the array created. For example: 1D, 2D, etc.
array_name: Name of the array
size1, size2, ..., sizeN: Sizes of the dimensions respectively.
Examples: 

Two dimensional array:
int[][] twoD_arr = new int[10][20];

Three dimensional array:
int[][][] threeD_arr = new int[10][20][30];


Size of multidimensional arrays: The total number of elements that can be stored in a multidimensional array can be calculated by **multiplying the size of all the dimensions**.

For example:
The array int[][] x = new int[10][20] can store a total of (10*20) = 200 elements.
Similarly, array int[][][] x = new int[5][10][20] can store a total of (5*10*20) = 1000 elements.

#### Two - dimensional Array (2D-Array)

Two - dimensional array is the simplest form of a multidimensional array. A two - dimensional array can be seen as an array of one - dimensional array for easier understanding. 

Indirect Method of Declaration:

Declaration Syntax:
data_type[][] array_name = new data_type[number of rows][number of columns];

For example:
int[][] arr = new int[10][20];

Initialization Syntax:
array_name[row_index][column_index] = value;

For example:
arr[0][0] = 1;


Direct Method of Declaration:

Declaration as well as Initialization Syntax:
data_type[][] array_name = { {valueR1C1, valueR1C2, ....},
{valueR2C1, valueR2C2, ....} };

For example:
int[][] arr = {{1, 2}, {3, 4}};


Accessing Elements of Two-Dimensional Arrays
Elements in two-dimensional arrays are commonly referred by arr[i][j] where 'i' is the row number and 'j' is the column number.

Representation of 2D array in Tabular Format:
A two - dimensional array can be seen as a table with 'n' rows and 'm' columns where the row number ranges from 0 to (n-1) and column number ranges from 0 to (m-1).

#### Jagged Array - refer above notes

### Three - dimensional Array (3D-Array)

Three - dimensional array is a complex form of a multidimensional array. A three - dimensional array can be seen as an array of two - dimensional array for easier understanding.

Indirect Method of Declaration:

Declaration Syntax:
data_type[][][] array_name = new data_type[x][y][z];

For example:
int[][][] arr = new int[10][20][30];

Initialization Syntax:
array_name[array_index][row_index][column_index] = value;

For example:
arr[0][0][0] = 1;


Direct Method of Declaration:

Declaration as well as Initialization Syntax:
data_type[][][] array_name = { { {valueA1R1C1, valueA1R1C2, ....},
{valueA1R2C1, valueA1R2C2, ....} },
{ {valueA2R1C1, valueA2R1C2, ....},
{valueA2R2C1, valueA2R2C2, ....} } };

For example:
int[][][] arr = { {{1, 2}, {3, 4}}, {{5, 6}, {7, 8}} };

Accessing Elements of Three-Dimensional Arrays
Elements in three-dimensional arrays are commonly referred by arr[i][j][k] where 'i' is the array number, 'j' is the row number and 'k' is the column number.

- Representation of 3D array in Tabular Format:
A three-dimensional array can be visualized as a table of arrays with n rows, m columns, and l arrays. The row numbers range from 0 to (n-1), the column numbers range from 0 to (m-1), and the array numbers range from 0 to (l-1)

Print 3D array in tabular format: To output all the elements of a Three-Dimensional array, use nested for loops. For this three for loops are required, One to traverse the arrays, second to traverse the rows and another to traverse columns.
Example: 

```java
// Java Code to print a Three-dimensional Array
class GfG {
    public static void main(String[] args) {

        // Initializing a 3D array with 2 arrays, each containing 2 rows and 2 columns
        int[][][] arr = { 
            { { 1, 2 }, { 3, 4 } },  // First 2D array
            { { 5, 6 }, { 7, 8 } }   // Second 2D array
        };

        // Outer loop iterates over the 2 arrays
        for (int i = 0; i < 2; i++) {

            // Middle loop iterates over the rows in each 2D array
            for (int j = 0; j < 2; j++) {

                // Inner loop iterates over the columns in each row
                for (int k = 0; k < 2; k++) {

                    // Printing each element in the 3D array
                    System.out.print(arr[i][j][k] + " ");
                }

                // New line after printing all columns in a row
                System.out.println();
            }

            // New line after printing all rows in one 2D array
            System.out.println();
        }
    }
}
```

Output
1 2 
3 4 

5 6 
7 8 