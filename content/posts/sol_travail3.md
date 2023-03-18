---
title: "Sorting Algorithms"
date: 2023-03-18T19:29:48+01:00
draft: false
tags:
- C
- Algorithms
---

## Function N°01: Selection Sort

### Source Code:
```c
#include <stdio.h>

void f1(int T[7])
{
    int i, j, tmp;
    for (i = 0; i < 6; i++) {
        for (j = i+1; j < 7; j++){
            if (T[j] > T[i]){
				tmp = T[j];
				T[j] = T[i];
				T[i] = tmp;
			}
		}
	}
}
int main()
{
	int T[7]={1, 5, 3, 2, 7, 6, 4};
	int i;
	printf("Before\n");
	for(i=0;i<7;i++){
		printf("T[%d] = %d\n", i+1, T[i]);
	}
	f1(T);
	printf("After\n");
	for(i=0;i<7;i++){
		printf("T[%d] = %d\n", i+1, T[i]);
	}
	return 0;
}
```
### After Compiling: 
```
Before
T[1] = 1
T[2] = 5
T[3] = 3
T[4] = 2
T[5] = 7
T[6] = 6
T[7] = 4
After
T[1] = 7
T[2] = 6
T[3] = 5
T[4] = 4
T[5] = 3
T[6] = 2
T[7] = 1
```

## Function N°02: Bubble Sort

### Source Code:
```c
#include <stdio.h>
void f2(int T[7]) {
    int i, j, tmp;
    for (i = 0; i < 6; i++) {
        for (j = 0; j < 6-i; j++) {
            if (T[j+1] > T[j]) {
                tmp = T[j];
                T[j] = T[j+1];
                T[j+1] = tmp;
            }
        }
    }
}
int main()
{
	int T[7]={1, 5, 3, 2, 7, 6, 4};
	int i;
	printf("Before\n");
	for(i=0;i<7;i++){
		printf("T[%d] = %d\n", i+1, T[i]);
	}
	f2(T);
	printf("After\n");
	for(i=0;i<7;i++){
		printf("T[%d] = %d\n", i+1, T[i]);
	}
	return 0;
}
```

### After Compiling:

```
Before
T[1] = 1
T[2] = 5
T[3] = 3
T[4] = 2
T[5] = 7
T[6] = 6
T[7] = 4
After
T[1] = 7
T[2] = 6
T[3] = 5
T[4] = 4
T[5] = 3
T[6] = 2
T[7] = 1
```

## Function N°03: Insertion sort

### Source Code:
```c
#include <stdio.h>

void f3(int T[7])
{
    int i, j, tmp;
    for (i = 1; i < 7; i++) {
        tmp = T[i];
        j = i - 1;

        while (j >= 0 && T[j] < tmp) {
            T[j+1] = T[j];
	    j--;
        }
        T[j+1] = tmp;
    }
}
int main()
{
	int T[7]={1, 5, 3, 2, 7, 6, 4};
	int i;
	printf("Before\n");
	for(i=0;i<7;i++){
		printf("T[%d] = %d\n", i+1, T[i]);
	}
	f3(T);
	printf("After\n");
	for(i=0;i<7;i++){
		printf("T[%d] = %d\n", i+1, T[i]);
	}
	return 0;
}
```
### After Compiling:

```
Before
T[1] = 1
T[2] = 5
T[3] = 3
T[4] = 2
T[5] = 7
T[6] = 6
T[7] = 4
After
T[1] = 7
T[2] = 6
T[3] = 5
T[4] = 4
T[5] = 3
T[6] = 2
T[7] = 1
```
