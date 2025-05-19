## Practice Questions

### Factorial of a Number
```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        System.out.println("Enter n: ");
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int i=1;
        int factorial=1;
        while(i<=n){
            factorial*=i;
            i++;
        }
        System.out.println("Factorial of n: "+ factorial);
    }
}
```

### GCD (Greatest Common Divisor) of two numbers.
Steps:-
1. Find the smaller of the two numbers. Math.min(a,b).
2. Iterate from 1 to the Smaller of the two numbers, find the number which divides both the numbers.

```java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {
        System.out.println("Enter n: ");
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        int ans=1;
        int x=Math.min(a,b);
        for(int i=1; i<=x; i++){
            if((a%i==0) && (b%i==0)){
                ans = i;
            }
        }
        System.out.print(ans);
    }
}
```
