+++
title = "Strings in C Programming"
weight = 18
chapter = false
pre = " <b> 18. </b> "
+++

#### Strings in C Programming

#### Introduction
Strings in C are used for storing text and characters. For example, `"Hello World"` is a string of characters.

Unlike many programming languages, C doesn't have a built-in String type. Instead, we use the `char` type and create an array of characters:

```c
char greetings[] = "Hello World!";
```

**Note**: Always use double quotes (`" "`) for strings.

#### String Output
To output strings, use the `printf()` function with the `%s` format specifier:

```c
char greetings[] = "Hello World!";
printf("%s", greetings);
```

#### Accessing Characters
Since strings are arrays in C, you can access individual characters using index numbers:

```c
char greetings[] = "Hello World!";
printf("%c", greetings[0]);  // Prints 'H'
```

**Note**: Use the `%c` format specifier to print single characters.

#### Modifying Strings
To change a specific character, refer to its index and use single quotes:

```c
char greetings[] = "Hello World!";
greetings[0] = 'J';
printf("%s", greetings);  // Outputs "Jello World!"
```

#### Looping Through Strings
You can iterate through a string using a for loop:

```c
char carName[] = "Volvo";
int i;

// Method 1: Manual length
for (i = 0; i < 5; ++i) {
    printf("%c\n", carName[i]);
}

// Method 2: Using sizeof
int length = sizeof(carName) / sizeof(carName[0]);
for (i = 0; i < length; ++i) {
    printf("%c\n", carName[i]);
}
```

#### Alternative String Creation
There are two ways to create strings in C:

#### 1. String Literal (Recommended)
```c
char greetings[] = "Hello World!";
```

#### 2. Character Array
```c
char greetings[] = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd', '!', '\0'};
```

**Important**: The `\0` character is the "null terminating character" and is required when creating strings using the character array method.

#### Size Comparison
Both methods create arrays of the same size:

```c
char greetings[] = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd', '!', '\0'};
char greetings2[] = "Hello World!";

printf("%lu\n", sizeof(greetings));   // Outputs 13
printf("%lu\n", sizeof(greetings2));  // Outputs 13
```

#### Practical Example
Creating a welcome message by combining strings:

```c
char message[] = "Good to see you,";
char fname[] = "John";

printf("%s %s!", message, fname);  // Outputs "Good to see you, John!"
```