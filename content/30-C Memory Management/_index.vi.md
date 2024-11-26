+++
title = "C Memory Management" 
weight = 30
chapter = false
pre = " <b> 30. </b> "
+++

#### C Memory Management

Memory management là quá trình xử lý việc một chương trình sử dụng bao nhiêu bộ nhớ thông qua các thao tác khác nhau.

#### Bộ nhớ trong C

Việc hiểu cách bộ nhớ hoạt động trong C là rất quan trọng. Khi bạn tạo một biến cơ bản, C sẽ tự động dành riêng không gian cho biến đó. Ví dụ, một biến `int` thường chiếm 4 bytes bộ nhớ, trong khi biến `double` sẽ chiếm 8 bytes bộ nhớ.

Bạn có thể sử dụng toán tử `sizeof` để tìm kích thước của các kiểu dữ liệu khác nhau:

#### Ví dụ

```c
int myInt;
float myFloat;
double myDouble;
char myChar;

printf("%lu\n", sizeof(myInt));      // 4 bytes
printf("%lu\n", sizeof(myFloat));    // 4 bytes  
printf("%lu\n", sizeof(myDouble));   // 8 bytes
printf("%lu\n", sizeof(myChar));     // 1 byte
```

#### Tại sao việc này lại quan trọng?

Nếu bạn tạo một chương trình chiếm quá nhiều hoặc sử dụng bộ nhớ không cần thiết, nó có thể dẫn đến hiệu năng chậm và kém.

Trong C, bạn phải tự quản lý bộ nhớ. Đây là một tác vụ phức tạp, nhưng cũng rất mạnh mẽ khi được sử dụng đúng cách:

* Quản lý bộ nhớ máy tính đúng cách sẽ tối ưu hóa hiệu năng của chương trình
* Bạn cần biết cách giải phóng bộ nhớ khi không còn cần thiết nữa 
* Chỉ sử dụng lượng bộ nhớ tối thiểu cần thiết cho tác vụ

#### Memory Addresses và Pointers 

Trong các chương trước, bạn đã học về memory addresses và pointers.

Cả hai đều quan trọng khi nói đến memory management, vì có thể làm việc trực tiếp với bộ nhớ thông qua pointers.

> **Quan trọng**: Pointers phải được xử lý cẩn thận, vì có thể làm hỏng dữ liệu được lưu trữ ở các memory addresses khác.

#### Các thao tác Memory Management

Memory management là quá trình xử lý việc một chương trình sử dụng bao nhiêu bộ nhớ thông qua ba thao tác chính:

1. Allocation (Cấp phát)
2. Reallocation (Cấp phát lại)
3. Deallocation (Giải phóng - thường được gọi là "freeing")