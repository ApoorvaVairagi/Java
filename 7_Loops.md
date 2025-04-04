for loops:
for loop provides a concise way of writing the loop structure. Unlike a while loop, a for statement consumes the initialization, condition, and increment/decrement in one line thereby providing a shorter, easy-to-debug structure of looping. 

Syntax:

for (initialization condition; testing condition; increment/decrement)
{
statement(s)
}

Initialization condition: Here, we initialize the loop variable in use. It marks the start of a for loop. An already declared variable can be used or a variable can be declared, local to loop only.
Testing Condition: It is used for testing the exit condition for a loop. It must return a boolean value. It is also an Entry Control Loop as the condition is checked prior to the execution of the loop statements.
Statement execution: Once the condition is evaluated to be true, the statements in the loop body are executed.
Increment/ Decrement: It is used for updating the variable for the next iteration.
Loop termination: When the condition becomes false, the loop terminates marking the end of its life cycle.


For-each is another array traversing technique like for loop, while loop, do-while loop introduced in Java5.  

It starts with the keyword for like a normal for-loop.
Instead of declaring and initializing a loop counter variable, you declare a variable that is the same type as the base type of the array, followed by a colon, which is then followed by the array name.
In the loop body, you can use the loop variable you created rather than using an indexed array element. 
It's commonly used to iterate over an array or a Collections class (eg, ArrayList)

Syntax: 

for (type var : array)
{
statements using var;
}


is equivalent to: 

for (int i = 0; i < arr.length; i++)
{
type var = arr[i];
statements using var;
}

Limitations of for-each loop 

1. For-each loops are not appropriate when you want to modify the array:
 

for (int num : marks)
{
// only changes num, no effect on array element
num = num * 2;
}

 
2. For-each loops do not keep track of index. So we can not obtain array index using For-Each loop 
 

for (int num : numbers)
{
if (num == target)
{
return ???; // as we do not know the index of num
}
}

 
3.  For-each only iterates forward over the array in single steps 
 

// cannot be converted to a for-each loop
for (int i = numbers.length-1; i > 0; i--)
{
System.out.println(numbers[i]);
}


4. For-each cannot process two decision making statements at once 
 

// cannot be easily converted to a for-each loop
for (int i=0; i<numbers.length; i++)
{
if (numbers[i] == arr[i])
{
.......
}
}

     
5. For-each also has some performance overhead over simple iteration:
   

### Break and Continue
Continue - If you hit the Continue statement, the statements after it are skipped and the loop continues for the next iteration.

```java
class Test{
  public static void main(String[] args){
    for(int i=0; i<5; i++){
      if(i==3){
      continue;
      }
      System.out.print(i+" ");
    }
  }
}
```
Output - 0 1 2 4

```java
class Test{
  public static void main(String[] args){
    int i=0;
    while(i<3){
      i++;
      System.out.println("Before "+i);
      if(i==2)
        continue;
      System.out.println("After "+i);
  }
}
```
Output -
Before 1
After 1
Before 2
Before 3
After 3

Break - As you hit this break statement the loop will not continue after that. It is used to stop the loop from further execution.

```java
class Test{
  public static void main(String[] args){
    int i;
    for(i=0; i<5; i++){
      if(i==3)
        break;
      System.out.println(i);
    }
  }
}
```
Output - 0 1 2

-> Q. 



