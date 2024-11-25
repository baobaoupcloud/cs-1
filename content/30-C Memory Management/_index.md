+++
title = "C Memory Management"
weight = 30
chapter = false
pre = " <b> 30. </b> "
+++

#### C Memory Management

Memory management is the process of handling how much memory a program uses through different operations.

#### Memory in C

Understanding how memory works in C is important. When you create a basic variable, C will automatically reserve space for that variable. An `int` variable for example, will typically occupy 4 bytes of memory, while a `double` variable will occupy 8 bytes of memory.

You can use the `sizeof` operator to find the size of different types:

#### Example

```c
int myInt;
float myFloat;
double myDouble;
char myChar;

printf("%lu\n", sizeof(myInt));      // 4 bytes
printf("%lu\n", sizeof(myFloat));    // 4 bytes
printf("%lu\n", sizeof(myDouble));   // 8 bytes
printf("%lu\n", sizeof(myChar));     // 1 byte
```

#### Why is it important to know?

If you create a program that occupies too much, or unnecessary memory, it can result in slow and poor performance.

In C, you have to manage memory yourself. It is a complicated task, but is also quite powerful when used correctly:

* Properly managing the computer memory optimizes the performance of the program
* It is useful that you know how to release memory when it is no longer required
* Only use as little memory as necessary for the task

#### Memory Addresses and Pointers

In previous chapters you learned about memory addresses and pointers.

Both have an importance when it comes to memory management, since it is possible to work directly with memory through pointers.

> **Important**: Pointers must be handled with care, since it is possible to damage data stored in other memory addresses.

#### Memory Management Operations

Memory management is the process of handling how much memory a program uses through three main operations:

1. Allocation
2. Reallocation 
3. Deallocation (often referred to as "freeing")
