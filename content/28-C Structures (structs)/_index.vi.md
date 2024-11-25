+++
title = "C Structures (structs)" 
weight = 28
chapter = false
pre = " <b> 28. </b> "
+++

#### C Structures (structs)

#### Giới thiệu về Structure

Structure (còn gọi là struct) là cách để nhóm nhiều biến có liên quan với nhau vào một nơi. Mỗi biến trong structure được gọi là một thành viên (member) của structure đó.

Khác với mảng, một structure có thể chứa nhiều kiểu dữ liệu khác nhau (`int`, `float`, `char`, v.v.).

#### Tạo Structure 

Bạn có thể tạo structure bằng từ khóa `struct` và khai báo các thành viên của nó trong dấu ngoặc nhọn:

```c
struct MyStructure {    // Khai báo structure
    int myNum;         // Thành viên (biến kiểu int)
    char myLetter;     // Thành viên (biến kiểu char)  
}; // Kết thúc structure bằng dấu chấm phẩy
```

Để sử dụng structure, tạo một biến của nó bằng từ khóa `struct` trong hàm `main()`:

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

#### Truy cập thành viên của Structure

Sử dụng cú pháp dấu chấm (`.`) để truy cập thành viên của structure:

```c
struct myStructure {
    int myNum;
    char myLetter;
};

int main() {
    struct myStructure s1;
    
    // Gán giá trị cho các thành viên của s1
    s1.myNum = 13;
    s1.myLetter = 'B';
    
    // In giá trị
    printf("My number: %d\n", s1.myNum);
    printf("My letter: %c\n", s1.myLetter);
    
    return 0;
}
```

Bạn có thể tạo nhiều biến structure với các giá trị khác nhau:

```c
// Tạo các biến struct khác nhau
struct myStructure s1;
struct myStructure s2;

// Gán giá trị cho các biến struct khác nhau
s1.myNum = 13;
s1.myLetter = 'B';

s2.myNum = 20;
s2.myLetter = 'C';
```

#### Làm việc với String trong Structure

Khi sử dụng string trong structure, cần nhớ rằng string trong C là mảng ký tự. Bạn không thể gán giá trị trực tiếp cho mảng:

```c
struct myStructure {
    int myNum;
    char myLetter;
    char myString[30];  // String
};
```

Thay vào đó, sử dụng hàm `strcpy()` để gán giá trị cho string:

```c
struct myStructure {
    int myNum;
    char myLetter;
    char myString[30];
};

int main() {
    struct myStructure s1;
    
    // Gán giá trị cho string bằng strcpy
    strcpy(s1.myString, "Some text");
    
    // In giá trị
    printf("My string: %s", s1.myString);
    
    return 0;
}
```

#### Khởi tạo Structure đơn giản

Bạn có thể gán giá trị cho các thành viên structure ngay khi khai báo bằng danh sách các giá trị phân cách bởi dấu phẩy:

```c
struct myStructure {
    int myNum;
    char myLetter;
    char myString[30];
};

int main() {
    // Khởi tạo structure với giá trị
    struct myStructure s1 = {13, 'B', "Some text"};
    
    // In giá trị
    printf("%d %c %s", s1.myNum, s1.myLetter, s1.myString);
    
    return 0;
}
```

#### Sao chép và Sửa đổi Structure

Bạn có thể sao chép một structure sang structure khác:

```c
struct myStructure s1 = {13, 'B', "Some text"};
struct myStructure s2;

s2 = s1;  // Sao chép s1 sang s2
```

Để sửa đổi giá trị, sử dụng cú pháp dấu chấm hoặc `strcpy()` cho string:

```c
// Sửa đổi giá trị
s1.myNum = 30;
s1.myLetter = 'C';
strcpy(s1.myString, "Something else");
```

#### Ví dụ thực tế: Cơ sở dữ liệu xe hơi

Đây là một ví dụ thực tế sử dụng structure để lưu trữ thông tin xe hơi:

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