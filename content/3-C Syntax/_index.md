+++
title = "C Syntax"
weight = 3
chapter = false
pre = " <b> 3. </b> "
+++


#### Overview

You have already seen the following code a couple of times in the first chapters. Let's break it down to understand it better:

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0003/0001.png?featherlight=false&width=90pc)

#### Example

```c
#include <stdio.h>

int main() {
    printf("Hello World!");
    return 0;
}
```

#### Example Explained

**Line 1:** `#include <stdio.h>` is a **header file library** that lets us work with input and output functions, such as `printf()` (used in line 4). Header files add functionality to C programs.

*Don't worry if you don't understand how `#include <stdio.h>` works. Just think of it as something that (almost) always appears in your program.*

**Line 2:** A blank line. C ignores white space. But we use it to make the code more readable.

**Line 3:** Another thing that always appear in a C program is `main()`. This is called a **function**. Any code inside its curly brackets `{}` will be executed.

**Line 4:** `printf()` is a **function** used to output/print text to the screen. In our example, it will output "Hello World!".

> Note: Every C statement ends with a semicolon `;`

> Tip: The body of `int main()` could also been written as:
```c
int main(){printf("Hello World!");return 0;}
```
> However, multiple lines makes the code more readable.

**Line 5:** `return 0` ends the `main()` function.

**Line 6:** Do not forget to add the closing curly bracket `}` to actually end the main function.

#### Introduction to Program Statements

A computer program consists of a sequence of instructions that tell the computer what actions to perform. In programming languages, these instructions are called **statements**.

#### Basic Statement Structure 

#### Statement Example
```c
printf("Hello World!");
```

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0003/0002.png?featherlight=false&width=90pc)

#### Statement Requirements
- Each statement must end with a semicolon (`;`)
- Forgetting the semicolon leads to compilation errors

#### Error Example
```c
printf("Hello World!") // Error: Missing semicolon
```

> Warning: *Compiler Output:* `error: expected ';' before 'return'`

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0003/0003.png?featherlight=false&width=90pc)

#### Multiple Statements

Programs typically contain multiple statements that execute sequentially.

#### Example of Multiple Statements
```c
printf("Hello World!");
printf("Have a good day!");
return 0;
```

#### Execution Order

Statements are executed in order from top to bottom:

1. First statement: Outputs "Hello World!"
2. Second statement: Outputs "Have a good day!"
3. Third statement: Returns 0 to end the program successfully

#### Best Practices

- Always end statements with semicolons
- Write one statement per line for better readability
- Use proper indentation to maintain code structure
- Add comments to explain complex statements

#### Summary

- Programs are lists of instructions (statements)
- Statements must end with semicolons
- Multiple statements execute in sequential order
- Proper syntax and formatting improve code reliability