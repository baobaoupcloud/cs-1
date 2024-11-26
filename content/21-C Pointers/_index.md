+++
title = "Switch Statement in C"
weight = 21
chapter = false
pre = " <b> 21. </b> "
+++

#### Pointers in C Programming

#### Creating Pointers

In the previous chapter, you learned that we can get the memory address of a variable using the reference operator `&`:

```c
int myAge = 43;     // an int variable

printf("%d", myAge);   // Outputs the value of myAge (43)
printf("%p", &myAge);  // Outputs the memory address of myAge (0x7ffe5367e044)
```

A pointer is a variable that stores the memory address of another variable as its value. A pointer variable points to a data type (like `int`) of the same type and is created with the `*` operator. The address of the variable you're working with is assigned to the pointer:

```c
int myAge = 43;      // An int variable
int* ptr = &myAge;   // A pointer variable named ptr that stores the address of myAge

// Output the value of myAge (43)
printf("%d\n", myAge);

// Output the memory address of myAge (0x7ffe5367e044)
printf("%p\n", &myAge);

// Output the memory address of myAge with the pointer (0x7ffe5367e044)
printf("%p\n", ptr);
```

#### Understanding the Example

1. Create a pointer variable named `ptr` that points to an `int` variable (`myAge`)
2. The pointer's type must match the variable type you're working with (`int` in this example)
3. Use the `&` operator to store the memory address of the `myAge` variable and assign it to the pointer
4. Now, `ptr` holds the value of `myAge`'s memory address

#### Dereference Operator

While we use the pointer variable to get the memory address of a variable (with the `&` reference operator), we can also get the value of the variable the pointer points to using the `*` operator (the dereference operator):

```c
int myAge = 43;      // Variable declaration
int* ptr = &myAge;   // Pointer declaration

// Reference: Output the memory address of myAge with the pointer (0x7ffe5367e044)
printf("%p\n", ptr);

// Dereference: Output the value of myAge with the pointer (43)
printf("%d\n", *ptr);
```

**Note**: The `*` sign serves two different purposes:
- In declaration (`int* ptr`): Creates a pointer variable
- Outside declaration: Acts as a dereference operator

#### Alternative Pointer Declaration Syntax

There are two valid ways to declare pointer variables in C:
```c
int* myNum;
int *myNum;
```

#### Important Notes on Pointers

Pointers are a distinctive feature of C that sets it apart from languages like Python and Java. They are crucial because:

1. They allow direct manipulation of computer memory data
2. They can reduce code and improve performance
3. They're essential for implementing data structures like:
   - Lists
   - Trees
   - Graphs
4. They're required for certain operations like:
   - File handling
   - Memory management

**Warning**: Handle pointers carefully, as they can potentially damage data stored in other memory addresses if not used properly.


#### Pointers & Arrays in C

#### Arrays and Memory Addresses

When working with arrays in C, you can use pointers to access array elements. Let's explore this concept:

#### Basic Array Example
```c
int myNumbers[4] = {25, 50, 75, 100};
int i;

// Traditional array iteration
for (i = 0; i < 4; i++) {
    printf("%d\n", myNumbers[i]);
}
```

This produces:
```
25
50
75
100
```

#### Memory Addresses of Array Elements
```c
int myNumbers[4] = {25, 50, 75, 100};
int i;

for (i = 0; i < 4; i++) {
    printf("%p\n", &myNumbers[i]);
}
```

Output example:
```
0x7ffe70f9d8f0
0x7ffe70f9d8f4
0x7ffe70f9d8f8
0x7ffe70f9d8fc
```

Notice how each address differs by 4 bytes - this is because an integer typically occupies 4 bytes of memory:

```c
// Demonstrating integer size
int myInt;
printf("%lu", sizeof(myInt));  // Outputs: 4

// Array size demonstration
int myNumbers[4] = {25, 50, 75, 100};
printf("%lu", sizeof(myNumbers));  // Outputs: 16 (4 bytes * 4 elements)
```

#### Understanding Array-Pointer Relationship

In C, an array name acts as a pointer to its first element. Here's how we can verify this:

```c
int myNumbers[4] = {25, 50, 75, 100};

// Both print the same address
printf("%p\n", myNumbers);        // Array name
printf("%p\n", &myNumbers[0]);    // Address of first element
```

#### Accessing Array Elements Using Pointers

You can use pointer arithmetic to access array elements:

```c
int myNumbers[4] = {25, 50, 75, 100};

// Access first element
printf("%d\n", *myNumbers);           // Outputs: 25

// Access subsequent elements
printf("%d\n", *(myNumbers + 1));     // Outputs: 50
printf("%d\n", *(myNumbers + 2));     // Outputs: 75
```

#### Iterating Through Arrays with Pointers

```c
int myNumbers[4] = {25, 50, 75, 100};
int *ptr = myNumbers;
int i;

for (i = 0; i < 4; i++) {
    printf("%d\n", *(ptr + i));
}
```

#### Modifying Array Elements with Pointers

```c
int myNumbers[4] = {25, 50, 75, 100};

// Modify elements using pointers
*myNumbers = 13;              // Change first element
*(myNumbers + 1) = 17;       // Change second element

printf("%d\n", *myNumbers);           // Outputs: 13
printf("%d\n", *(myNumbers + 1));     // Outputs: 17
```

#### Important Notes

1. Pointer arithmetic is particularly efficient for:
   - Large arrays
   - Two-dimensional arrays
   - String manipulation (strings are character arrays)

2. **Warning**: Handle pointers with care as improper use can overwrite memory and cause undefined behavior.

3. The pointer-based approach might seem complex for simple arrays, but it becomes valuable when working with larger data structures and complex memory manipulations.

