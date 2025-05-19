## Java Flow Controls

### If-Else in Java
Also known as the conditional statements.

if(condition){
    // Statement to be executed when condition is true.
}
else{
    // Statement to be executed when condition is not true.
}

-> Q.Given a number n, find if the number is even or odd.
```java
import java.util.Scanner;
class Main {
    public static void main(String[] args) {
        System.out.println("Enter the number: ");
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        if(n%2==0){
            System.out.println("Even");
        }
        else{
            System.out.println("Odd");
        }
    }
}
```

-> Q.Take a number from the user, print sum of the first n natural numbers, if the user enters a negative number show error and exit.

```java
import java.util.Scanner;
class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        System.out.println("Please enter a number: ");
        int n = sc.nextInt();
        if(n < 0){
            System.out.println("Invalid Input");
            return;
        }
        System.out.println(n*(n+1)/2);
    }
}
```
### If-Else Ladder

if(condition)
else if(condition)
else if(condition)
.
.
.
else

```java
import java.util.Scanner;
class Test{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        System.out.println("Please enter a number:");
        int n = sc.nextInt();
        if(n>0){
            System.out.print("Positive ");
            if(n%2==0){
                System.out.print("Even\n");
            }
            else{
                System.out.print("Odd\n");
            }
        }
        else if(n<0){
            System.out.print("Negative ");
            if(n%2==0){
                System.out.print("Even\n");
            }
            else{
                System.out.print("Odd\n");
            }
        }
        else{
            System.out.print("Zero ");
        }
    }
}
```
---

### Switch in Java

```java
import java.util.Scanner;
class Main{
    public static void main(String[] args){
        int x=0, y=0;
        System.out.println("Enter a move: ");
        Scanner sc = new Scanner(System.in);
        char move = sc.next.chrAt(0);

        switch(move){
            case 'L':
                x--;
                break;
            case 'R':
                x++;
                break;
            case 'U':
                y++;
                break;
            case 'D':
                y--;
                break;
            default:
                System.out.println("Invalid");
        }
    }
}
```

In java, you can have strings also in switch, this is there in java after java7 onwards, In C, C++ this is not allowed.
These can also be done using the if-else. They provide the same funcionality. To use these or that, you can go with the logic if you have a single variable and multiple branchings go with switch. As you have to type less and the code is neat. When you have different conditions use if-else.

-> Q.Largest of three numbers

```java
import java.util.Scanner;
class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int x = sc.nextInt();
        int y = sc.nextInt();
        int z = sc.nextInt();

        if(x>=y && x>=y){
            System.out.println(x);
        }
        else if(y>=x && y>=z){
            System.out.println(y);
        }
        else{
            System.out.println(z);
        }
    }
}
```

--> Q.Using Math.max function


```java
import java.util.Scanner;
class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int x = sc.nextInt();
        int y = sc.nextInt();
        int z = sc.nextInt();

        int ans = Math.max(x, y);
        int ans2 = Math.max(ans, z);
        System.out.println(ans2);
    }
}
```

-> Q.LEAP Year
Rule 1: Divisible by 4, but not divisible by 100. eg. 1952, 1956, 1960
Rule 2: Divisible by 400. eg. 2000, 2400, 2800
Note: Year like 2100, 2300, 2200 are not leap years.

```java
import java.util.Scanner;
class Main{
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        int year = sc.nextInt();
        
        if(year%4 == 0 && year %100 !=0){
            System.out.println("Yes");
        }
        else if(year%400==0){
            System.out.println("Yes");
        }
        else{
            System.out.println("No");
        }
    }
}
```

-> Q.Calculator

```java
import java.util.Scanner;
class Main{
    public static void main(String[] args){
        System.out.println("SELECT THE OPERATION:\n 1.Addition\n2.Substraction\n3.Multiplication");
        int operation = sc.nextInt();
        if(operation!=1&&operation!=2&&operation!=3){
            System.out.println("Invalid Input");
            return;
        }
        else{
            System.out.println("Enter first number");
            int a = sc.nextInt();
            System.out.println("Enter second number");
            int b = sc.nextInt();
        }

        if(operation==1){
            System.out.println(a+b);
        }
        else if(operation==2){
            System.out.println(a-b);
        }
        else if(operation==3){
            
            System.out.println(a*b);
        }
    }
}
```
























