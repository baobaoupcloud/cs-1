+++
title = "Nhập Dữ Liệu Từ Người Dùng Trong Lập Trình C" 
weight = 19
chapter = false
pre = " <b> 19. </b> "
+++

#### Nhập Dữ Liệu Từ Người Dùng Trong Lập Trình C

#### Sử dụng `printf()` và `scanf()`

Bạn đã biết rằng `printf()` được dùng để xuất dữ liệu. Để nhập dữ liệu từ người dùng, C cung cấp hàm `scanf()`.

#### Ví dụ Cơ Bản Về Nhập Dữ Liệu
Dưới đây là cách nhận và xuất một số từ người dùng nhập vào:

```c
// Tạo biến integer để lưu số người dùng nhập
int myNum;

// Yêu cầu người dùng nhập số
printf("Hãy nhập một số: \n");

// Nhận và lưu số đó
scanf("%d", &myNum);

// Xuất số ra màn hình
printf("Số bạn đã nhập là: %d", myNum);
```

**Lưu ý Quan Trọng:** Hàm `scanf()` yêu cầu hai tham số:
1. Format specifier (ví dụ: `%d` cho số nguyên)
2. Toán tử tham chiếu (`&myNum`) cho địa chỉ bộ nhớ của biến

#### Nhập Nhiều Giá Trị

Bạn có thể nhập nhiều giá trị trong một lệnh `scanf()`:

```c
// Khai báo biến
int myNum;
char myChar;

// Yêu cầu người dùng nhập
printf("Hãy nhập một số VÀ một ký tự rồi nhấn enter: \n");

// Nhận cả hai giá trị
scanf("%d %c", &myNum, &myChar);

// Hiển thị kết quả
printf("Số bạn đã nhập là: %d\n", myNum);
printf("Ký tự bạn đã nhập là: %c\n", myChar);
```

#### Nhập Chuỗi

#### Nhập Chuỗi Cơ Bản với `scanf()`

```c
// Tạo một chuỗi (mảng ký tự)
char firstName[30];

// Yêu cầu nhập
printf("Nhập tên của bạn: \n");

// Nhận chuỗi đầu vào
scanf("%s", firstName);

// Hiển thị kết quả
printf("Xin chào %s", firstName);
```

**Lưu ý:** Khi sử dụng `scanf()` với chuỗi:
- Bạn phải chỉ định kích thước mảng
- Không cần toán tử tham chiếu (`&`)
- Nó chỉ nhận đầu vào đến khoảng trắng đầu tiên

#### Hạn Chế của `scanf()` với Chuỗi

Ví dụ này cho thấy hạn chế của `scanf()` với chuỗi nhiều từ:

```c
char fullName[30];

printf("Nhập họ tên đầy đủ của bạn: \n");
scanf("%s", &fullName);

printf("Xin chào %s", fullName);

// Nếu nhập: Nguyen Van A
// Kết quả sẽ là: Xin chào Nguyen
```

#### Sử Dụng `fgets()` để Nhập Chuỗi Tốt Hơn

Để nhận toàn bộ dòng văn bản, bao gồm cả khoảng trắng, hãy dùng `fgets()`:

```c
char fullName[30];

printf("Nhập họ tên đầy đủ của bạn: \n");
fgets(fullName, sizeof(fullName), stdin);

printf("Xin chào %s", fullName);

// Nếu nhập: Nguyen Van A
// Kết quả sẽ là: Xin chào Nguyen Van A
```

**Lưu ý:** Khi sử dụng `fgets()`, cần nhớ bao gồm:
- Tên biến chuỗi
- Kích thước chuỗi (`sizeof(tên_chuỗi)`)
- Standard input (`stdin`)