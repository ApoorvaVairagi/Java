## Analysis of Algorithm
### What is meant by Algorithm Analysis?
Algorithm analysis is an important part of computational complexity theory, which provides theoretical estimation for the required resources of an algorithm to solve a specific computational problem. Analysis of algorithms is the determination of the amount of time and space resources required to execute it.

Why Analysis of Algorithms is important?
- To predict the behavior of an algorithm without implementing it on a specific computer.
- It is much more convenient to have simple measures for the efficiency of an algorithm than to implement the algorithm and test the efficiency every time a certain parameter in the underlying computer system changes.
- It is impossible to predict the exact behaviour of an algorithm. There are too many influencing factors.
- The analysis is thus only an approximation; it is not perfect.
- More importantly, by analyzing different algorithms, we can compare them to determine the best one for our purpose.

Types of Algorithm Analysis:
- Best case
- Worst case
- Average case

### What is Asymptotic Analysis?
Asymptotic analysis is a way to evaluate the performance of an algorithm by **focusing on its growth rate** as the input size (n) becomes very large. It ignores:

- Machine-dependent constants (e.g., hardware speed).
- Programming language differences.
- Smaller terms become insignificant for large inputs.

- **Instead, it focuses on the big picture: how the algorithm scales with input size.**

### How to Perform Asymptotic Analysis?
- Identify the Dominant Term:
- For large inputs, the term with the highest growth rate dominates.
- Ignore constants and lower-order terms.

Example: In c4 * n² + c5 * n + c6, the dominant term is n².

Use Big-O Notation:
- Big-O notation describes the upper bound of an algorithm's growth rate.
Example: If an algorithm takes 3n² + 2n + 1 time, its time complexity is O(n²).

Key Points to Remember
- Focus on Growth Rate: Asymptotic analysis focuses on how the algorithm performs as the input size grows.
- Ignore Constants: Constants (like c1, c2, etc.) are ignored because they don’t affect the growth rate.
- Compare Algorithms: Use asymptotic analysis to compare algorithms and choose the most efficient one.

### Worst, Average and Best Case Time Complexities

We can have three cases to analyze an algorithm:
- Worst Case
- Average Case
- Best Case
Below is the algorithm for performing linear search:
```java
// Linearly search x in arr[]. 
// If x is present then return the index,
// otherwise return -1
int search(int arr[], int n, int x)
{
    int i;
    for (i=0;i<n;i++){
    	if(arr[i]==x){
    		return i;
    	}
    }
    return -1;
 }
 
 //Driver program to test above functions
 int main(){
 	int arr[]={2,8,12,9};
 	int x=12;
 	int n=sizeof(arr)/sizeof(arr[0]);
 	printf("%d is present in %d index",x,search(arr,n,x));
 	getchar();
 	return 0;
 }
 ```
 
**Worst Case Analysis (Usually Done)**: In the worst case analysis, we calculate upper bound on running time of an algorithm. We must know the case that causes the maximum number of operations to be executed. For Linear Search, the worst case happens when the element to be searched (x in the above code) is not present in the array. When x is not present, the search() functions compares it with all the elements of arr[] one by one. Therefore, the worst case time complexity of linear search would be  O(N), where N is the number of elements in the array.

**Average Case Analysis (Sometimes done)**:  In average case analysis, we take all possible inputs and calculate computing time for all of the inputs. Sum all the calculated values and divide the sum by total number of inputs. We must know (or predict) distribution of cases. For the linear search problem, let us assume that all cases are uniformly distributed (including the case of x not being present in array). So we sum all the cases and divide the sum by (N+1). Following is the value of average case time complexity.

**Best Case Analysis (Bogus)**: In the best case analysis, we calculate lower bound on running time of an algorithm. We must know the case that causes minimum number of operations to be executed. In the linear search problem, the best case occurs when x is present at the first location. The number of operations in the best case is constant (not dependent on N). So time complexity in the best case would be 𝛀(1).


Time Complexity Analysis: (In Big-O notation)

1. Best Case: Ω(1), This will take place if the element to be searched is on the first index of the given list. So, the number of comparisons, in this case, is 1.
2. Average Case: O(n), This will take place if the element to be searched is on the middle index of the given list.
3. Worst Case: O(n), This will take place if:
    - The element to be searched is on the last index
    - The element to be searched is not present on the list