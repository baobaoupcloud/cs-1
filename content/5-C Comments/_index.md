+++
title = "C Comments"
weight = 5
chapter = false
pre = " <b> 5. </b> "
+++


#### C Comments {#comments-in-c}

#### Single-line Comments

Single-line comments start with two forward slashes (`//`).

Any text between `//` and the end of the line is ignored by the compiler (will not be executed).

#### Example - Comment Before Code

```c
// This is a comment
printf("Hello World!");
```

#### Example - Comment After Code

```c
printf("Hello World!"); // This is a comment
```

#### Multi-line Comments

Multi-line comments start with `/*` and end with `*/`.

Any text between `/*` and `*/` will be ignored by the compiler:

#### Example

```c
/* The code below will print the words Hello World!
to the screen, and it is amazing */
printf("Hello World!");
```

#### Single or Multi-line Comments?

It is up to you which you want to use. Typically:
- Use `//` for short comments  
- Use `/* */` for longer comments

#### Note

Before version C99 (released in 1999), you could only use multi-line comments in C.
