+++
title = "Các kiểu dữ liệu trong C"
weight = 7 
chapter = false
pre = " <b> 7. </b> "
+++

#### Tổng quan

Chương này đề cập đến các kiểu dữ liệu cơ bản trong lập trình C, bao gồm cách khai báo biến và sử dụng format specifier cho các thao tác input/output.

#### Biến cơ bản và Format Specifier 

Trong ngôn ngữ C, mỗi biến phải có một kiểu dữ liệu xác định. Dưới đây là cách tạo và in các loại biến khác nhau:

```c
// Khai báo biến
int myNum = 5;             // Số nguyên
float myFloatNum = 5.99;   // Số thực
char myLetter = 'D';       // Ký tự

// In biến
printf("%d\n", myNum);
printf("%f\n", myFloatNum);
printf("%c\n", myLetter);
```

#### Các kiểu dữ liệu cơ bản

Các kiểu dữ liệu cơ bản trong C gồm:

| Kiểu dữ liệu | Kích thước | Mô tả | Ví dụ |
|-----------|------|-------------|---------|
| int | 2 hoặc 4 bytes | Lưu trữ số nguyên không có phần thập phân | 1 |
| float | 4 bytes | Lưu trữ số thực (độ chính xác 6-7 chữ số thập phân) | 1.99 |
| double | 8 bytes | Lưu trữ số thực (độ chính xác 15 chữ số thập phân) | 1.99 |
| char | 1 byte | Lưu trữ một ký tự/chữ cái/số hoặc giá trị ASCII | 'A' |

#### Format Specifier

Khi sử dụng hàm `printf()`, mỗi kiểu dữ liệu cần format specifier riêng:

| Format Specifier | Kiểu dữ liệu | Cách dùng |
|-----------------|-----------|--------|
| %d hoặc %i | int | In số nguyên |
| %f hoặc %F | float | In số thực |
| %lf | double | In số thực độ chính xác kép |
| %c | char | In ký tự đơn |
| %s | string | In chuỗi ký tự |

#### Làm việc với ký tự

#### Kiểu dữ liệu char

Trong C, ký tự được lưu trữ bằng kiểu `char` và phải được đặt trong dấu nháy đơn:

```c
char myGrade = 'A';
printf("%c", myGrade);
```

#### Giá trị ASCII

Ký tự cũng có thể được biểu diễn bằng giá trị ASCII:

```c
char a = 65, b = 66, c = 67;  // Biểu diễn 'A', 'B', 'C'
printf("%c%c%c", a, b, c);    // In ra: ABC
```

#### Làm việc với số

#### Số nguyên

Với số nguyên, sử dụng kiểu dữ liệu `int`:

```c
int myNum = 1000;
printf("%d", myNum);
```

#### Số thực

Với số thập phân, có thể chọn giữa `float` và `double`:

```c
float myFloat = 5.75;
printf("%f", myFloat);

double myDouble = 19.99;
printf("%lf", myDouble);
```

#### Ký hiệu khoa học

Số lớn có thể được biểu diễn bằng ký hiệu khoa học:

```c
float f1 = 35e3;    // 35 x 10^3
double d1 = 12E4;   // 12 x 10^4

printf("%f\n", f1);   // Kết quả: 35000.000000
printf("%lf", d1);    // Kết quả: 120000.000000
```

#### Một số lưu ý quan trọng

1. **Khớp Format Specifier**
   - Luôn sử dụng format specifier chính xác cho mỗi kiểu dữ liệu
   - Format specifier không khớp có thể gây ra hành vi không mong muốn

2. **Lựa chọn kiểu dữ liệu**
   - Dùng `int` cho số nguyên
   - Ưu tiên dùng `double` thay vì `float` cho tính toán chính xác
   - Chỉ dùng `char` cho ký tự đơn

3. **Cân nhắc bộ nhớ**
   - Xem xét kích thước kiểu dữ liệu khi làm việc với bộ nhớ giới hạn
   - Dùng `float` thay vì `double` khi không cần độ chính xác cao

#### Lỗi thường gặp

1. **Lưu trữ ký tự**
   ```c
   char myText = 'Hello';   // Sai! Phải dùng string
   char myText[] = "Hello"; // Đúng với nhiều ký tự
   ```

2. **Sử dụng sai Format Specifier**
   ```c
   int num = 42;
   printf("%f", num);    // Sai! Phải dùng %d cho số nguyên
   printf("%d", num);    // Đúng
   ```

#### Nội dung tiếp theo

Trong các chương sau, chúng ta sẽ tìm hiểu:
- Array và string
- Chuyển đổi kiểu
- Hằng số và literal
- Các kiểu dữ liệu nâng cao

{{% notice note %}}
Nhớ biên dịch code với các flag phù hợp để phát hiện lỗi liên quan đến kiểu dữ liệu. Khuyến nghị sử dụng `-Wall` với gcc.
{{% /notice %}}