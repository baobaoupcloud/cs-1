+++
title = "C Constants"
weight = 8
chapter = false
pre = " <b> 8. </b> "
+++

#### C Constants

Constants are variables whose values cannot be modified after declaration. They provide a way to create read-only values in your programs.

#### Declaring Constants

To declare a constant, use the `const` keyword before the data type:

```c
const int myNum = 15;  // myNum will always be 15
// myNum = 10;  // ERROR: Cannot modify a constant variable
```

#### Common Use Cases

Constants are ideal for values that should remain unchanged throughout program execution:

```c
const int MINUTES_PER_HOUR = 60;
const float PI = 3.14;
```

#### Important Rules

#### Rule 1: Immediate Initialization Required

Constants must be initialized when they are declared:

```c
// Correct way:
const int MINUTES_PER_HOUR = 60;

// Wrong way - will cause an error:
// const int MINUTES_PER_HOUR;
// MINUTES_PER_HOUR = 60;
```

#### Rule 2: Naming Convention

While not required by the language, it's considered good practice to name constants using uppercase letters:

```c
// Recommended naming convention
const int BIRTH_YEAR = 1980;
const float MAX_TEMPERATURE = 100.0;
```

This convention makes constants easily distinguishable from regular variables in your code and is widely used by C programmers.

#### Benefits of Using Constants

- Prevents accidental value modifications
- Makes code more maintainable
- Improves code readability
- Helps catch potential errors at compile time

Remember that trying to modify a constant after declaration will result in a compilation error, helping you maintain data integrity in your programs.
