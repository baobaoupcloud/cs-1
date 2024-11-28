+++
title = "C Programming Operators"
weight = 9
chapter = false
pre = " <b> 9. </b> "
+++

#### C Programming Operators

Operators are used to perform operations on variables and values.

#### Basic Usage

In C, operators can be used to perform calculations with values and variables:

```c
int myNum = 100 + 50;    // Basic addition with values

// Operations with variables and values
int sum1 = 100 + 50;     // 150 (100 + 50)
int sum2 = sum1 + 250;   // 400 (150 + 250)
int sum3 = sum2 + sum2;  // 800 (400 + 400)
```

#### Categories of C Operators

C provides several categories of operators:

1. Arithmetic operators
2. Assignment operators
3. Comparison operators
4. Logical operators
5. Bitwise operators

#### Arithmetic Operators

These operators perform common mathematical operations:

| Operator | Name | Description | Example |
|----------|------|-------------|----------|
| + | Addition | Adds two values | x + y |
| - | Subtraction | Subtracts values | x - y |
| * | Multiplication | Multiplies values | x * y |
| / | Division | Divides values | x / y |
| % | Modulus | Returns remainder | x % y |
| ++ | Increment | Increases by 1 | ++x |
| -- | Decrement | Decreases by 1 | --x |

#### Assignment Operators

Assignment operators assign values to variables:

```c
int x = 10;     // Basic assignment
x += 5;         // Addition assignment (same as x = x + 5)
```

Full list of assignment operators:

| Operator | Example | Equivalent |
|----------|----------|------------|
| = | x = 5 | x = 5 |
| += | x += 3 | x = x + 3 |
| -= | x -= 3 | x = x - 3 |
| *= | x *= 3 | x = x * 3 |
| /= | x /= 3 | x = x / 3 |
| %= | x %= 3 | x = x % 3 |
| &= | x &= 3 | x = x & 3 |
| \|= | x \|= 3 | x = x \| 3 |
| ^= | x ^= 3 | x = x ^ 3 |
| >>= | x >>= 3 | x = x >> 3 |
| <<= | x <<= 3 | x = x << 3 |

#### Comparison Operators

Comparison operators return boolean values (1 for true, 0 for false):

```c
int x = 5;
int y = 3;
printf("%d", x > y);    // Returns 1 (true) because 5 > 3
```

List of comparison operators:

| Operator | Name | Example | Description |
|----------|------|---------|-------------|
| == | Equal to | x == y | Returns 1 if values are equal |
| != | Not equal | x != y | Returns 1 if values are not equal |
| > | Greater than | x > y | Returns 1 if x is greater than y |
| < | Less than | x < y | Returns 1 if x is less than y |
| >= | Greater than or equal | x >= y | Returns 1 if x is greater than or equal to y |
| <= | Less than or equal | x <= y | Returns 1 if x is less than or equal to y |

#### Logical Operators

Logical operators combine multiple conditions:

| Operator | Name | Example | Description |
|----------|------|---------|-------------|
| && | AND | x < 5 && x < 10 | Returns 1 if both conditions are true |
| \|\| | OR | x < 5 \|\| x < 4 | Returns 1 if at least one condition is true |
| ! | NOT | !(x < 5) | Returns 1 if the condition is false |

