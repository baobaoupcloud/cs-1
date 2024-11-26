+++
title = "Câu lệnh điều kiện trong C" 
weight = 11
chapter = false
pre = " <b> 11. </b> "
+++

#### Câu lệnh điều kiện trong C

#### Các điều kiện logic

C hỗ trợ các điều kiện logic toán học tiêu chuẩn:

- Nhỏ hơn: `a < b`
- Nhỏ hơn hoặc bằng: `a <= b` 
- Lớn hơn: `a > b`
- Lớn hơn hoặc bằng: `a >= b`
- Bằng: `a == b`
- Không bằng: `a != b`

Các điều kiện này cho phép thực hiện các hành động khác nhau dựa trên logic quyết định.

#### Các loại câu lệnh điều kiện

C cung cấp một số câu lệnh điều kiện:

1. `if` - Thực thi code khi điều kiện đúng
2. `else` - Thực thi code khi điều kiện sai
3. `else if` - Kiểm tra điều kiện mới khi điều kiện trước đó sai  
4. `switch` - Thực thi các khối code khác nhau dựa trên nhiều điều kiện

#### Câu lệnh if

Câu lệnh `if` sẽ thực thi một khối code khi điều kiện được chỉ định là đúng.

#### Cú pháp

```c
if (condition) {
    // khối code được thực thi nếu điều kiện đúng
}
```

**Lưu ý**: `if` phải viết thường. Sử dụng `If` hoặc `IF` sẽ gây ra lỗi biên dịch.

#### Ví dụ

Kiểm tra giá trị số:
```c
if (20 > 18) {
    printf("20 lớn hơn 18");
}
```

Kiểm tra biến:
```c
int x = 20;
int y = 18;
if (x > y) {
    printf("x lớn hơn y");
}
```

#### Giải thích ví dụ

Trong ví dụ biến ở trên:
- Ta khai báo hai biến: `x` có giá trị 20 và `y` có giá trị 18
- Câu lệnh `if` kiểm tra xem `x` có lớn hơn `y` không bằng toán tử `>`
- Do 20 lớn hơn 18 nên điều kiện là đúng  
- Chương trình in ra màn hình "x lớn hơn y"

#### Câu lệnh else trong C

Câu lệnh `else` cho phép bạn thực thi một khối code khác khi điều kiện `if` là sai. Điều này tạo ra cấu trúc quyết định nhị phân trong chương trình của bạn.

#### Cú pháp

```c
if (condition) {
    // khối code được thực thi khi điều kiện đúng
} else {
    // khối code được thực thi khi điều kiện sai  
}
```

#### Ví dụ 

Đây là một ví dụ đơn giản kiểm tra thời gian và in lời chào phù hợp:

```c
int time = 20;

if (time < 18) {
    printf("Chào ngày mới.");
} else {
    printf("Chào buổi tối.");
}
// Kết quả: "Chào buổi tối."
```

#### Cách hoạt động

1. Đầu tiên, điều kiện trong câu lệnh `if` được đánh giá
2. Nếu điều kiện là `false` (trong trường hợp này, 20 không nhỏ hơn 18)
3. Chương trình bỏ qua khối code đầu tiên 
4. Chương trình thực thi khối code sau câu lệnh `else`
5. Trong ví dụ này, nó in ra "Chào buổi tối."

#### Các trường hợp sử dụng phổ biến

Bạn có thể sử dụng câu lệnh `if...else` cho nhiều tình huống:

```c
// Kiểm tra số dương hay âm
int number = -5;

if (number >= 0) {
    printf("Số này là số dương.");
} else {
    printf("Số này là số âm.");
}

// Kiểm tra học sinh đậu hay rớt
int score = 75;
int passingGrade = 60;

if (score >= passingGrade) {
    printf("Học sinh đậu!");
} else {
    printf("Học sinh rớt.");
}
```

#### Các nguyên tắc thực hành tốt

1. Luôn sử dụng dấu ngoặc nhọn `{}` ngay cả với câu lệnh đơn
2. Giữ các khối code thụt lề đúng để dễ đọc hơn
3. Đảm bảo điều kiện được viết rõ ràng và dễ hiểu
4. Cân nhắc sử dụng `else if` khi cần kiểm tra nhiều điều kiện

Lưu ý rằng câu lệnh `else` là tùy chọn - bạn có thể sử dụng câu lệnh `if` mà không cần `else` khi chỉ cần thực thi code cho điều kiện đúng.

#### Câu lệnh `else if`

Sử dụng câu lệnh `else if` để chỉ định một điều kiện mới nếu điều kiện đầu tiên là sai.

#### Cú pháp

```c
if (condition1) {
    // khối code được thực thi nếu condition1 đúng
} else if (condition2) {
    // khối code được thực thi nếu condition1 sai và condition2 đúng
} else {
    // khối code được thực thi nếu condition1 sai và condition2 sai
}
```

#### Ví dụ

```c
int time = 22;
if (time < 10) {
    printf("Chào buổi sáng.");
} else if (time < 20) {
    printf("Chào ngày mới.");
} else {
    printf("Chào buổi tối.");
}
// Kết quả là "Chào buổi tối."
```

Trong ví dụ này:
- Nếu time nhỏ hơn 10, in ra "Chào buổi sáng"
- Nếu time nhỏ hơn 20 (nhưng lớn hơn hoặc bằng 10), in ra "Chào ngày mới"
- Nếu cả hai điều kiện đều sai (time lớn hơn hoặc bằng 20), in ra "Chào buổi tối"

Kết quả là "Chào buổi tối" vì biến `time` là 22, lớn hơn cả 10 và 20, khiến code thực thi khối `else`.