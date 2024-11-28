+++
title = "C For Loop"
weight = 14
chapter = false
pre = " <b> 14. </b> "
+++

#### C For Loop

When you need to iterate a specific number of times through a block of code, the `for` loop is often more suitable than a `while` loop.

#### Syntax

```c
for (expression 1; expression 2; expression 3) {
    // code block to be executed
}
```

The three expressions in the `for` loop serve different purposes:

* **Expression 1**: Initializes the loop variable and executes only once before the loop begins
* **Expression 2**: Defines the condition for executing the code block - loop continues while this is true
* **Expression 3**: Executes after each iteration of the loop, typically to update the loop variable

#### Example

Here's a simple example that prints numbers from 0 to 4:

```c
int i;

for (i = 0; i < 5; i++) {
    printf("%d\n", i);
}
```

#### How It Works

Let's break down the example:

1. `i = 0`: Initializes the counter variable to 0
2. `i < 5`: Loop continues as long as i is less than 5
3. `i++`: Increments i by 1 after each iteration

The output will be:
```
0
1
2
3
4
```

This loop will execute exactly 5 times, with `i` taking on values from 0 to 4. Once `i` reaches 5, the condition `i < 5` becomes false, and the loop terminates.

#### Nested Loops in C

In C programming, you can place a loop inside another loop, creating what's called a **nested loop**.

When using nested loops, the inner loop completes all its iterations for *each single iteration* of the outer loop.

#### Example

```c
int i, j;

// Outer loop
for (i = 1; i <= 2; ++i) {
    printf("Outer: %d\n", i);  // Executes 2 times
    
    // Inner loop
    for (j = 1; j <= 3; ++j) {
        printf(" Inner: %d\n", j);  // Executes 6 times (2 * 3)
    }
}
```

#### Output:
```
Outer: 1
 Inner: 1
 Inner: 2
 Inner: 3
Outer: 2
 Inner: 1
 Inner: 2
 Inner: 3
```

#### Execution Flow:
1. The outer loop runs 2 times (i = 1, 2)
2. For *each* iteration of the outer loop:
   - The inner loop runs 3 times (j = 1, 2, 3)
3. Total number of inner loop iterations: 2 × 3 = 6 times

