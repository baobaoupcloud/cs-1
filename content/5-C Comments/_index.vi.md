+++
title = "Comments trong C" 
weight = 5
chapter = false
pre = " <b> 5. </b> "
+++

#### Comments trong C {#comments-in-c}

#### Comments một dòng (Single-line Comments)

Comments một dòng bắt đầu bằng hai dấu gạch chéo (`//`).

Bất kỳ đoạn text nào nằm giữa `//` và cuối dòng sẽ được trình biên dịch bỏ qua (sẽ không được thực thi).

#### Ví dụ - Comment trước code

```c
// Đây là một comment
printf("Hello World!");
```

#### Ví dụ - Comment sau code 

```c
printf("Hello World!"); // Đây là một comment
```

#### Comments nhiều dòng (Multi-line Comments)

Comments nhiều dòng bắt đầu với `/*` và kết thúc với `*/`.

Bất kỳ đoạn text nào nằm giữa `/*` và `*/` sẽ được trình biên dịch bỏ qua:

#### Ví dụ

```c
/* Đoạn code dưới đây sẽ in ra dòng chữ Hello World!
lên màn hình, và nó thật tuyệt vời */
printf("Hello World!");
```

#### Nên dùng Comments một dòng hay nhiều dòng?

Bạn có thể tùy ý lựa chọn loại comments phù hợp. Thông thường:
- Sử dụng `//` cho các comments ngắn
- Sử dụng `/* */` cho các comments dài hơn

#### Lưu ý

Trước phiên bản C99 (phát hành năm 1999), bạn chỉ có thể sử dụng comments nhiều dòng trong C.