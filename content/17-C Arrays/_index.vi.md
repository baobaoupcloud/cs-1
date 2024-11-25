+++
title = "Mảng trong Lập trình C"
weight = 17 
chapter = false
pre = " <b> 17. </b> "
+++ 

#### Mảng trong Lập trình C

Mảng (array) cho phép bạn lưu trữ nhiều giá trị trong một biến duy nhất, thay vì phải tạo nhiều biến riêng lẻ cho từng giá trị.

#### Tạo Mảng

Để tạo một mảng trong C:
1. Định nghĩa kiểu dữ liệu (ví dụ: `int`)  
2. Chỉ định tên mảng và dấu ngoặc vuông `[]`
3. Khởi tạo giá trị sử dụng danh sách các phần tử ngăn cách bởi dấu phẩy trong dấu ngoặc nhọn

```c
int myNumbers[] = {25, 50, 75, 100};
```

Đoạn code trên tạo ra một biến chứa mảng gồm 4 số nguyên.

#### Truy cập Phần tử Mảng

Các phần tử mảng được truy cập thông qua chỉ số, bắt đầu từ 0:
- `[0]` là phần tử đầu tiên  
- `[1]` là phần tử thứ hai
- Và tiếp tục...

```c
int myNumbers[] = {25, 50, 75, 100};
printf("%d", myNumbers[0]);  // In ra 25
```

#### Thay đổi Giá trị Phần tử Mảng

Để thay đổi giá trị của một phần tử cụ thể, tham chiếu đến chỉ số của nó:

```c
int myNumbers[] = {25, 50, 75, 100};
myNumbers[0] = 33;
printf("%d", myNumbers[0]);  // Bây giờ sẽ in ra 33 thay vì 25
```

#### Duyệt qua Các Phần tử Mảng

Sử dụng vòng lặp `for` để duyệt qua các phần tử mảng:

```c 
int myNumbers[] = {25, 50, 75, 100};
int i;

for (i = 0; i < 4; i++) {
    printf("%d\n", myNumbers[i]);
}
```

#### Chỉ định Kích thước Mảng

Bạn có thể khai báo mảng với kích thước cố định và thêm phần tử sau:

```c
// Khai báo mảng 4 số nguyên
int myNumbers[4];

// Thêm phần tử
myNumbers[0] = 25;
myNumbers[1] = 50; 
myNumbers[2] = 75;
myNumbers[3] = 100;
```

**Lưu ý quan trọng:**
- Kích thước mảng không thể thay đổi sau khi đã tạo
- Bạn phải biết trước số lượng phần tử để cấp phát bộ nhớ phù hợp

#### Tính nhất quán của Kiểu dữ liệu

Tất cả phần tử trong mảng phải cùng kiểu dữ liệu. Trộn lẫn các kiểu khác nhau có thể gây ra lỗi hoặc hành vi không mong muốn:

```c
// Sử dụng sai - trộn lẫn số nguyên và số thực
int myArray[] = {25, 50, 75, 3.15, 5.99};  // 3.15 và 5.99 sẽ bị cắt thành 3 và 5
```

Sự không nhất quán này có thể dẫn đến:
- Mất mát dữ liệu
- Lỗi biên dịch
- Hành vi không mong muốn

Luôn đảm bảo tất cả phần tử mảng có cùng kiểu dữ liệu để chương trình chạy đúng.

#### Lấy Kích thước hoặc Độ dài Mảng trong C 

Để lấy kích thước của mảng, bạn có thể sử dụng toán tử `sizeof`:

#### Ví dụ Cơ bản về Kích thước

```c
int myNumbers[] = {10, 25, 50, 75, 100}; 
printf("%lu", sizeof(myNumbers)); // In ra 20
```

#### Hiểu về Kết quả

Bạn có thể thắc mắc tại sao kết quả là 20 thay vì 5, khi mảng chứa 5 phần tử?

