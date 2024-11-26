+++
title = "C Function Parameters"
weight = 23
chapter = false
pre = " <b> 23. </b> "
+++

#### C Function Parameters

#### Parameters and Arguments

Information can be passed to functions as parameters. Parameters act as variables inside the function.

Parameters are specified after the function name, inside parentheses. You can add multiple parameters by separating them with commas.

#### Basic Syntax
```c
returnType functionName(parameter1, parameter2, parameter3) {
    // code to be executed
}
```

#### Simple Function Example
Here's a function that takes a string parameter and prints a greeting:

```c
void myFunction(char name[]) {
    printf("Hello %s\n", name);
}

int main() {
    myFunction("Liam");
    myFunction("Jenny"); 
    myFunction("Anja");
    return 0;
}

// Output:
// Hello Liam
// Hello Jenny
// Hello Anja
```

When a parameter is passed to the function, it becomes an argument. In the example above:
- `name` is a parameter
- `"Liam"`, `"Jenny"`, and `"Anja"` are arguments

#### Multiple Parameters

Functions can accept multiple parameters:

```c
void myFunction(char name[], int age) {
    printf("Hello %s. You are %d years old.\n", name, age);
}

int main() {
    myFunction("Liam", 3);
    myFunction("Jenny", 14);
    myFunction("Anja", 30);
    return 0;
}

// Output:
// Hello Liam. You are 3 years old.
// Hello Jenny. You are 14 years old.
// Hello Anja. You are 30 years old.
```

#### Array Parameters

You can pass arrays to functions:

```c
void myFunction(int myNumbers[5]) {
    for (int i = 0; i < 5; i++) {
        printf("%d\n", myNumbers[i]);
    }
}

int main() {
    int myNumbers[5] = {10, 20, 30, 40, 50};
    myFunction(myNumbers);
    return 0;
}
```

Note: When passing an array, use just the array name in the function call, but include the full array declaration in the parameter definition.

#### Return Values

Functions can return values using the `return` keyword. Replace `void` with the appropriate data type:

```c
int myFunction(int x, int y) {
    return x + y;
}

int main() {
    int result = myFunction(5, 3);
    printf("Result is = %d", result);
    return 0;
}
// Output: Result is = 8
```

#### Practical Example: Temperature Converter

Here's a real-world example that converts Fahrenheit to Celsius:

```c
float toCelsius(float fahrenheit) {
    return (5.0 / 9.0) * (fahrenheit - 32.0);
}

int main() {
    float f_value = 98.8;
    float result = toCelsius(f_value);
    
    printf("Fahrenheit: %.2f\n", f_value);
    printf("Convert Fahrenheit to Celsius: %.2f\n", result);
    
    return 0;
}
```

#### Working with Multiple Results

When dealing with multiple results, you can store them in an array:

```c
int calculateSum(int x, int y) {
    return x + y;
}

int main() {
    int resultArr[6];
    
    resultArr[0] = calculateSum(5, 3);
    resultArr[1] = calculateSum(8, 2);
    resultArr[2] = calculateSum(15, 15);
    resultArr[3] = calculateSum(9, 1);
    resultArr[4] = calculateSum(7, 7);
    resultArr[5] = calculateSum(1, 1);
    
    for (int i = 0; i < 6; i++) {
        printf("Result%d is = %d\n", i + 1, resultArr[i]);
    }
    
    return 0;
}
```

#### Important Notes
- Function calls must have the same number of arguments as parameters
- Arguments must be passed in the same order as parameters
- The return type must match the data type of the returned value
- Use appropriate data types for parameters and return values