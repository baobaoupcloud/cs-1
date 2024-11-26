+++
title = "C Functions" 
weight = 22
chapter = false
pre = " <b> 22. </b> "
+++

#### C Functions

Functions (hàm) là những thành phần cơ bản không thể thiếu trong lập trình C, cho phép bạn tổ chức và tái sử dụng code một cách hiệu quả. Function là một khối code sẽ được thực thi khi được gọi, và có thể nhận các tham số đầu vào.

#### Tìm hiểu về Functions

Functions phục vụ nhiều mục đích:
- Thực thi các tác vụ cụ thể
- Cho phép tái sử dụng code 
- Tổ chức code thành các khối dễ quản lý
- Xử lý các tham số đầu vào
- Trả về kết quả

#### Các Functions có sẵn

Bạn đã làm quen với một số functions có sẵn trong C. Ví dụ, `main()` và `printf()` là các functions tích hợp sẵn:

```c
int main() {
    printf("Hello World!");
    return 0;
}
```

#### Tạo Functions

Để khai báo một function, chỉ định tên function theo sau là dấu ngoặc đơn `()` và dấu ngoặc nhọn `{}`:

#### Cú pháp cơ bản

```c
void myFunction() {
    // code sẽ được thực thi
}
```

#### Giải thích các thành phần của Function

- `myFunction()` - tên của function
- `void` - cho biết không có giá trị trả về  
- Thân function - code nằm giữa cặp dấu ngoặc nhọn

#### Gọi Functions 

Để thực thi một function, gọi nó bằng cách viết tên function theo sau là dấu ngoặc đơn và dấu chấm phẩy:

```c
// Định nghĩa function
void myFunction() {
    printf("I just got executed!");
}

int main() {
    myFunction(); // gọi function
    return 0;
}
```

#### Gọi Functions nhiều lần

Bạn có thể gọi cùng một function nhiều lần:

```c
void myFunction() {
    printf("I just got executed!");
}

int main() {
    myFunction();
    myFunction();
    myFunction();
    return 0;
}

// Output:
// I just got executed!
// I just got executed!
// I just got executed!
```

#### Ví dụ thực tế: Tính toán số

Đây là một ví dụ thực tế về function tính tổng hai số:

```c
void calculateSum() {
    int x = 5;
    int y = 10;
    int sum = x + y;
    printf("The sum of x + y is: %d", sum);
}

int main() {
    calculateSum();  // gọi function
    return 0;
}

// Output: The sum of x + y is: 15
```

#### Lưu ý về tính linh hoạt của Function

Ví dụ này sử dụng các giá trị cố định (5 và 10). Trong thực tế, functions sẽ mạnh mẽ hơn khi chúng chấp nhận các tham số, cho phép tính toán linh hoạt với các giá trị đầu vào khác nhau. Khái niệm này sẽ được đề cập trong phần tiếp theo về tham số của function.

#### Những điểm quan trọng cần nhớ

1. Functions phải được khai báo trước khi sử dụng
2. Tên function nên mô tả được chức năng và tuân theo quy ước đặt tên trong C
3. Từ khóa `void` cho biết không có giá trị trả về
4. Functions có thể được gọi nhiều lần
5. Code trong functions chỉ thực thi khi function được gọi