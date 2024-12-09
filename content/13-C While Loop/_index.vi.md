+++
title = "Vòng lặp While trong C" 
weight = 13
chapter = false
pre = " <b> 13. </b> "
+++

#### Vòng lặp While trong C

Loops (vòng lặp) có thể thực thi một khối lệnh cho đến khi một điều kiện cụ thể được thỏa mãn. Chúng rất hữu ích vì:
- Tiết kiệm thời gian
- Giảm thiểu lỗi
- Làm cho code dễ đọc hơn

#### Vòng lặp While

Vòng lặp while thực thi một khối lệnh lặp đi lặp lại miễn là điều kiện được chỉ định còn đúng.

#### Cú pháp
```c
while (condition) {
    // khối lệnh cần thực thi
}
```

#### Ví dụ
Trong ví dụ này, code trong vòng lặp sẽ chạy lặp đi lặp lại miễn là biến `i` nhỏ hơn 5:

```c
int i = 0;

while (i < 5) {
    printf("%d\n", i);
    i++;
}
```

> **Lưu ý:** Đừng quên tăng giá trị của biến được sử dụng trong điều kiện (`i++`), nếu không vòng lặp sẽ không bao giờ kết thúc!

Kết quả của đoạn code trên sẽ là:
```
0
1
2
3 
4
```

Trong ví dụ này:
1. Chúng ta khởi tạo `i` bằng 0
2. Vòng lặp while kiểm tra nếu `i` nhỏ hơn 5
3. Nếu đúng, nó in ra giá trị của `i`
4. Sau đó tăng `i` lên 1
5. Quá trình này lặp lại cho đến khi `i` đạt giá trị 5, lúc này điều kiện trở thành sai và vòng lặp kết thúc

#### Vòng lặp Do/While

Vòng lặp do/while là một biến thể của vòng lặp while. Vòng lặp này sẽ thực thi khối lệnh một lần trước khi kiểm tra điều kiện, sau đó nó sẽ lặp lại miễn là điều kiện còn đúng.

#### Cú pháp

```c
do {
  // khối lệnh cần thực thi
} while (condition);
```

Ví dụ dưới đây sử dụng vòng lặp do/while. Vòng lặp sẽ luôn được thực thi ít nhất một lần, kể cả khi điều kiện sai, vì khối lệnh được thực thi trước khi điều kiện được kiểm tra:

#### Ví dụ

```c
int i = 0;

do {
    printf("%d\n", i);
    i++;
} while (i < 5);
```

Kết quả sẽ là:
```
0
1
2
3
4
```
