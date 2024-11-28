+++
title = "C Break and Continue"
weight = 15
chapter = false
pre = " <b> 15. </b> "
+++

#### C Break and Continue

#### Break Statement

The `break` statement allows you to exit or "jump out" of a loop immediately. It's commonly used in both loops and switch statements.

#### Break in For Loop Example

```c
int i;

for (i = 0; i < 10; i++) {
    if (i == 4) {
        break;
    }
    printf("%d\n", i);
}
```

This code will print numbers 0 through 3, then stop when i equals 4.

#### Continue Statement

The `continue` statement skips the rest of the current iteration and moves to the next one. Unlike `break`, it doesn't exit the loop entirely.

#### Continue in For Loop Example

```c
int i;

for (i = 0; i < 10; i++) {
    if (i == 4) {
        continue;
    }
    printf("%d\n", i);
}
```

This code will print all numbers from 0 to 9, except for 4.

#### Using Break and Continue in While Loops

#### Break in While Loop

```c
int i = 0;

while (i < 10) {
    if (i == 4) {
        break;
    }
    printf("%d\n", i);
    i++;
}
```

#### Continue in While Loop

```c
int i = 0;

while (i < 10) {
    if (i == 4) {
        i++;
        continue;
    }
    printf("%d\n", i);
    i++;
}
```

Key differences between `break` and `continue`:
- `break` terminates the entire loop
- `continue` skips only the current iteration
- With `continue` in a while loop, remember to update your counter before the continue statement to avoid infinite loops