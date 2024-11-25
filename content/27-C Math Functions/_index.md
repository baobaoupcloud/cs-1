+++
title = "Switch Statement in C"
weight = 27
chapter = false
pre = " <b> 27s. </b> "
+++

#### C Math Functions

When working with mathematical operations in C, you can access a variety of built-in math functions. These functions provide common mathematical operations like square root, rounding, and power calculations.

#### Including the Math Header

Before using any math functions, you must include the math header file:

```c
#include <math.h>
```

#### Common Math Functions

#### Square Root - sqrt()
The `sqrt()` function calculates the square root of a number:

```c
printf("%f", sqrt(16));  // Output: 4.000000
```

#### Rounding Functions
C provides two main rounding functions:

#### ceil() - Round Up
The `ceil()` function rounds a number upward to the nearest integer:

```c
printf("%f", ceil(1.4));  // Output: 2.000000
```

#### floor() - Round Down
The `floor()` function rounds a number downward to the nearest integer:

```c
printf("%f", floor(1.4));  // Output: 1.000000
```

#### Power - pow()
The `pow()` function calculates the value of x raised to the power of y (xʸ):

```c
printf("%f", pow(4, 3));  // Output: 64.000000  (4³ = 4 * 4 * 4)
```

Keep in mind that when using these math functions:
- Values are typically returned as double precision floating-point numbers
- You may need to link against the math library when compiling (using `-lm` flag)
- Always check for domain errors when using functions like `sqrt()` with negative numbers