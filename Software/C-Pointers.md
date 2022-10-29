---
layout: default
title: C Pointers
has_children: false
permalink: software/c-pointer
parent: Software
---

# C Pointers

Here, we are always showing MWEs, minimal working examples.
This means, that (unless I did something wrong), you can always copy the code and compile it, to see what it does.
If you don't have a compiler to your hand, you can use [replit.com](https://replit.com/) to compile and run this code online.
Just as a hint: If you don't want to create an account on this page, just go to the bottom and select your desired language there, this will give you the same functionality without an account (except saving code in your account of course).

## Theory

- Create Variable using `type name` (e.g. `int number`)
- Create a pointer using `type *name` (e.g. `int *numberPointer`)
  - Although it looks more intuitive to add the star to the type (which I also do most of the times), the star belongs to the var name. You will notice this if you create multiple vars, e.g. using `int* a, b;`, which would create `a` as a pointer and `b` as a normal int.
- Get a pointer to where a variable is stored: `&name` (e.g. `int number; int *numPointer = &number;`)
- Dereference a pointer (i.e. read the value which the pointer points to) using `*name` (e.g. `int *numberPointer; int number = *numberPointer`)

There is also a function called `malloc(size)`, which allows to allocate (reserve) some memory.
It returns the address of the first reserved byte, so you can use the following `size` bytes as you like.
Afterwards, you can free this memory using `free(addr)`, where `addr` is one address inside the reserved region (you don't have to provide the first address).

## Examples

### Integer

```c
#include <stdio.h>

int main() {
    int number = 8192;
    printf("Print number: %d\n", number);

    int* numberPointer = &number;
    printf("Print number, from dereferenced pointer: %d\n", *numberPointer);
    printf("Meanwhile, if you print the pointer: %p\n", numberPointer);

    return 0;
```

The `return 0;` at the end has nothing to do with the logic of our program, but 0 is the exit code of our program.
The exit code basically tells the shell if everything went well (0), if our application crashed or whatever happened (other values than 0, in fact, all these numbers have predefined meanings).
This is not required for this basic example, but should be considered as best-practice and thus be included.

### malloc

```c
#include <stdio.h>

int main() {
    int *numberPointer = (int*) malloc(sizeof(int));    // Allocates memory for one int (4 bytes)
    *numberPointer = 8192;                              // writes value 8192 into allocated memory
    printf("Print number: %d\n", *numberPointer);
    printf("This number is stored at: %p\n", numberPointer);

    int number = *numberPointer;
    printf("Print number, which we got from dereferenced pointer: %d\n", number);

    return 0;
}
```