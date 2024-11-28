+++
title = "C While Loop"
weight = 13
chapter = false
pre = " <b> 13. </b> "
+++

#### C While Loop

Loops can execute a block of code as long as a specified condition is reached. They are handy because they:
- Save time
- Reduce errors 
- Make code more readable

#### While Loop

The while loop executes a block of code repeatedly as long as a specified condition is true.

#### Syntax
```c
while (condition) {
    // code block to be executed
}
```

#### Example
Here, the code in the loop will run repeatedly as long as the variable `i` is less than 5:

```c
int i = 0;

while (i < 5) {
    printf("%d\n", i);
    i++;
}
```

> **Note:** Don't forget to increment the variable used in the condition (`i++`), otherwise the loop will never end!

The output of this code will be:
```
0
1
2
3
4
```

In this example:
1. We initialize `i` to 0
2. The while loop checks if `i` is less than 5
3. If true, it prints the value of `i`
4. Then increments `i` by 1
5. The process repeats until `i` reaches 5, at which point the condition becomes false and the loop ends



#### The Do/While Loop

The do/while loop is a variant of the while loop. This loop will execute the code block once, before checking if the condition is true, then it will repeat the loop as long as the condition is true.

#### Syntax

```c
do {
  // code block to be executed
} while (condition);
```

The example below uses a do/while loop. The loop will always be executed at least once, even if the condition is false, because the code block is executed before the condition is tested:

#### Example

```c 
int i = 0;

do {
    printf("%d\n", i);
    i++;
} while (i < 5);
```

The output will be:
```
0
1
2
3
4
```