+++
title = "C Function Declaration and Definition"
weight = 25
chapter = false
pre = " <b> 25. </b> "
+++

#### C Function Declaration and Definition

#### Basic Function Structure
A function in C consists of two main parts:
1. **Declaration**: Specifies the function's name, return type, and parameters (if any)
2. **Definition**: Contains the body of the function (code to be executed)

#### Basic Function Example
```c
// Create a function
void myFunction() {
  printf("I just got executed!");
}

int main() {
  myFunction(); // call the function
  return 0;
}
```

#### Separating Declaration and Definition
For better code organization and optimization, it's recommended to separate function declarations and definitions:

```c
// Function declaration
void myFunction();

// The main method
int main() {
  myFunction();  // call the function
  return 0;
}

// Function definition
void myFunction() {
  printf("I just got executed!");
}
```

#### Working with Parameters and Return Values
When working with function parameters and return values, maintain the same separation principle:

```c
// Function declaration
int myFunction(int x, int y);

// The main method
int main() {
  int result = myFunction(5, 3); // call the function
  printf("Result is = %d", result);
  return 0;
}

// Function definition
int myFunction(int x, int y) {
  return x + y;
}
```

#### Functions Calling Other Functions
Functions can call other functions as long as they are properly declared first:

```c
// Declare two functions
void myFunction();
void myOtherFunction();

int main() {
  myFunction(); // call myFunction (from main)
  return 0;
}

// Define myFunction
void myFunction() {
  printf("Some text in myFunction\n");
  myOtherFunction(); // call myOtherFunction (from myFunction)
}

// Define myOtherFunction
void myOtherFunction() {
  printf("Hey! Some text in myOtherFunction\n");
}
```

#### Key Points to Remember:
- Always declare functions before they are called
- Keep declarations and definitions separate for better code organization
- Main function typically goes between declarations and definitions
- Function declarations (prototypes) should match their definitions
- Include appropriate return types and parameter lists in both declaration and definition
