#


### Pointer

[Original Question](https://www.hackerrank.com/challenges/c-tutorial-pointer)


input
```
4
5
```
output
```
9
1
```
Explain
```
9=4+5
1=|4-5|
```

```c
#include <stdio.h>

void update(int *a,int *b) {
    // Complete this function below
    ????
}

int main() {
    int a, b;
    int *pa = &a, *pb = &b;
    
    scanf("%d %d", &a, &b);
    update(pa, pb);
    printf("%d\n%d", a, b);

    return 0;
}
```

Solution

```c++
void update(int *a,int *b) {
	int ta = *a;
	int tb = *b;
	*a = ta + tb;
	if(ta>tb) *b = ta -tb;
	else *b = tb - ta;
}
```

```c
    // Assign pointer variables
    int a, b;
    int *pa = &a, *pb = &b;

// If you print out the memory address
&a  = 22fe1c     &b = 22fe18
&pa = 22fe10    &pb = 22fe08
pa  = 22fe1c     pb = 22fe18
*pa = 3         *pb = 4
```


---
