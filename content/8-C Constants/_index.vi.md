+++
title = "Hằng số trong lập trình C" 
weight = 8
chapter = false
pre = " <b> 8. </b> "
+++

#### Hằng số trong lập trình C

Hằng số (Constants) là các biến mà giá trị của chúng không thể thay đổi sau khi được khai báo. Chúng cung cấp cách tạo các giá trị chỉ đọc trong chương trình của bạn.

#### Khai báo hằng số

Để khai báo một hằng số, sử dụng từ khóa `const` trước kiểu dữ liệu:

```c
const int myNum = 15;  // myNum sẽ luôn là 15
// myNum = 10;  // LỖI: Không thể thay đổi giá trị của hằng số
```

#### Các trường hợp sử dụng phổ biến

Hằng số lý tưởng cho các giá trị cần được giữ nguyên trong suốt quá trình thực thi chương trình:

```c
const int MINUTES_PER_HOUR = 60;
const float PI = 3.14;
```

#### Các quy tắc quan trọng

#### Quy tắc 1: Bắt buộc khởi tạo giá trị ngay lập tức

Hằng số phải được khởi tạo giá trị khi khai báo:

```c
// Cách đúng:
const int MINUTES_PER_HOUR = 60;

// Cách sai - sẽ gây lỗi:
// const int MINUTES_PER_HOUR;
// MINUTES_PER_HOUR = 60;
```

#### Quy tắc 2: Quy ước đặt tên

Mặc dù không bắt buộc bởi ngôn ngữ, nhưng theo quy ước tốt là đặt tên hằng số bằng chữ in hoa:

```c
// Quy ước đặt tên được khuyến nghị
const int BIRTH_YEAR = 1980;
const float MAX_TEMPERATURE = 100.0;
```

Quy ước này giúp hằng số dễ dàng phân biệt với các biến thông thường trong mã của bạn và được sử dụng rộng rãi bởi các lập trình viên C.

#### Lợi ích của việc sử dụng hằng số

- Ngăn chặn việc vô tình thay đổi giá trị
- Giúp code dễ bảo trì hơn
- Cải thiện khả năng đọc hiểu code
- Giúp phát hiện lỗi tiềm ẩn trong quá trình biên dịch

Lưu ý rằng việc cố gắng thay đổi giá trị của hằng số sau khi khai báo sẽ dẫn đến lỗi biên dịch, điều này giúp bạn duy trì tính toàn vẹn dữ liệu trong chương trình.