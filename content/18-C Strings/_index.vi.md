+++
title = "Chuỗi ký tự trong lập trình C" 
weight = 18
chapter = false
pre = " <b> 18. </b> "
+++

#### Chuỗi ký tự trong lập trình C

#### Giới thiệu
Chuỗi trong C được dùng để lưu trữ văn bản và ký tự. Ví dụ, `"Hello World"` là một chuỗi các ký tự.

Khác với nhiều ngôn ngữ lập trình khác, C không có kiểu String có sẵn. Thay vào đó, chúng ta sử dụng kiểu `char` và tạo một mảng các ký tự:

```c
char greetings[] = "Hello World!";
```

**Lưu ý**: Luôn sử dụng dấu ngoặc kép (`" "`) cho chuỗi.

#### Xuất chuỗi
Để xuất chuỗi, sử dụng hàm `printf()` với định dạng `%s`:

```c
char greetings[] = "Hello World!";
printf("%s", greetings);
```

#### Truy cập từng ký tự
Vì chuỗi là mảng trong C, bạn có thể truy cập từng ký tự riêng lẻ bằng chỉ số:

```c
char greetings[] = "Hello World!";
printf("%c", greetings[0]);  // In ra 'H'
```

**Lưu ý**: Sử dụng định dạng `%c` để in ký tự đơn.

#### Chỉnh sửa chuỗi
Để thay đổi một ký tự cụ thể, tham chiếu đến chỉ số của nó và sử dụng dấu nháy đơn:

```c
char greetings[] = "Hello World!";
greetings[0] = 'J';
printf("%s", greetings);  // Kết quả "Jello World!"
```

#### Duyệt qua chuỗi
Bạn có thể duyệt qua chuỗi bằng vòng lặp for:

```c
char carName[] = "Volvo";
int i;

// Cách 1: Độ dài thủ công
for (i = 0; i < 5; ++i) {
    printf("%c\n", carName[i]);
}

// Cách 2: Sử dụng sizeof
int length = sizeof(carName) / sizeof(carName[0]);
for (i = 0; i < length; ++i) {
    printf("%c\n", carName[i]);
}
```

#### Các cách tạo chuỗi
Có hai cách để tạo chuỗi trong C:

#### 1. Chuỗi ký tự trực tiếp (Khuyến nghị)
```c
char greetings[] = "Hello World!";
```

#### 2. Mảng ký tự
```c
char greetings[] = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd', '!', '\0'};
```

**Quan trọng**: Ký tự `\0` là "ký tự kết thúc chuỗi" và bắt buộc phải có khi tạo chuỗi bằng phương pháp mảng ký tự.

#### So sánh kích thước
Cả hai phương pháp đều tạo ra mảng có cùng kích thước:

```c
char greetings[] = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd', '!', '\0'};
char greetings2[] = "Hello World!";

printf("%lu\n", sizeof(greetings));   // Kết quả 13
printf("%lu\n", sizeof(greetings2));  // Kết quả 13
```

#### Ví dụ thực tế
Tạo thông điệp chào mừng bằng cách kết hợp các chuỗi:

```c
char message[] = "Good to see you,";
char fname[] = "John";

printf("%s %s!", message, fname);  // Kết quả "Good to see you, John!"
```