+++
title = "C Enumeration (enum)" 
weight = 29
chapter = false
pre = " <b> 29. </b> "
+++

#### C Enumeration (enum)

Trong ngôn ngữ lập trình C, enum (enumeration) là một kiểu dữ liệu đặc biệt dùng để định nghĩa một nhóm các hằng số (giá trị không thể thay đổi).

#### Cú pháp cơ bản

Để tạo một enum, sử dụng từ khóa `enum` theo sau là tên và liệt kê các phần tử trong dấu ngoặc nhọn:

```c
enum Level {
    LOW,
    MEDIUM, 
    HIGH
};
```

*Lưu ý: Phần tử cuối cùng không cần dấu phẩy.*

#### Sử dụng Enum

Để sử dụng enum, tạo một biến thuộc kiểu enum:

```c
enum Level myVar;       // Khai báo biến enum
myVar = MEDIUM;        // Gán giá trị
```

Bạn cũng có thể khai báo và khởi tạo trong cùng một dòng:

```c
enum Level myVar = MEDIUM;
```

#### Giá trị mặc định

Theo mặc định, các giá trị enum bắt đầu từ 0 và tăng dần 1 đơn vị:
- `LOW` = 0
- `MEDIUM` = 1  
- `HIGH` = 2

#### Giá trị tùy chỉnh

Bạn có thể gán các giá trị tùy chỉnh cho các phần tử enum:

```c
enum Level {
    LOW = 25,
    MEDIUM = 50,
    HIGH = 75
};
```

Nếu bạn gán giá trị cho một phần tử, các phần tử tiếp theo sẽ tăng dần từ giá trị đó:

```c
enum Level {
    LOW = 5,    // 5
    MEDIUM,     // 6  
    HIGH        // 7
};
```

#### Sử dụng Enum trong Switch

Enum hoạt động tốt với câu lệnh switch:

```c
enum Level {
    LOW = 1,
    MEDIUM,
    HIGH
};

int main() {
    enum Level myVar = MEDIUM;
    
    switch (myVar) {
        case 1:
            printf("Low Level");
            break;
        case 2:
            printf("Medium level"); 
            break;
        case 3:
            printf("High level");
            break;
    }
    return 0;
}
```

#### Các nguyên tắc thực hành tốt

1. Sử dụng CHỮ HOA cho các hằng số enum (không bắt buộc)
2. Dùng enum cho các hằng số có liên quan và không thay đổi
3. Các trường hợp sử dụng phổ biến:
   - Số ngày trong tháng
   - Các ngày trong tuần
   - Mã màu
   - Chất của bộ bài
   - Mã trạng thái
   - Tùy chọn menu

#### Lợi ích của việc sử dụng Enum

1. Làm cho code dễ đọc hơn
2. Đảm bảo tính an toàn cho kiểu dữ liệu
3. Dễ dàng bảo trì
4. Code tự giải thích
5. Tổ chức tốt hơn các hằng số có liên quan