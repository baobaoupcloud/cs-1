+++
title = "Khai báo và Định nghĩa Function trong C"
weight = 25
chapter = false
pre = " <b> 25. </b> "
+++

#### Khai báo và Định nghĩa Function trong C

#### Cấu trúc Function cơ bản
Một function trong C gồm hai phần chính:
1. **Declaration** (Khai báo): Xác định tên function, kiểu giá trị trả về và các parameters (nếu có)
2. **Definition** (Định nghĩa): Chứa phần thân của function (code sẽ được thực thi)

#### Ví dụ Function cơ bản
```c
// Tạo một function
void myFunction() {
  printf("I just got executed!");
}

int main() {
  myFunction(); // gọi function
  return 0;
}
```

#### Tách riêng Declaration và Definition
Để tổ chức code tốt hơn và tối ưu hóa, nên tách riêng phần khai báo và định nghĩa function:

```c
// Function declaration
void myFunction();

// Hàm main
int main() {
  myFunction();  // gọi function
  return 0;
}

// Function definition 
void myFunction() {
  printf("I just got executed!");
}
```

#### Làm việc với Parameters và Return Values
Khi làm việc với parameters và return values của function, vẫn áp dụng nguyên tắc tách riêng:

```c
// Function declaration
int myFunction(int x, int y);

// Hàm main
int main() {
  int result = myFunction(5, 3); // gọi function
  printf("Result is = %d", result);
  return 0;
}

// Function definition
int myFunction(int x, int y) {
  return x + y;
}
```

#### Function gọi Function khác
Các function có thể gọi function khác miễn là chúng được khai báo trước:

```c
// Khai báo hai function
void myFunction();
void myOtherFunction();

int main() {
  myFunction(); // gọi myFunction (từ main)
  return 0;
}

// Định nghĩa myFunction
void myFunction() {
  printf("Some text in myFunction\n");
  myOtherFunction(); // gọi myOtherFunction (từ myFunction)
}

// Định nghĩa myOtherFunction
void myOtherFunction() {
  printf("Hey! Some text in myOtherFunction\n");
}
```

#### Các điểm quan trọng cần nhớ:
- Luôn khai báo function trước khi chúng được gọi
- Tách riêng phần declaration và definition để tổ chức code tốt hơn  
- Hàm main thường được đặt giữa phần declarations và definitions
- Function declarations (prototypes) phải khớp với definitions của chúng
- Đảm bảo kiểu return và danh sách parameters phù hợp ở cả declaration và definition