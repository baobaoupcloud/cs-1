+++
title = "Switch Statement trong C" 
weight = 27
chapter = false
pre = " <b> 27s. </b> "
+++

#### Các Hàm Toán Học Trong C

Khi làm việc với các phép toán trong C, bạn có thể sử dụng nhiều hàm toán học có sẵn. Các hàm này cung cấp những phép tính phổ biến như căn bậc hai, làm tròn và tính lũy thừa.

#### Thêm Thư Viện Math

Trước khi sử dụng bất kỳ hàm toán học nào, bạn cần khai báo thư viện math:

```c
#include <math.h>
```

#### Các Hàm Toán Học Thường Dùng

#### Căn Bậc Hai - sqrt()
Hàm `sqrt()` tính căn bậc hai của một số:

```c
printf("%f", sqrt(16));  // Kết quả: 4.000000
```

#### Các Hàm Làm Tròn
C cung cấp hai hàm làm tròn chính:

#### ceil() - Làm Tròn Lên
Hàm `ceil()` làm tròn một số lên đến số nguyên gần nhất:

```c
printf("%f", ceil(1.4));  // Kết quả: 2.000000
```

#### floor() - Làm Tròn Xuống
Hàm `floor()` làm tròn một số xuống đến số nguyên gần nhất:

```c
printf("%f", floor(1.4));  // Kết quả: 1.000000
```

#### Lũy Thừa - pow()
Hàm `pow()` tính giá trị của x mũ y (xʸ):

```c
printf("%f", pow(4, 3));  // Kết quả: 64.000000  (4³ = 4 * 4 * 4)
```

Lưu ý khi sử dụng các hàm toán học này:
- Giá trị trả về thường ở dạng số thực dấu phẩy động độ chính xác kép (double)
- Bạn có thể cần liên kết với thư viện math khi biên dịch (sử dụng cờ `-lm`)
- Luôn kiểm tra lỗi miền giá trị khi sử dụng các hàm như `sqrt()` với số âm