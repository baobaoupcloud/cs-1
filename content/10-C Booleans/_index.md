+++
title = "C Booleans"
weight = 10
chapter = false
pre = " <b> 10. </b> "
+++

#### C Booleans

In programming, you often need a data type that can only have one of two values:
- YES / NO
- ON / OFF
- TRUE / FALSE

C provides the `bool` data type (booleans) to represent values that are either true or false.

#### Boolean Variables

Unlike `int` or `char`, the `bool` type is not built-in to C. It was introduced in C99 and requires importing:

```c
#include <stdbool.h>
```

Declare boolean variables using the `bool` keyword:

```c
bool isProgrammingFun = true;
bool isFishTasty = false;
```

#### Printing Boolean Values

Booleans are represented internally as integers:
- 1 (or any non-zero number) represents `true`
- 0 represents `false`

Use the `%d` format specifier to print boolean values:

```c
// Create boolean variables
bool isProgrammingFun = true;
bool isFishTasty = false;

// Print boolean values
printf("%d", isProgrammingFun);   // Returns 1 (true)
printf("%d", isFishTasty);        // Returns 0 (false)
```

#### Comparing Values and Variables

Boolean values commonly result from comparisons between values and variables. These comparisons help make decisions in programs.

Using comparison operators:

```c
// Compare values
printf("%d", 10 > 9);  // Returns 1 (true)

// Compare variables
int x = 10;
int y = 9;
printf("%d", x > y);   // Returns 1 (true)
```

Using the equality operator (`==`):

```c
printf("%d", 10 == 10); // Returns 1 (true)
printf("%d", 10 == 15); // Returns 0 (false)
printf("%d", 5 == 55);  // Returns 0 (false)
```

You can also compare boolean variables:

```c
bool isHamburgerTasty = true;
bool isPizzaTasty = true;

// Compare boolean values
printf("%d", isHamburgerTasty == isPizzaTasty); // Returns 1 (true)
```

**Important:** Always remember to include the `<stdbool.h>` header file when working with boolean variables.