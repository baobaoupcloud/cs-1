+++
title = "Kiểu dữ liệu Boolean" 
weight = 10
chapter = false
pre = " <b> 10. </b> "
+++

#### Kiểu dữ liệu Boolean trong C

Trong lập trình, bạn thường cần một kiểu dữ liệu chỉ có thể nhận một trong hai giá trị:
- YES / NO
- ON / OFF 
- TRUE / FALSE

C cung cấp kiểu dữ liệu `bool` (boolean) để biểu diễn các giá trị hoặc là true hoặc false.

#### Khai báo biến Boolean

Khác với `int` hay `char`, kiểu `bool` không được tích hợp sẵn trong C. Nó được giới thiệu trong C99 và yêu cầu phải import:

```c
#include <stdbool.h>
```

Khai báo biến boolean sử dụng từ khóa `bool`:

```c
bool isProgrammingFun = true;
bool isFishTasty = false;
```

#### In giá trị Boolean

Boolean được biểu diễn nội bộ dưới dạng số nguyên:
- 1 (hoặc bất kỳ số khác 0) biểu thị cho `true`
- 0 biểu thị cho `false`

Sử dụng định dạng `%d` để in giá trị boolean:

```c
// Tạo biến boolean
bool isProgrammingFun = true;
bool isFishTasty = false;

// In giá trị boolean
printf("%d", isProgrammingFun);   // Trả về 1 (true)
printf("%d", isFishTasty);        // Trả về 0 (false)
```

#### So sánh giá trị và biến

Giá trị boolean thường là kết quả của việc so sánh giữa các giá trị và biến. Những phép so sánh này giúp đưa ra quyết định trong chương trình.

Sử dụng toán tử so sánh:

```c
// So sánh giá trị
printf("%d", 10 > 9);  // Trả về 1 (true)

// So sánh biến
int x = 10;
int y = 9;
printf("%d", x > y);   // Trả về 1 (true)
```

Sử dụng toán tử bằng (`==`):

```c
printf("%d", 10 == 10); // Trả về 1 (true)
printf("%d", 10 == 15); // Trả về 0 (false)
printf("%d", 5 == 55);  // Trả về 0 (false)
```

Bạn cũng có thể so sánh các biến boolean:

```c
bool isHamburgerTasty = true;
bool isPizzaTasty = true;

// So sánh giá trị boolean
printf("%d", isHamburgerTasty == isPizzaTasty); // Trả về 1 (true)
```

**Quan trọng:** Luôn nhớ include file header `<stdbool.h>` khi làm việc với biến boolean.