Điều này xảy ra vì toán tử `sizeof` trả về kích thước theo byte của một kiểu. Do kiểu `int` thường chiếm 4 byte, phép tính sẽ là:
- 4 byte × 5 phần tử = 20 byte

Hiểu về kích thước bộ nhớ của mảng rất có giá trị khi làm việc với các chương trình lớn cần quản lý bộ nhớ hiệu quả.

#### Lấy Độ dài Mảng

Để tìm số lượng phần tử trong mảng, sử dụng công thức sau:

```c
int myNumbers[] = {10, 25, 50, 75, 100};
int length = sizeof(myNumbers) / sizeof(myNumbers[0]);

printf("%d", length);  // In ra 5 
```

#### Cải thiện Vòng lặp Mảng

#### Cách Truyền thống (Ít Linh hoạt)

```c
int myNumbers[] = {25, 50, 75, 100};
int i;

for (i = 0; i < 4; i++) {
    printf("%d\n", myNumbers[i]);  
}
```

#### Cách Tốt hơn (Kích thước Động)

```c
int myNumbers[] = {25, 50, 75, 100};
int length = sizeof(myNumbers) / sizeof(myNumbers[0]);
int i;

for (i = 0; i < length; i++) {
    printf("%d\n", myNumbers[i]);
}
```

Phương pháp cải tiến này bền vững hơn vì nó hoạt động với mảng có kích thước bất kỳ, không cần phải cập nhật điều kiện vòng lặp thủ công khi kích thước mảng thay đổi.

#### Mảng Đa chiều trong C

Trong lập trình C, bạn có thể tạo mảng với nhiều chiều. Ngoài mảng một chiều quen thuộc, mảng đa chiều cho phép lưu trữ dữ liệu theo dạng bảng với hàng và cột.

#### Mảng Hai Chiều (2D)

Mảng 2D, còn gọi là ma trận, là một mảng các mảng. Đây là cách khai báo và khởi tạo mảng 2D:

```c
int matrix[2][3] = {
    {1, 4, 2},  // Hàng 0
    {3, 6, 8}   // Hàng 1
};
```

Số đầu tiên `[2]` biểu thị số hàng, số thứ hai `[3]` biểu thị số cột. Điều này tạo ra cấu trúc bảng:

```c
// Biểu diễn trực quan
1  4  2
3  6  8
```

#### Truy cập Phần tử

Để truy cập phần tử trong mảng 2D, chỉ định chỉ số hàng và cột:

```c
int matrix[2][3] = {{1, 4, 2}, {3, 6, 8}};
printf("%d", matrix[0][2]);  // In ra 2
```

Nhớ rằng chỉ số mảng bắt đầu từ 0, vì vậy:
- `matrix[0][0]` truy cập phần tử đầu tiên ở hàng đầu tiên
- `matrix[1][2]` truy cập phần tử thứ ba ở hàng thứ hai

#### Thay đổi Phần tử

Bạn có thể thay đổi giá trị bằng cách tham chiếu đến chỉ số:

```c
int matrix[2][3] = {{1, 4, 2}, {3, 6, 8}};
matrix[0][0] = 9;  // Thay đổi phần tử đầu tiên thành 9
```

#### Duyệt qua Mảng 2D

Để truy cập tất cả phần tử, sử dụng vòng lặp lồng nhau - một cho hàng và một cho cột:

```c
int matrix[2][3] = {{1, 4, 2}, {3, 6, 8}};

for (int i = 0; i < 2; i++) {
    for (int j = 0; j < 3; j++) {
        printf("%d ", matrix[i][j]);
    }
    printf("\n");  // Xuống dòng sau mỗi hàng
}
```

Code này sẽ in ra:
```
1 4 2
3 6 8
```

Lưu ý:
- Vòng lặp ngoài `i` duyệt qua các hàng
- Vòng lặp trong `j` duyệt qua các cột  
- Sử dụng giới hạn mảng phù hợp để tránh truy cập bộ nhớ không hợp lệ
- Mảng 2D được lưu trữ theo thứ tự row-major trong bộ nhớ