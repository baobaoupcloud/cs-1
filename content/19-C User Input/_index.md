+++
title = "User Input in C Programming"
weight = 19
chapter = false
pre = " <b> 19. </b> "
+++

#### User Input in C Programming

#### Using `printf()` and `scanf()`

You've already learned that `printf()` is used for output. For user input, C provides the `scanf()` function.

#### Basic Input Example
Here's how to get and output a number from user input:

```c
// Create an integer variable to store the user's number
int myNum;

// Ask the user to type a number
printf("Type a number: \n");

// Get and save the number
scanf("%d", &myNum);

// Output the number
printf("Your number is: %d", myNum);
```

**Important Note:** The `scanf()` function requires two arguments:
1. Format specifier (e.g., `%d` for integers)
2. Reference operator (`&myNum`) for the variable's memory address

#### Multiple Inputs

You can get multiple inputs in a single `scanf()` call:

```c
// Declare variables
int myNum;
char myChar;

// Request input from user
printf("Type a number AND a character and press enter: \n");

// Get both inputs
scanf("%d %c", &myNum, &myChar);

// Display results
printf("Your number is: %d\n", myNum);
printf("Your character is: %c\n", myChar);
```

#### String Input

#### Basic String Input with `scanf()`

```c
// Create a string (character array)
char firstName[30];

// Request input
printf("Enter your first name: \n");

// Get the string input
scanf("%s", firstName);

// Display result
printf("Hello %s", firstName);
```

**Note:** When using `scanf()` with strings:
- You must specify the array size
- The reference operator (`&`) is not needed
- It only captures input up to the first whitespace

#### Limitations of `scanf()` with Strings

This example shows the limitation of `scanf()` with multi-word strings:

```c
char fullName[30];

printf("Type your full name: \n");
scanf("%s", &fullName);

printf("Hello %s", fullName);

// If input is: John Doe
// Output will be: Hello John
```

#### Using `fgets()` for Better String Input

To capture full lines of text, including spaces, use `fgets()`:

```c
char fullName[30];

printf("Type your full name: \n");
fgets(fullName, sizeof(fullName), stdin);

printf("Hello %s", fullName);

// If input is: John Doe
// Output will be: Hello John Doe
```

**Note:** When using `fgets()`, remember to include:
- String variable name
- Size of string (`sizeof(string_name)`)
- Standard input (`stdin`)
