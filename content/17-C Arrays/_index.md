+++
title = "Arrays in C Programming"
weight = 17
chapter = false
pre = " <b> 17. </b> "
+++

#### Arrays in C Programming

Arrays allow you to store multiple values in a single variable, eliminating the need for separate variables for each value.

#### Creating an Array

To create an array in C:
1. Define the data type (e.g., `int`)
2. Specify the array name followed by square brackets `[]`
3. Initialize values using comma-separated list inside curly braces

```c
int myNumbers[] = {25, 50, 75, 100};
```

This creates a variable holding an array of four integers.

#### Accessing Array Elements

Array elements are accessed using index numbers, starting from 0:
- `[0]` refers to the first element
- `[1]` refers to the second element
- And so on...

```c
int myNumbers[] = {25, 50, 75, 100};
printf("%d", myNumbers[0]);  // Outputs 25
```

#### Modifying Array Elements

To change a specific element's value, reference its index number:

```c
int myNumbers[] = {25, 50, 75, 100};
myNumbers[0] = 33;
printf("%d", myNumbers[0]);  // Now outputs 33 instead of 25
```

#### Iterating Through Arrays

Use a `for` loop to iterate through array elements:

```c
int myNumbers[] = {25, 50, 75, 100};
int i;

for (i = 0; i < 4; i++) {
    printf("%d\n", myNumbers[i]);
}
```

#### Specifying Array Size

You can declare an array with a fixed size and add elements later:

```c
// Declare an array of four integers
int myNumbers[4];

// Add elements
myNumbers[0] = 25;
myNumbers[1] = 50;
myNumbers[2] = 75;
myNumbers[3] = 100;
```

**Important Notes:**
- Array size cannot be changed after creation
- You must know the number of elements in advance for proper memory allocation

#### Data Type Consistency

All elements in an array must be of the same data type. Mixing different types can cause errors or unexpected behavior:

```c
// Incorrect usage - mixing integers and floating points
int myArray[] = {25, 50, 75, 3.15, 5.99};  // 3.15 and 5.99 will be truncated to 3 and 5
```

This inconsistency might result in:
- Data truncation
- Compilation errors
- Unexpected behavior

Always ensure all array elements share the same data type for reliable program execution.


#### Get Array Size or Length in C

To get the size of an array, you can use the `sizeof` operator:

#### Basic Size Example

```c
int myNumbers[] = {10, 25, 50, 75, 100};
printf("%lu", sizeof(myNumbers)); // Prints 20
```

#### Understanding the Output

You might wonder why the result shows 20 instead of 5, when the array contains 5 elements?

This occurs because the `sizeof` operator returns the size of a type in bytes. Since an `int` type typically occupies 4 bytes, the calculation becomes:
- 4 bytes × 5 elements = 20 bytes

Understanding the memory size of an array is valuable when working with larger programs that require efficient memory management.

#### Getting Array Length

To find the number of elements in an array, use this formula:

```c
int myNumbers[] = {10, 25, 50, 75, 100};
int length = sizeof(myNumbers) / sizeof(myNumbers[0]);

printf("%d", length);  // Prints 5
```

#### Improving Array Loops

#### Traditional Approach (Less Flexible)

```c
int myNumbers[] = {25, 50, 75, 100};
int i;

for (i = 0; i < 4; i++) {
    printf("%d\n", myNumbers[i]);
}
```

#### Better Approach (Dynamic Size)

```c
int myNumbers[] = {25, 50, 75, 100};
int length = sizeof(myNumbers) / sizeof(myNumbers[0]);
int i;

for (i = 0; i < length; i++) {
    printf("%d\n", myNumbers[i]);
}
```

This improved method is more sustainable as it works with arrays of any size, eliminating the need to manually update the loop condition when the array size changes.

#### Multidimensional Arrays in C

In C programming, you can create arrays with multiple dimensions. While you're familiar with single-dimension arrays, multidimensional arrays allow you to store data in a tabular format with rows and columns.

#### Two-Dimensional Arrays (2D)

A 2D array, also known as a matrix, is an array of arrays. Here's how to declare and initialize a 2D array:

```c
int matrix[2][3] = {
    {1, 4, 2},  // Row 0
    {3, 6, 8}   // Row 1
};
```

The first number `[2]` represents rows, while the second `[3]` represents columns. This creates a table structure:

```c
// Visual representation
1  4  2
3  6  8
```

#### Accessing Elements

To access elements in a 2D array, specify both row and column indices:

```c
int matrix[2][3] = {{1, 4, 2}, {3, 6, 8}};
printf("%d", matrix[0][2]);  // Outputs 2
```

Remember that array indexing starts at 0, so:
- `matrix[0][0]` accesses the first element in the first row
- `matrix[1][2]` accesses the third element in the second row

#### Modifying Elements

You can change values by referencing their indices:

```c
int matrix[2][3] = {{1, 4, 2}, {3, 6, 8}};
matrix[0][0] = 9;  // Changes first element to 9
```

#### Iterating Through 2D Arrays

To access all elements, use nested loops - one for rows and one for columns:

```c
int matrix[2][3] = {{1, 4, 2}, {3, 6, 8}};

for (int i = 0; i < 2; i++) {
    for (int j = 0; j < 3; j++) {
        printf("%d ", matrix[i][j]);
    }
    printf("\n");  // New line after each row
}
```

This code outputs:
```
1 4 2
3 6 8
```

Remember:
- The outer loop `i` iterates through rows
- The inner loop `j` iterates through columns
- Use proper array bounds to avoid accessing invalid memory
- 2D arrays are stored in row-major order in memory