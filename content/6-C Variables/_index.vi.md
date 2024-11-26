+++
title = "Biến trong C" 
weight = 6
chapter = false
pre = " <b> 6. </b> "
+++

#### Tổng quan

Biến (Variables) đóng vai trò như các container để lưu trữ giá trị dữ liệu như số và ký tự trong lập trình C. Hiểu cách làm việc với biến là nền tảng cơ bản trong lập trình C.

#### Các kiểu biến cơ bản

#### Số nguyên (Integer - int)
- Lưu trữ số nguyên không có phần thập phân
- Ví dụ: `123`, `-123` 
- Không có giá trị phân số hoặc thập phân

#### Số thực (Float)
- Lưu trữ số có dấu thập phân
- Ví dụ: `19.99`, `-19.99`
- Phù hợp cho các phép tính chính xác

#### Ký tự (Character - char)  
- Lưu trữ một ký tự đơn
- Phải được đặt trong dấu nháy đơn
- Ví dụ: `'a'`, `'B'`

#### Khai báo biến

#### Cú pháp cơ bản
```c
type tenBien = giaTri;
```

#### Ví dụ khai báo
```c
// Khởi tạo trực tiếp
int soToi = 15;

// Khai báo và gán giá trị riêng biệt  
int soToi;      // Khai báo biến
soToi = 15;     // Gán giá trị
```

#### Xuất biến

#### Sử dụng printf()
Hàm `printf()` được dùng để hiển thị giá trị biến trong C.

```c
// Cách sai
int soToi = 15; 
printf(soToi);    // Cách này không hoạt động

// Cách đúng
int soToi = 15;
printf("%d", soToi);    // Sẽ hiển thị 15
```

#### Format Specifiers
Khi xuất biến, sử dụng các format specifiers sau:
- `%d` - cho số nguyên (int)
- `%f` - cho số thực (float) 
- `%c` - cho ký tự đơn (char)

#### Format Specifiers nâng cao

#### Bảng Format Specifiers
| Specifier | Kiểu dữ liệu | Ví dụ giá trị |
|-----------|--------------|---------------|
| %d | int | 42 |
| %f | float | 3.14 |
| %c | char | 'A' |
| %s | string | "Hello" |
| %lf | double | 3.14159265359 |
| %x hoặc %X | hexadecimal | 0xFF |
| %o | octal | 075 |
| %p | pointer | 0x7ffee2d7e8f0 |

#### Ví dụ về độ rộng và độ chính xác
```c
float pi = 3.14159;
printf("Mặc định: %f\n", pi);        // 3.141590
printf("Độ rộng 8: %8f\n", pi);      //  3.141590
printf("Độ chính xác 2: %.2f\n", pi); // 3.14
```

#### Những thực hành tốt nhất

1. Chọn tên biến có ý nghĩa mô tả
2. Khởi tạo giá trị cho biến khi khai báo
3. Sử dụng kiểu dữ liệu phù hợp cho giá trị
4. Tuân thủ quy tắc đặt tên nhất quán

#### Lỗi thường gặp cần tránh

- Quên khởi tạo giá trị cho biến
- Sử dụng biến trước khi khai báo
- In biến mà không dùng format specifiers
- Dùng sai format specifiers với kiểu dữ liệu

#### Bài tập thực hành

Tạo chương trình sử dụng các kiểu biến khác nhau:

```c
#include <stdio.h>

int main() {
    // Khai báo biến
    int tuoi = 25;
    float chieuCao = 5.9;
    char xepLoai = 'A';
    
    // Xuất với format specifiers phù hợp
    printf("Tuổi: %d\n", tuoi);
    printf("Chiều cao: %.1f\n", chieuCao);
    printf("Xếp loại: %c\n", xepLoai);
    
    return 0;
}
```

#### Ví dụ thực tế

#### Quản lý dữ liệu sinh viên
```c
// Lưu trữ dữ liệu sinh viên
int maSV = 15;
int tuoiSV = 23;
float hocPhi = 75.25;
char xepLoai = 'B';

// In thông tin sinh viên
printf("Mã SV: %d\n", maSV);
printf("Tuổi SV: %d\n", tuoiSV);
printf("Học phí: %.2f\n", hocPhi);
printf("Xếp loại: %c\n", xepLoai);
```

#### Tính diện tích hình chữ nhật
```c
// Biến cho kích thước hình chữ nhật
int chieuDai = 4;
int chieuRong = 6;
int dienTich;

// Tính diện tích
dienTich = chieuDai * chieuRong;

// Hiển thị kết quả
printf("Chiều dài: %d\n", chieuDai);
printf("Chiều rộng: %d\n", chieuRong);
printf("Diện tích: %d đơn vị vuông\n", dienTich);
```

#### Khai báo nhiều biến

Bạn có thể khai báo nhiều biến theo nhiều cách:

```c
// Khai báo ngăn cách bằng dấu phẩy
int x = 5, y = 6, z = 50;

// Cùng giá trị cho nhiều biến
int a, b, c;
a = b = c = 100;

// Khai báo riêng từng dòng cho rõ ràng
int chieuCao = 180;
int canNang = 75;
int tuoi = 25;
```

#### Kết luận

Hiểu về biến và cách sử dụng đúng là điều quan trọng trong lập trình C. Hãy nhớ:
- Chọn kiểu dữ liệu phù hợp
- Khởi tạo biến trước khi sử dụng
- Dùng format specifiers đúng
- Tuân thủ quy tắc đặt tên nhất quán
- Thực hành với ví dụ thực tế

Để tìm hiểu thêm các chủ đề nâng cao và bài tập, hãy xem phần tiếp theo về cấu trúc điều khiển trong C.