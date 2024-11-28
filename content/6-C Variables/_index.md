+++
title = "C Variables"
weight = 6
chapter = false
pre = " <b> 6. </b> "
+++

#### Overview

Variables serve as containers for storing data values, such as numbers and characters in C programming. Understanding how to work with variables is fundamental to C programming.

#### Basic Variable Types

#### Integer (int)
- Stores whole numbers without decimals
- Examples: `123`, `-123`
- No fractional or decimal values

#### Float (float) 
- Stores numbers with decimal points
- Examples: `19.99`, `-19.99`
- Suitable for precise calculations

#### Character (char)
- Stores single characters
- Must be surrounded by single quotes
- Examples: `'a'`, `'B'`

#### Variable Declaration

#### Basic Syntax
```c
type variableName = value;
```

#### Example Declarations
```c
// Direct initialization
int myNum = 15;

// Declaration and assignment separately
int myNum;       // Declare variable
myNum = 15;      // Assign value
```

#### Variable Output

#### Using printf()
The `printf()` function is used to display variable values in C.

```c
// Incorrect way
int myNum = 15;
printf(myNum);    // This will not work

// Correct way
int myNum = 15;
printf("%d", myNum);    // This will display 15
```

#### Format Specifiers
When outputting variables, use these format specifiers:
- `%d` - for integers
- `%f` - for floats
- `%c` - for single characters

#### Advanced Format Specifiers

#### Format Specifiers Table
| Specifier | Data Type | Example Value |
|-----------|-----------|---------------|
| %d | int | 42 |
| %f | float | 3.14 |
| %c | char | 'A' |
| %s | string | "Hello" |
| %lf | double | 3.14159265359 |
| %x or %X | hexadecimal | 0xFF |
| %o | octal | 075 |
| %p | pointer | 0x7ffee2d7e8f0 |

#### Width and Precision Example
```c
float pi = 3.14159;
printf("Default: %f\n", pi);        // 3.141590
printf("Width 8: %8f\n", pi);       //  3.141590
printf("Precision 2: %.2f\n", pi);  // 3.14
```

#### Best Practices

1. Choose descriptive variable names
2. Initialize variables when declaring them
3. Use appropriate data types for your values
4. Follow consistent naming conventions

#### Common Mistakes to Avoid

- Forgetting to initialize variables
- Using variables before declaring them
- Trying to print variables without format specifiers
- Using incorrect format specifiers for data types

#### Practice Exercise

Create a program that utilizes different variable types:

```c
#include <stdio.h>

int main() {
    // Variable declarations
    int age = 25;
    float height = 5.9;
    char grade = 'A';

    // Output with proper format specifiers
    printf("Age: %d\n", age);
    printf("Height: %.1f\n", height);
    printf("Grade: %c\n", grade);

    return 0;
}
```

#### Real-World Examples

#### Student Data Management
```c
// Student data storage
int studentID = 15;
int studentAge = 23;
float studentFee = 75.25;
char studentGrade = 'B';

// Print student information
printf("Student ID: %d\n", studentID);
printf("Student Age: %d\n", studentAge);
printf("Student Fee: %.2f\n", studentFee);
printf("Student Grade: %c\n", studentGrade);
```

#### Rectangle Area Calculator
```c
// Variables for rectangle dimensions
int length = 4;
int width = 6;
int area;

// Calculate area
area = length * width;

// Display results
printf("Length: %d\n", length);
printf("Width: %d\n", width);
printf("Area: %d square units\n", area);
```

#### Multiple Variable Declarations

You can declare multiple variables in several ways:

```c
// Comma-separated declaration
int x = 5, y = 6, z = 50;

// Same value to multiple variables
int a, b, c;
a = b = c = 100;

// Separate lines for clarity
int height = 180;
int weight = 75;
int age = 25;
```

#### Conclusion

Understanding variables and their proper usage is crucial for C programming. Remember to:
- Choose appropriate data types
- Initialize variables before use
- Use correct format specifiers
- Follow consistent naming conventions
- Practice with real-world examples

For more advanced topics and exercises, check out our next section on control structures in C.