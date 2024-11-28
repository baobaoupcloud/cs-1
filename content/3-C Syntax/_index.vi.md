+++
title = "Cú pháp C" 
weight = 3
chapter = false
pre = " <b> 3. </b> "
+++

#### Tổng quan

Bạn đã từng thấy đoạn code sau đây vài lần trong các chương đầu tiên. Hãy cùng phân tích kỹ hơn để hiểu rõ từng phần:

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0003/0001.png?featherlight=false&width=90pc)

#### Ví dụ

```c
#include <stdio.h>

int main() {
    printf("Hello World!");
    return 0;
}
```

#### Giải thích ví dụ

**Dòng 1:** `#include <stdio.h>` là một **thư viện header file** cho phép chúng ta làm việc với các hàm input và output, như `printf()` (được sử dụng ở dòng 4). Header file bổ sung thêm các chức năng cho chương trình C.

*Đừng lo lắng nếu bạn chưa hiểu `#include <stdio.h>` hoạt động như thế nào. Hãy cứ xem nó như một thứ (gần như) luôn xuất hiện trong chương trình của bạn.*

**Dòng 2:** Một dòng trống. C bỏ qua khoảng trắng. Nhưng chúng ta sử dụng nó để code dễ đọc hơn.

**Dòng 3:** Một thứ khác luôn xuất hiện trong chương trình C là `main()`. Đây được gọi là **hàm**. Bất kỳ code nào bên trong cặp ngoặc nhọn `{}` của nó sẽ được thực thi.

**Dòng 4:** `printf()` là một **hàm** được sử dụng để xuất/in text ra màn hình. Trong ví dụ của chúng ta, nó sẽ xuất ra "Hello World!".

> Lưu ý: Mỗi câu lệnh C kết thúc bằng dấu chấm phẩy `;`

> Mẹo: Phần thân của `int main()` cũng có thể được viết như sau:
```c
int main(){printf("Hello World!");return 0;}
```
> Tuy nhiên, viết nhiều dòng sẽ giúp code dễ đọc hơn.

**Dòng 5:** `return 0` kết thúc hàm `main()`.

**Dòng 6:** Đừng quên thêm dấu ngoặc nhọn đóng `}` để thực sự kết thúc hàm main.

#### Giới thiệu về câu lệnh chương trình

Một chương trình máy tính bao gồm một chuỗi các chỉ thị cho máy tính biết những hành động cần thực hiện. Trong ngôn ngữ lập trình, những chỉ thị này được gọi là **câu lệnh** (statements).

#### Cấu trúc câu lệnh cơ bản

#### Ví dụ câu lệnh
```c
printf("Hello World!");
```

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0003/0002.png?featherlight=false&width=90pc)

#### Yêu cầu câu lệnh
- Mỗi câu lệnh phải kết thúc bằng dấu chấm phẩy (`;`)
- Quên dấu chấm phẩy sẽ dẫn đến lỗi biên dịch

#### Ví dụ về lỗi
```c
printf("Hello World!") // Lỗi: Thiếu dấu chấm phẩy
```

> Cảnh báo: *Kết quả biên dịch:* `error: expected ';' before 'return'`

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0003/0003.png?featherlight=false&width=90pc)

#### Nhiều câu lệnh

Các chương trình thường chứa nhiều câu lệnh được thực thi tuần tự.

#### Ví dụ về nhiều câu lệnh
```c
printf("Hello World!");
printf("Have a good day!");
return 0;
```

#### Thứ tự thực thi

Các câu lệnh được thực thi theo thứ tự từ trên xuống dưới:

1. Câu lệnh đầu tiên: Xuất ra "Hello World!"
2. Câu lệnh thứ hai: Xuất ra "Have a good day!"
3. Câu lệnh thứ ba: Trả về 0 để kết thúc chương trình thành công

#### Các nguyên tắc thực hành tốt

- Luôn kết thúc câu lệnh bằng dấu chấm phẩy
- Viết mỗi câu lệnh trên một dòng để dễ đọc hơn
- Sử dụng thụt lề đúng để duy trì cấu trúc code
- Thêm comments để giải thích các câu lệnh phức tạp

#### Tóm tắt

- Chương trình là danh sách các chỉ thị (câu lệnh)
- Câu lệnh phải kết thúc bằng dấu chấm phẩy
- Nhiều câu lệnh thực thi theo thứ tự tuần tự
- Cú pháp và định dạng đúng giúp cải thiện độ tin cậy của code