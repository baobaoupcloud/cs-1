+++
title = "Con trỏ trong C"
weight = 21
chapter = false
pre = " <b> 21. </b> "
+++

#### Con trỏ trong lập trình C

#### Tạo con trỏ (Pointers)

Trong chương trước, bạn đã biết rằng chúng ta có thể lấy địa chỉ bộ nhớ của một biến bằng toán tử tham chiếu `&`:

```c
int myAge = 43;     // một biến kiểu int 

printf("%d", myAge);   // In ra giá trị của myAge (43)
printf("%p", &myAge);  // In ra địa chỉ bộ nhớ của myAge (0x7ffe5367e044)
```

Pointer là một biến lưu trữ địa chỉ bộ nhớ của một biến khác. Một biến pointer trỏ đến một kiểu dữ liệu (như `int`) cùng loại và được tạo ra với toán tử `*`. Địa chỉ của biến bạn đang làm việc được gán cho pointer:

```c
int myAge = 43;      // Một biến kiểu int
int* ptr = &myAge;   // Một biến pointer tên ptr lưu địa chỉ của myAge

// In ra giá trị của myAge (43)
printf("%d\n", myAge);

// In ra địa chỉ bộ nhớ của myAge (0x7ffe5367e044)
printf("%p\n", &myAge);

// In ra địa chỉ bộ nhớ của myAge thông qua pointer (0x7ffe5367e044)
printf("%p\n", ptr);
```

#### Hiểu về ví dụ trên

1. Tạo một biến pointer tên `ptr` trỏ đến biến kiểu `int` (`myAge`)
2. Kiểu của pointer phải khớp với kiểu của biến bạn đang làm việc (`int` trong ví dụ này)
3. Sử dụng toán tử `&` để lưu địa chỉ bộ nhớ của biến `myAge` và gán nó cho pointer
4. Lúc này, `ptr` chứa giá trị là địa chỉ bộ nhớ của `myAge`

#### Toán tử giải tham chiếu (Dereference)

Trong khi chúng ta dùng biến pointer để lấy địa chỉ bộ nhớ của một biến (với toán tử tham chiếu `&`), chúng ta cũng có thể lấy giá trị của biến mà pointer đang trỏ tới bằng toán tử `*` (toán tử giải tham chiếu):

```c
int myAge = 43;      // Khai báo biến
int* ptr = &myAge;   // Khai báo pointer

// Tham chiếu: In ra địa chỉ bộ nhớ của myAge qua pointer (0x7ffe5367e044)
printf("%p\n", ptr);

// Giải tham chiếu: In ra giá trị của myAge qua pointer (43)
printf("%d\n", *ptr);
```

**Lưu ý**: Dấu `*` có hai mục đích khác nhau:
- Trong khai báo (`int* ptr`): Tạo một biến pointer
- Ngoài khai báo: Đóng vai trò như toán tử giải tham chiếu

#### Cú pháp khai báo pointer thay thế 

Có hai cách hợp lệ để khai báo biến pointer trong C:
```c
int* myNum;
int *myNum;
```

#### Những điểm quan trọng về Pointer

Pointer là một tính năng đặc biệt của C, khác biệt với các ngôn ngữ như Python và Java. Chúng rất quan trọng vì:

1. Cho phép thao tác trực tiếp với dữ liệu trong bộ nhớ máy tính
2. Có thể giảm code và cải thiện hiệu năng
3. Cần thiết để triển khai các cấu trúc dữ liệu như:
   - Lists (Danh sách)
   - Trees (Cây)
   - Graphs (Đồ thị)
4. Bắt buộc cho một số thao tác như:
   - File handling (Xử lý file)
   - Memory management (Quản lý bộ nhớ)

**Cảnh báo**: Xử lý pointer cẩn thận, vì chúng có thể làm hỏng dữ liệu được lưu ở các địa chỉ bộ nhớ khác nếu không sử dụng đúng cách.

