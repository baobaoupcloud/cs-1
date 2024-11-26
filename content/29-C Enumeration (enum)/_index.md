+++
title = "C Enumeration (enum)"
weight = 29
chapter = false
pre = " <b> 29. </b> "
+++

#### C Enumeration (enum)

In C programming, an enum (enumeration) is a special type that defines a group of constants (unchangeable values).

#### Basic Syntax

To create an enum, use the `enum` keyword followed by the name and list the items within curly braces:

```c
enum Level {
    LOW,
    MEDIUM,
    HIGH
};
```

*Note: The last item doesn't require a comma.*

#### Using Enums

To use an enum, create a variable of the enum type:

```c
enum Level myVar;       // Declare enum variable
myVar = MEDIUM;        // Assign value
```

You can also declare and initialize in one line:

```c
enum Level myVar = MEDIUM;
```

#### Default Values

By default, enum values start at 0 and increment by 1:
- `LOW` = 0
- `MEDIUM` = 1
- `HIGH` = 2

#### Custom Values

You can assign custom values to enum members:

```c
enum Level {
    LOW = 25,
    MEDIUM = 50,
    HIGH = 75
};
```

If you assign a value to one item, subsequent items will increment from that value:

```c
enum Level {
    LOW = 5,    // 5
    MEDIUM,     // 6
    HIGH        // 7
};
```

#### Using Enums in Switch Statements

Enums work well with switch statements:

```c
enum Level {
    LOW = 1,
    MEDIUM,
    HIGH
};

int main() {
    enum Level myVar = MEDIUM;
    
    switch (myVar) {
        case 1:
            printf("Low Level");
            break;
        case 2:
            printf("Medium level");
            break;
        case 3:
            printf("High level");
            break;
    }
    return 0;
}
```

#### Best Practices

1. Use UPPERCASE for enum constants (though not required)
2. Use enums for related constants that won't change
3. Common use cases:
   - Month days
   - Week days
   - Color codes
   - Card suits
   - Status codes
   - Menu options

#### Benefits of Using Enums

1. Makes code more readable
2. Provides type safety
3. Easier maintenance
4. Self-documenting code
5. Better organization of related constants