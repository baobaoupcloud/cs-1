+++
title = "C If-Else"
weight = 11
chapter = false
pre = " <b> 11. </b> "
+++

#### C If-Else

#### Logical Conditions

C supports standard mathematical logical conditions:

- Less than: `a < b`
- Less than or equal to: `a <= b`
- Greater than: `a > b`
- Greater than or equal to: `a >= b`
- Equal to: `a == b`
- Not Equal to: `a != b`

These conditions enable different actions based on decision logic.

#### Conditional Statements

C provides several conditional statements:

1. `if` - Executes code when a condition is true
2. `else` - Executes code when the condition is false 
3. `else if` - Tests a new condition when the previous condition is false
4. `switch` - Executes different code blocks based on multiple conditions

#### The if Statement

The `if` statement executes a block of code when a specified condition evaluates to true.

#### Syntax

```c
if (condition) {
    // block of code to be executed if the condition is true
}
```

**Important**: `if` must be lowercase. Using `If` or `IF` will result in a compiler error.

#### Examples

Testing numeric values:
```c
if (20 > 18) {
    printf("20 is greater than 18");
}
```

Testing variables:
```c
int x = 20;
int y = 18;
if (x > y) {
    printf("x is greater than y");
}
```

#### Example Explanation

In the variable example above:
- We declare two variables: `x` with value 20 and `y` with value 18
- The `if` statement tests whether `x` is greater than `y` using the `>` operator
- Since 20 is greater than 18, the condition is true
- The program prints "x is greater than y" to the screen

#### The else Statement in C

The `else` statement allows you to execute a different block of code when the `if` condition evaluates to false. This creates a binary decision structure in your program.

#### Syntax

```c
if (condition) {
    // code block executed when condition is true
} else {
    // code block executed when condition is false
}
```

#### Example

Here's a simple example that checks the time and prints an appropriate greeting:

```c
int time = 20;

if (time < 18) {
    printf("Good day.");
} else {
    printf("Good evening.");
}
// Output: "Good evening."
```

#### How it Works

1. First, the condition inside the `if` statement is evaluated
2. If the condition is `false` (in this case, 20 is not less than 18)
3. The program skips the first code block
4. The program executes the code block after the `else` statement
5. In this example, it prints "Good evening."

#### Common Use Cases

You can use the `if...else` statement for various scenarios:

```c
// Check if a number is positive or negative
int number = -5;

if (number >= 0) {
    printf("The number is positive.");
} else {
    printf("The number is negative.");
}

// Check if a student passed or failed
int score = 75;
int passingGrade = 60;

if (score >= passingGrade) {
    printf("Student passed!");
} else {
    printf("Student failed.");
}
```

#### Best Practices

1. Always use curly braces `{}` even for single-line statements
2. Keep the code blocks well-indented for better readability
3. Make sure the condition is clearly written and understandable
4. Consider using `else if` when you need to check multiple conditions

Remember that the `else` statement is optional - you can use `if` statements without them when you only need to execute code for the true condition.


#### The `else if` Statement

Use the `else if` statement to specify a new condition if the first condition is false.

#### Syntax

```c
if (condition1) {
    // block of code to be executed if condition1 is true
} else if (condition2) {
    // block of code to be executed if condition1 is false and condition2 is true
} else {
    // block of code to be executed if condition1 is false and condition2 is false
}
```

#### Example

```c
int time = 22;
if (time < 10) {
    printf("Good morning.");
} else if (time < 20) {
    printf("Good day.");
} else {
    printf("Good evening.");
}
// Outputs "Good evening."
```

In this example:
- If the time is less than 10, it prints "Good morning"
- If the time is less than 20 (but greater than or equal to 10), it prints "Good day"
- If neither condition is true (time is greater than or equal to 20), it prints "Good evening"

The output is "Good evening" because the variable `time` is 22, which is greater than both 10 and 20, causing the code to execute the `else` block.