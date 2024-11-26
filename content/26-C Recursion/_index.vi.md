+++
title = " C Recursion" 
weight = 26
chapter = false
pre = " <b> 26. </b> "
+++

#### C Recursion

#### Recursion là gì

Recursion là kỹ thuật cho phép một hàm tự gọi chính nó. Kỹ thuật này cung cấp cách giải quyết các bài toán phức tạp bằng cách chia nhỏ thành các bài toán đơn giản hơn.

Recursion có thể hơi khó hiểu lúc đầu. Cách tốt nhất để hiểu cách nó hoạt động là thông qua thực hành.

#### Ví dụ về Recursion 

Việc cộng hai số là đơn giản, nhưng cộng một dãy số thì phức tạp hơn. Trong ví dụ sau, recursion được sử dụng để cộng một dãy số bằng cách chia nhỏ thành các phép cộng hai số đơn giản:

#### Ví dụ

```c
int sum(int k);

int main() {
    int result = sum(10);
    printf("%d", result);
    return 0;
}

int sum(int k) {
    if (k > 0) {
        return k + sum(k - 1);
    } else {
        return 0;
    }
}
```

#### Giải thích ví dụ

Khi hàm `sum()` được gọi, nó cộng tham số `k` với tổng của tất cả các số nhỏ hơn `k` và trả về kết quả. Khi `k` bằng 0, hàm sẽ trả về 0. Khi chạy, chương trình thực hiện theo các bước sau:

```text
10 + sum(9)
10 + ( 9 + sum(8) )
10 + ( 9 + ( 8 + sum(7) ) )
...
10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1 + sum(0)
10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1 + 0
```

Do hàm không tự gọi lại khi `k` bằng 0, chương trình dừng tại đó và trả về kết quả.

Lập trình viên cần rất cẩn thận khi sử dụng recursion vì rất dễ vô tình tạo ra hàm chạy vô hạn, hoặc sử dụng quá nhiều bộ nhớ hay tài nguyên xử lý. Tuy nhiên, khi được viết đúng cách, recursion có thể là một phương pháp lập trình hiệu quả và khéo léo về mặt toán học.