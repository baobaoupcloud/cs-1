+++
title = "Memory Address trong lập trình C" 
weight = 20
chapter = false
pre = " <b> 20. </b> "
+++

#### Memory Address trong lập trình C

Khi một biến được tạo ra trong C, một địa chỉ bộ nhớ sẽ được gán cho biến đó. Địa chỉ bộ nhớ này đại diện cho vị trí nơi biến được lưu trữ trên máy tính.

Khi ta gán một giá trị cho biến, giá trị đó sẽ được lưu trữ tại địa chỉ bộ nhớ này.

Để truy cập địa chỉ bộ nhớ, ta sử dụng toán tử tham chiếu (`&`). Điều này sẽ cho biết biến được lưu trữ ở đâu:

#### Ví dụ

```c
int myAge = 43;
printf("%p", &myAge); // Kết quả: 0x7ffe5367e044
```

**Lưu ý:**
- Địa chỉ bộ nhớ được hiển thị dưới dạng số thập lục phân (0x..)
- Bạn có thể nhận được kết quả khác trong chương trình của mình vì vị trí bộ nhớ phụ thuộc vào máy tính của bạn 
- Biểu thức `&myAge` thường được gọi là "con trỏ" - nó lưu trữ địa chỉ bộ nhớ của một biến như là giá trị của nó
- Để in các giá trị con trỏ, chúng ta sử dụng định dạng `%p`

#### Tầm quan trọng của Memory Address

Memory address và con trỏ đóng vai trò then chốt trong lập trình C vì nhiều lý do:

1. Chúng cho phép thao tác trực tiếp với dữ liệu trong bộ nhớ máy tính
2. Chúng có thể giúp giảm độ phức tạp của mã nguồn
3. Chúng có thể cải thiện hiệu suất chương trình
4. Chúng tạo nên sự khác biệt của C so với các ngôn ngữ lập trình khác như Python và Java

Chức năng con trỏ này là một trong những tính năng mạnh mẽ nhất của C, và bạn sẽ tìm hiểu sâu hơn về nó khi học về con trỏ chi tiết.