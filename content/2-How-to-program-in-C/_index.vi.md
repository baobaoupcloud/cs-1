+++
title = "Lập trình bằng ngôn ngữ C" 
weight = 2
chapter = false
pre = " <b> 2. </b> "
+++

#### Bắt đầu với lập trình C

Chào mừng bạn đến với hướng dẫn toàn diện về lập trình C! Bài viết này sẽ hướng dẫn bạn những bước cơ bản để bắt đầu hành trình lập trình C, từ việc thiết lập môi trường phát triển đến viết chương trình đầu tiên.

#### Môi trường phát triển

Trong hướng dẫn này, chúng ta sẽ sử dụng **Visual Studio Code** (VS Code) làm IDE (Integrated Development Environment). VS Code mang đến nhiều lợi ích cho lập trình C:

- Nhẹ và nhanh
- Hỗ trợ extension C/C++ tốt
- Terminal tích hợp  
- Debugger tích hợp
- Code completion thông minh

#### Các lệnh cơ bản

Để làm việc hiệu quả với chương trình C, bạn cần nắm vững 3 lệnh cơ bản sau:

1. `code` - Tạo và chỉnh sửa file source
2. `make` - Biên dịch code
3. `./` - Chạy chương trình

#### Viết chương trình C đầu tiên

Hãy tạo một chương trình "Hello" đơn giản để hiểu quy trình cơ bản:

#### Tạo file source

Mở terminal và nhập:

```bash
code hello.c
```

#### Viết code

Trong VS Code editor, nhập chương trình cơ bản sau:

```c
#include <stdio.h>

int main(void)
{
    printf("hello, mate\n");
}
```

#### Biên dịch chương trình

Trong terminal, bạn có hai cách để biên dịch code:

Cách 1 - Sử dụng make:
```bash
make hello
```

Cách 2 - Sử dụng trực tiếp clang:
```bash
clang hello.c -o hello
```

#### Chạy chương trình

Thực thi chương trình bằng lệnh:
```bash
./hello
```

#### Tìm hiểu về thư viện C

C đi kèm với một bộ thư viện phong phú chứa các hàm được viết sẵn. Dưới đây là một số thư viện thường được sử dụng:

- `stdio.h`: Thao tác input/output
- `stdlib.h`: Tiện ích chung
- `string.h`: Xử lý chuỗi
- `math.h`: Phép toán
- `time.h`: Hàm thời gian và ngày tháng

#### Những lưu ý quan trọng khi lập trình

1. **Header Files**
   - Luôn include các header file cần thiết
   - Đảm bảo header phù hợp với hàm bạn sử dụng
   - Ví dụ: `#include <stdio.h>` cho `printf()`

2. **Quy tắc cú pháp**
   - Kết thúc câu lệnh bằng dấu chấm phẩy (`;`)
   - Sử dụng dấu ngoặc nhọn `{}` cho khối code
   - Chú ý phân biệt chữ hoa/thường

#### Lỗi thường gặp với người mới bắt đầu

1. Quên dấu chấm phẩy cuối câu lệnh
2. Thiếu hoặc không khớp dấu ngoặc nhọn
3. Không include header file cần thiết 
4. Viết sai chữ hoa/thường trong tên hàm
5. Quên lưu file trước khi biên dịch

#### Các bước tiếp theo

Sau khi đã tạo chương trình C đầu tiên, bạn đã sẵn sàng khám phá các khái niệm phức tạp hơn:

1. Biến và kiểu dữ liệu
2. Cấu trúc điều khiển (if/else, vòng lặp)
3. Hàm và tham số
4. Mảng và con trỏ
5. Cấu trúc và union