Q. 
```java
// For n = 3, print this pattern
//*
//* * 
//* * *

int i=1;
while(i<=n){
    int j=1;
    while(j<=i){
        System.out.print("*");
        j++;
    }
    i++;
    System.out.println();
}
```

Q.
```java
// For n = 3, print this pattern
//    *
//  * * 
//* * *

int i=1;
while(i<=n){
    int j=1;
    int space = n-i;
    while(space>0){
        System.out.print(" ");
        space--;
    }

    while(j<=i){
        System.out.print("*");
        j++;
    }
    i++;
    System.out.println();
}
```