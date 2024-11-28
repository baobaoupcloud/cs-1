+++
title = "C Switch"
weight = 12
chapter = false
pre = " <b> 12. </b> "
+++

#### C Switch

In C programming, the switch statement provides an efficient alternative to multiple if-else statements. It allows you to select one code block from many options based on a specific expression.

#### Basic Syntax

```c
switch (expression) {
    case x:
        // code block
        break;
    case y:
        // code block
        break;
    default:
        // code block
}
```

#### How It Works

The switch statement operates by:
1. Evaluating the expression once
2. Comparing the expression's value with each case
3. Executing the matched case's code block
4. Using break to exit the switch block
5. Falling back to default if no case matches

#### Example: Weekday Names

```c
int day = 4;

switch (day) {
    case 1:
        printf("Monday");
        break;
    case 2:
        printf("Tuesday");
        break;
    case 3:
        printf("Wednesday");
        break;
    case 4:
        printf("Thursday");
        break;
    case 5:
        printf("Friday");
        break;
    case 6:
        printf("Saturday");
        break;
    case 7:
        printf("Sunday");
        break;
}
// Outputs "Thursday" (day 4)
```

#### The break Keyword

The break statement serves several important purposes:
- Exits the switch block
- Prevents execution of subsequent cases
- Improves execution efficiency
- Avoids unintended fall-through behavior

#### The default Keyword 

Default provides a fallback option when no case matches:

```c
int day = 4;

switch (day) {
    case 6:
        printf("Today is Saturday");
        break;
    case 7:
        printf("Today is Sunday");
        break;
    default:
        printf("Looking forward to the Weekend");
}
// Outputs "Looking forward to the Weekend"
```

Important notes about default:
- Must be the last statement in the switch
- Does not require a break statement
- Executes when no case matches
- Is optional but recommended for error handling