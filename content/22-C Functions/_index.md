+++
title = "C Functions"
weight = 22
chapter = false
pre = " <b> 22. </b> "
+++

#### C Functions

Functions are essential building blocks in C programming that allow you to organize and reuse code efficiently. A function is a block of code that executes when called, and it can accept parameters as input data.

#### Understanding Functions

Functions serve multiple purposes:
- Execute specific tasks
- Enable code reusability
- Organize code into manageable blocks
- Process input parameters
- Return results

#### Predefined Functions

You're already familiar with some predefined functions in C. For example, `main()` and `printf()` are built-in functions:

```c
int main() {
    printf("Hello World!");
    return 0;
}
```

#### Creating Functions

To declare a function, specify its name followed by parentheses `()` and curly brackets `{}`:

#### Basic Syntax

```c
void myFunction() {
    // code to be executed
}
```

#### Function Components Explained

- `myFunction()` - the function name
- `void` - indicates no return value
- Function body - code between curly brackets

#### Calling Functions

To execute a function, call it by writing its name followed by parentheses and a semicolon:

```c
// Function definition
void myFunction() {
    printf("I just got executed!");
}

int main() {
    myFunction(); // function call
    return 0;
}
```

#### Multiple Function Calls

You can call the same function multiple times:

```c
void myFunction() {
    printf("I just got executed!");
}

int main() {
    myFunction();
    myFunction();
    myFunction();
    return 0;
}

// Output:
// I just got executed!
// I just got executed!
// I just got executed!
```

#### Practical Example: Number Calculation

Here's a practical example of a function that calculates the sum of two numbers:

```c
void calculateSum() {
    int x = 5;
    int y = 10;
    int sum = x + y;
    printf("The sum of x + y is: %d", sum);
}

int main() {
    calculateSum();  // calls the function
    return 0;
}

// Output: The sum of x + y is: 15
```

#### Note on Function Flexibility
This example uses fixed values (5 and 10). In practice, functions become more powerful when they accept parameters, allowing for dynamic calculations with different input values. This concept will be covered in the next section about function parameters.

#### Key Points to Remember

1. Functions must be declared before they can be used
2. Function names should be descriptive and follow C naming conventions
3. The `void` keyword indicates no return value
4. Functions can be called multiple times
5. Code inside functions only executes when the function is called