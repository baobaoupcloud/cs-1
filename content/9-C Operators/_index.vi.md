+++
title = "Toán tử trong C"
weight = 9
chapter = false
pre = " <b> 9. </b> "
+++

#### Toán tử trong lập trình C

Toán tử được sử dụng để thực hiện các phép tính trên biến và giá trị.

#### Cách sử dụng cơ bản

Trong C, toán tử có thể được dùng để thực hiện tính toán với giá trị và biến:

```c
int myNum = 100 + 50;    // Phép cộng cơ bản với giá trị

// Phép tính với biến và giá trị 
int sum1 = 100 + 50;     // 150 (100 + 50)
int sum2 = sum1 + 250;   // 400 (150 + 250)
int sum3 = sum2 + sum2;  // 800 (400 + 400)
```

#### Các loại toán tử trong C

C cung cấp một số loại toán tử sau:

1. Toán tử số học
2. Toán tử gán
3. Toán tử so sánh
4. Toán tử logic
5. Toán tử thao tác bit

#### Toán tử số học

Các toán tử này thực hiện các phép tính toán thông dụng:

| Toán tử | Tên | Mô tả | Ví dụ |
|----------|------|-------------|----------|
| + | Cộng | Cộng hai giá trị | x + y |
| - | Trừ | Trừ các giá trị | x - y |
| * | Nhân | Nhân các giá trị | x * y |
| / | Chia | Chia các giá trị | x / y |
| % | Chia lấy dư | Trả về số dư | x % y |
| ++ | Tăng | Tăng thêm 1 | ++x |
| -- | Giảm | Giảm đi 1 | --x |

#### Toán tử gán

Toán tử gán dùng để gán giá trị cho biến:

```c
int x = 10;     // Phép gán cơ bản
x += 5;         // Phép gán cộng (tương đương x = x + 5)
```

Danh sách đầy đủ các toán tử gán:

| Toán tử | Ví dụ | Tương đương |
|----------|----------|------------|
| = | x = 5 | x = 5 |
| += | x += 3 | x = x + 3 |
| -= | x -= 3 | x = x - 3 |
| *= | x *= 3 | x = x * 3 |
| /= | x /= 3 | x = x / 3 |
| %= | x %= 3 | x = x % 3 |
| &= | x &= 3 | x = x & 3 |
| \|= | x \|= 3 | x = x \| 3 |
| ^= | x ^= 3 | x = x ^ 3 |
| >>= | x >>= 3 | x = x >> 3 |
| <<= | x <<= 3 | x = x << 3 |

#### Toán tử so sánh

Toán tử so sánh trả về giá trị boolean (1 là đúng, 0 là sai):

```c
int x = 5;
int y = 3;
printf("%d", x > y);    // Trả về 1 (đúng) vì 5 > 3
```

Danh sách toán tử so sánh:

| Toán tử | Tên | Ví dụ | Mô tả |
|----------|------|---------|-------------|
| == | Bằng | x == y | Trả về 1 nếu các giá trị bằng nhau |
| != | Khác | x != y | Trả về 1 nếu các giá trị khác nhau |
| > | Lớn hơn | x > y | Trả về 1 nếu x lớn hơn y |
| < | Nhỏ hơn | x < y | Trả về 1 nếu x nhỏ hơn y |
| >= | Lớn hơn hoặc bằng | x >= y | Trả về 1 nếu x lớn hơn hoặc bằng y |
| <= | Nhỏ hơn hoặc bằng | x <= y | Trả về 1 nếu x nhỏ hơn hoặc bằng y |

#### Toán tử logic

Toán tử logic kết hợp nhiều điều kiện:

| Toán tử | Tên | Ví dụ | Mô tả |
|----------|------|---------|-------------|
| && | AND | x < 5 && x < 10 | Trả về 1 nếu cả hai điều kiện đều đúng |
| \|\| | OR | x < 5 \|\| x < 4 | Trả về 1 nếu ít nhất một điều kiện đúng |
| ! | NOT | !(x < 5) | Trả về 1 nếu điều kiện sai |