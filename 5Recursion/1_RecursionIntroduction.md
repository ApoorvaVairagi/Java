### What is Recursion?
Recursion is a way to solve a problem or way to write a program in which a function calls itself directly or indirectly. Using recursive algorithms, certain problems like Towers of Hanoi (TOH), Inorder/Preorder/Postorder Tree Traversals and DFS of Graph, can be solved quite easily.

In direct recursion, function calls itself while in indirect recursion the function fun1 calls another function fun2 which calls the fun1 function.

### What is the need of base condition in recursion?
The above functions have an issue - they recursively call themselves without any breaking condition, leading to StackOverflow or Segmentation Fault. In a recursive program, the solution to the base case is provided and the solution of bigger problem is expressed in terms of smaller problems.

```java
#include <iostream>
using namespace std;

void fun1(int n)
{
    if (n == 0) // base case
        return;

    cout << "GFG" << endl; 
    fun1(n - 1);
}

int main() {
	fun1(2);
	return 0;
}
```

### How memory is allocated to different function calls in recursion?

When any function is called from main(), the memory is allocated to it on **stack**. A recursive function calls itself, the memory for the called function is allocated on top of memory allocated to the calling function and a different copy of local variables is created for each function call. When the base case is reached, the function returns its value to the function by whom it is called and memory is de-allocated and the process continues.

- Disadvantage of Recursion: Note that both recursive and iterative programs have the same problem-solving powers, i.e., every recursive program can be written iteratively and vice versa. A recursive program has greater space requirements than an iterative program as all functions will remain in the stack until the base case is reached. A recursive program also has greater time requirements because of function calls and return overhead. 

- Advantages of Recursion: Recursion provides a clean and simple way to write code. Some problems are inherently recursive like tree traversals, Tower of Hanoi, etc. For such problems, it is preferred to write recursive code. We can write such codes also iteratively with the help of the stack data structure.