+++
title = "Switch Statement trong C" 
weight = 12
chapter = false
pre = " <b> 12. </b> "
+++

#### Switch Statement trong C

Trong lập trình C, switch statement cung cấp một cách hiệu quả thay thế cho nhiều câu lệnh if-else. Nó cho phép bạn chọn một khối code từ nhiều lựa chọn dựa trên một biểu thức cụ thể.

#### Cú pháp cơ bản

```c
switch (expression) {
    case x:
        // khối code
        break;
    case y:
        // khối code 
        break;
    default:
        // khối code
}
```

#### Cách hoạt động

Switch statement hoạt động bằng cách:
1. Đánh giá biểu thức một lần
2. So sánh giá trị của biểu thức với từng case
3. Thực thi khối code của case phù hợp
4. Sử dụng break để thoát khỏi khối switch
5. Chuyển sang default nếu không có case nào khớp

#### Ví dụ: Tên các ngày trong tuần

```c
int day = 4;

switch (day) {
    case 1:
        printf("Monday");
        break;
    case 2:
        printf("Tuesday"); 
        break;
    case 3:
        printf("Wednesday");
        break;
    case 4:
        printf("Thursday");
        break;
    case 5:
        printf("Friday");
        break;
    case 6:
        printf("Saturday");
        break;
    case 7:
        printf("Sunday");
        break;
}
// Kết quả là "Thursday" (ngày 4)
```

#### Từ khóa break

Câu lệnh break phục vụ một số mục đích quan trọng:
- Thoát khỏi khối switch
- Ngăn việc thực thi các case tiếp theo
- Cải thiện hiệu quả thực thi
- Tránh hành vi fall-through không mong muốn

#### Từ khóa default

Default cung cấp một lựa chọn dự phòng khi không có case nào khớp:

```c
int day = 4;

switch (day) {
    case 6:
        printf("Hôm nay là thứ bảy");
        break;
    case 7:
        printf("Hôm nay là chủ nhật");
        break;
    default:
        printf("Đang mong đợi đến cuối tuần");
}
// Kết quả là "Đang mong đợi đến cuối tuần"
```

Những điểm quan trọng về default:
- Phải là câu lệnh cuối cùng trong switch
- Không yêu cầu câu lệnh break
- Được thực thi khi không có case nào khớp
- Là tùy chọn nhưng được khuyến nghị để xử lý lỗi