#### Pointer và Mảng trong C

#### Mảng và địa chỉ bộ nhớ

Khi làm việc với mảng trong C, bạn có thể sử dụng pointer để truy cập các phần tử mảng. Hãy tìm hiểu khái niệm này:

#### Ví dụ mảng cơ bản
```c
int myNumbers[4] = {25, 50, 75, 100};
int i;

// Duyệt mảng theo cách truyền thống
for (i = 0; i < 4; i++) {
    printf("%d\n", myNumbers[i]);
}
```

Kết quả:
```
25
50
75
100
```

#### Địa chỉ bộ nhớ của các phần tử mảng
```c
int myNumbers[4] = {25, 50, 75, 100};
int i;

for (i = 0; i < 4; i++) {
    printf("%p\n", &myNumbers[i]);
}
```

Ví dụ kết quả:
```
0x7ffe70f9d8f0
0x7ffe70f9d8f4
0x7ffe70f9d8f8
0x7ffe70f9d8fc
```

Chú ý mỗi địa chỉ cách nhau 4 bytes - điều này là do một số nguyên thường chiếm 4 bytes trong bộ nhớ:

```c
// Minh họa kích thước số nguyên
int myInt;
printf("%lu", sizeof(myInt));  // Kết quả: 4

// Minh họa kích thước mảng
int myNumbers[4] = {25, 50, 75, 100};
printf("%lu", sizeof(myNumbers));  // Kết quả: 16 (4 bytes * 4 phần tử)
```

#### Hiểu mối quan hệ Mảng-Pointer

Trong C, tên mảng hoạt động như một pointer trỏ đến phần tử đầu tiên. Đây là cách chúng ta có thể kiểm chứng điều này:

```c
int myNumbers[4] = {25, 50, 75, 100};

// Cả hai đều in ra cùng địa chỉ
printf("%p\n", myNumbers);        // Tên mảng
printf("%p\n", &myNumbers[0]);    // Địa chỉ phần tử đầu tiên
```

#### Truy cập phần tử mảng sử dụng Pointer

Bạn có thể dùng phép toán pointer để truy cập phần tử mảng:

```c
int myNumbers[4] = {25, 50, 75, 100};

// Truy cập phần tử đầu tiên
printf("%d\n", *myNumbers);           // Kết quả: 25

// Truy cập các phần tử tiếp theo
printf("%d\n", *(myNumbers + 1));     // Kết quả: 50
printf("%d\n", *(myNumbers + 2));     // Kết quả: 75
```

#### Duyệt mảng bằng Pointer

```c
int myNumbers[4] = {25, 50, 75, 100};
int *ptr = myNumbers;
int i;

for (i = 0; i < 4; i++) {
    printf("%d\n", *(ptr + i));
}
```

#### Sửa đổi phần tử mảng bằng Pointer

```c
int myNumbers[4] = {25, 50, 75, 100};

// Sửa đổi phần tử sử dụng pointer
*myNumbers = 13;              // Thay đổi phần tử đầu tiên
*(myNumbers + 1) = 17;       // Thay đổi phần tử thứ hai

printf("%d\n", *myNumbers);           // Kết quả: 13
printf("%d\n", *(myNumbers + 1));     // Kết quả: 17
```

#### Những điểm quan trọng

1. Phép toán pointer đặc biệt hiệu quả cho:
   - Mảng lớn
   - Mảng hai chiều
   - Xử lý chuỗi (chuỗi là mảng ký tự)

2. **Cảnh báo**: Xử lý pointer cẩn thận vì sử dụng không đúng có thể ghi đè lên bộ nhớ và gây ra hành vi không xác định.

3. Cách tiếp cận dùng pointer có vẻ phức tạp cho mảng đơn giản, nhưng nó trở nên có giá trị khi làm việc với cấu trúc dữ liệu lớn hơn và thao tác bộ nhớ phức tạp.