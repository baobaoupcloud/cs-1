+++
title = "Output và Input trong C" 
weight = 4
chapter = false
pre = " <b> 4. </b> "
+++

#### Output và Input trong C

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách tạo output text trong ngôn ngữ lập trình C, từ in ấn cơ bản đến output có định dạng.

#### Output Cơ Bản

Nền tảng của output trong C là hàm `printf()`, được cung cấp từ thư viện input/output chuẩn. Dưới đây là ví dụ đơn giản:

```c
#include <stdio.h>

int main() {
    printf("Hello World!");
    return 0;
}
```

#### Làm Việc với Text String

Text string trong C phải được đặt trong dấu ngoặc kép (`""`). Hãy xem cách đúng và sai:

#### ✅ Cách đúng:
```c
printf("Đây là text string hợp lệ");
```

#### ❌ Cách sai:
```c
printf(Cách này sẽ gây lỗi);
```

#### Nhiều Lệnh Print

Bạn có thể sử dụng nhiều lệnh `printf()` liên tiếp. Lưu ý rằng mặc định, `printf()` không tự động thêm xuống dòng:

```c
#include <stdio.h>

int main() {
    printf("Hello World!");
    printf("Tôi đang học C.");
    printf("Và nó thật tuyệt vời!");
    return 0;
}
```

Output:
```
Hello World!Tôi đang học C.Và nó thật tuyệt vời!
```

#### Thêm Xuống Dòng

Để tạo output dễ đọc hơn, sử dụng ký tự escape `\n` để xuống dòng:

```c
#include <stdio.h>

int main() {
    printf("Hello World!\n");
    printf("Tôi đang học C.\n");
    printf("Và nó thật tuyệt vời!\n");
    return 0;
}
```

Output:
```
Hello World!
Tôi đang học C.
Và nó thật tuyệt vời!
```

#### Mẹo Để Output Hiệu Quả

Một số mẹo quan trọng cần nhớ khi làm việc với output trong C:

1. Luôn include thư viện `stdio.h`
2. Nhớ sử dụng dấu ngoặc kép cho text string
3. Dùng `\n` để xuống dòng
4. Kết thúc mỗi câu lệnh bằng dấu chấm phẩy
5. Kiểm tra các dấu ngoặc đóng mở đúng cặp

#### Các Hàm Output Phổ Biến

C cung cấp một số hàm cho output:

- `printf()` - Output có định dạng với khả năng kiểm soát cách hiển thị
- `puts()` - Output string với tự động xuống dòng
- `putchar()` - Output một ký tự đơn

#### Ví Dụ với Output Có Định Dạng

Đây là cách sử dụng output có định dạng với các kiểu dữ liệu khác nhau:

```c
#include <stdio.h>

int main() {
    int tuoi = 25;
    float chieuCao = 1.75;
    
    printf("Tuổi: %d\n", tuoi);
    printf("Chiều cao: %.2f mét\n", chieuCao);
    return 0;
}
```

Output:
```
Tuổi: 25
Chiều cao: 1.75 mét
```

#### Bài Tập Thực Hành

Tạo một chương trình in thông tin cá nhân của bạn với định dạng phù hợp. Bao gồm:
- Tên của bạn
- Tuổi của bạn
- Ngôn ngữ lập trình yêu thích

#### Mẫu Giải
```c
#include <stdio.h>

int main() {
    printf("Tên: [Tên của bạn]\n");
    printf("Tuổi: [Tuổi của bạn]\n");
    printf("Ngôn ngữ yêu thích: [Ngôn ngữ]\n");
    return 0;
}
```

#### Output Mẫu
```
Tên: Nguyễn Văn A
Tuổi: 25
Ngôn ngữ yêu thích: C
```

#### Điểm Chính Cần Nhớ

1. Luôn include thư viện cần thiết (`stdio.h`)
2. Sử dụng định dạng string đúng với dấu ngoặc kép
3. Nhớ dùng xuống dòng (`\n`) để output dễ đọc
4. Hiểu rõ các hàm output khác nhau
5. Thực hành định dạng và tổ chức code đúng cách