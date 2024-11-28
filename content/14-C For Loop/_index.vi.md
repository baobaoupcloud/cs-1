+++
title = "Vòng lặp For trong C"
weight = 14
chapter = false
pre = " <b> 14. </b> "
+++

#### Vòng lặp For trong C

Khi bạn cần lặp một khối code với số lần cụ thể, vòng lặp `for` thường phù hợp hơn vòng lặp `while`.

#### Cú pháp

```c
for (biểu thức 1; biểu thức 2; biểu thức 3) {
    // khối lệnh cần thực thi
}
```

Ba biểu thức trong vòng lặp `for` có các mục đích khác nhau:

* **Biểu thức 1**: Khởi tạo biến lặp và chỉ thực thi một lần trước khi vòng lặp bắt đầu
* **Biểu thức 2**: Xác định điều kiện để thực thi khối lệnh - vòng lặp tiếp tục khi điều kiện đúng
* **Biểu thức 3**: Thực thi sau mỗi lần lặp, thường dùng để cập nhật biến lặp

#### Ví dụ

Dưới đây là ví dụ đơn giản in các số từ 0 đến 4:

```c
int i;

for (i = 0; i < 5; i++) {
    printf("%d\n", i); 
}
```

#### Cách hoạt động

Hãy phân tích ví dụ trên:

1. `i = 0`: Khởi tạo biến đếm bằng 0
2. `i < 5`: Vòng lặp tiếp tục chừng nào i nhỏ hơn 5
3. `i++`: Tăng i lên 1 đơn vị sau mỗi lần lặp

Kết quả sẽ là:
```
0
1  
2
3
4
```

Vòng lặp này sẽ thực thi đúng 5 lần, với `i` nhận các giá trị từ 0 đến 4. Khi `i` đạt giá trị 5, điều kiện `i < 5` trở thành sai và vòng lặp kết thúc.

#### Vòng lặp lồng nhau trong C

Trong lập trình C, bạn có thể đặt một vòng lặp bên trong vòng lặp khác, tạo thành **vòng lặp lồng nhau**.

Khi sử dụng vòng lặp lồng nhau, vòng lặp bên trong sẽ hoàn thành tất cả các lần lặp của nó cho *mỗi lần lặp* của vòng lặp bên ngoài.

#### Ví dụ

```c
int i, j;

// Vòng lặp ngoài
for (i = 1; i <= 2; ++i) {
    printf("Ngoài: %d\n", i);  // Thực thi 2 lần
    
    // Vòng lặp trong
    for (j = 1; j <= 3; ++j) {
        printf(" Trong: %d\n", j);  // Thực thi 6 lần (2 * 3)
    }
}
```

#### Kết quả:
```
Ngoài: 1
 Trong: 1
 Trong: 2
 Trong: 3
Ngoài: 2
 Trong: 1
 Trong: 2
 Trong: 3
```

#### Quy trình thực thi:
1. Vòng lặp ngoài chạy 2 lần (i = 1, 2)
2. Với *mỗi* lần lặp của vòng ngoài:
   - Vòng lặp trong chạy 3 lần (j = 1, 2, 3)  
3. Tổng số lần lặp của vòng trong: 2 × 3 = 6 lần