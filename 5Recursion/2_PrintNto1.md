### Print N to 1 using Iteration and Recursion

#### Iteration
```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        System.out.println("Enter the number: ");
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        for(int i=n; i>0; i--){
            System.out.print(i + " ");
        }
    }
}
```
Time Complexity: O(N)
Auxiliary Space: O(1)

#### Recursion
```java
// Java program to print all numbers
// between 1 to N in reverse order
class GFG{

// Recursive function to print
// from N to 1
static void PrintReverseOrder(int N)
{
	
	// If N is less than 1 then
	// return static void function
	if (N <= 0)
	{
		return;
	}
	else
	{
		System.out.print(N + " ");

		// Recursive call of the function
		PrintReverseOrder(N - 1);
	}
}

// Driver code
public static void main(String[] args)
{
	int N = 5;

	PrintReverseOrder(N);
}
}
```
Time Complexity: O(N)
Auxiliary Space: O(N)