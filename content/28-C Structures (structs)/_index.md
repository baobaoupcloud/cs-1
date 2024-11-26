+++
title = "C Structures (structs)"
weight = 28
chapter = false
pre = " <b> 28. </b> "
+++

#### C Structures (structs)

#### Introduction to Structures

Structures (also called structs) are a way to group several related variables into one place. Each variable in the structure is known as a member of the structure.

Unlike an array, a structure can contain many different data types (`int`, `float`, `char`, etc.).

#### Creating a Structure

You can create a structure using the `struct` keyword and declare its members inside curly braces:

```c
struct MyStructure {   // Structure declaration
    int myNum;        // Member (int variable)
    char myLetter;    // Member (char variable)
}; // End the structure with a semicolon
```

To access the structure, create a variable of it using the `struct` keyword inside the `main()` method:

```c
struct myStructure {
    int myNum;
    char myLetter;
};

int main() {
    struct myStructure s1;
    return 0;
}
```

#### Accessing Structure Members

Use the dot syntax (`.`) to access members of a structure:

```c
struct myStructure {
    int myNum;
    char myLetter;
};

int main() {
    struct myStructure s1;
    
    // Assign values to members of s1
    s1.myNum = 13;
    s1.myLetter = 'B';
    
    // Print values
    printf("My number: %d\n", s1.myNum);
    printf("My letter: %c\n", s1.myLetter);
    
    return 0;
}
```

You can create multiple structure variables with different values:

```c
// Create different struct variables
struct myStructure s1;
struct myStructure s2;

// Assign values to different struct variables
s1.myNum = 13;
s1.myLetter = 'B';

s2.myNum = 20;
s2.myLetter = 'C';
```

#### Working with Strings in Structures

When using strings in structures, remember that strings in C are character arrays. You cannot directly assign values to arrays:

```c
struct myStructure {
    int myNum;
    char myLetter;
    char myString[30];  // String
};
```

Instead, use the `strcpy()` function to assign string values:

```c
struct myStructure {
    int myNum;
    char myLetter;
    char myString[30];
};

int main() {
    struct myStructure s1;
    
    // Assign a value to the string using strcpy
    strcpy(s1.myString, "Some text");
    
    // Print the value
    printf("My string: %s", s1.myString);
    
    return 0;
}
```

#### Simplified Structure Initialization

You can assign values to structure members at declaration time using a comma-separated list:

```c
struct myStructure {
    int myNum;
    char myLetter;
    char myString[30];
};

int main() {
    // Initialize structure with values
    struct myStructure s1 = {13, 'B', "Some text"};
    
    // Print values
    printf("%d %c %s", s1.myNum, s1.myLetter, s1.myString);
    
    return 0;
}
```

#### Copying and Modifying Structures

You can copy one structure to another:

```c
struct myStructure s1 = {13, 'B', "Some text"};
struct myStructure s2;

s2 = s1;  // Copy s1 to s2
```

To modify values, use the dot syntax or `strcpy()` for strings:

```c
// Modify values
s1.myNum = 30;
s1.myLetter = 'C';
strcpy(s1.myString, "Something else");
```

#### Real-Life Example: Car Database

Here's a practical example using structures to store car information:

```c
struct Car {
    char brand[50];
    char model[50];
    int year;
};

int main() {
    struct Car car1 = {"BMW", "X5", 1999};
    struct Car car2 = {"Ford", "Mustang", 1969};
    struct Car car3 = {"Toyota", "Corolla", 2011};

    printf("%s %s %d\n", car1.brand, car1.model, car1.year);
    printf("%s %s %d\n", car2.brand, car2.model, car2.year);
    printf("%s %s %d\n", car3.brand, car3.model, car3.year);

    return 0;
}
```