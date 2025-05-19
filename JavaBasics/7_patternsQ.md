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

Q.
```java
// For n = 3, print this pattern
//* * *
//* * * 
//* * *

int i=1;
while(i<=n){
    int j=1;
    while(j<=n){
        System.out.print("*");
        j++;
    }
    System.out.println();
    i++;
}
```

Q.
```java
// For n = 4, print this pattern
//   *
//  ***
// *****
//*******

int i=1;
while(i<=n){
    int space = n-i;
    while(space>0){
        System.out.print(" ");
        space--;
    }
    int star=i;
    while(star>0){
        System.out.print("*");
        star--;
    }
    int trailingStar=i-1;
    while(trailingStar>0){
        System.out.print("*");
        trailingStar--;
    }
    System.out.println();
    i++;
}