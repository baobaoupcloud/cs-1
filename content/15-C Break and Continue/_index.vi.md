+++
title = "Câu lệnh Break và Continue trong C" 
weight = 15
chapter = false
pre = " <b> 15. </b> "
+++

#### Câu lệnh Break và Continue trong C

#### Câu lệnh Break

Câu lệnh `break` cho phép bạn thoát hoặc "nhảy ra khỏi" một vòng lặp ngay lập tức. Nó thường được sử dụng trong cả vòng lặp và câu lệnh switch.

#### Ví dụ Break trong vòng lặp For

```c
int i;

for (i = 0; i < 10; i++) {
    if (i == 4) {
        break;
    }
    printf("%d\n", i);
}
```

Đoạn mã trên sẽ in các số từ 0 đến 3, sau đó dừng lại khi i bằng 4.

#### Câu lệnh Continue 

Câu lệnh `continue` bỏ qua phần còn lại của lần lặp hiện tại và chuyển sang lần lặp tiếp theo. Khác với `break`, nó không thoát khỏi vòng lặp hoàn toàn.

#### Ví dụ Continue trong vòng lặp For

```c
int i;

for (i = 0; i < 10; i++) {
    if (i == 4) {
        continue;
    }
    printf("%d\n", i);
}
```

Đoạn mã trên sẽ in tất cả các số từ 0 đến 9, ngoại trừ số 4.

#### Sử dụng Break và Continue trong vòng lặp While

#### Break trong vòng lặp While

```c
int i = 0;

while (i < 10) {
    if (i == 4) {
        break;
    }
    printf("%d\n", i);
    i++;
}
```

#### Continue trong vòng lặp While

```c
int i = 0;

while (i < 10) {
    if (i == 4) {
        i++;
        continue;
    }
    printf("%d\n", i);
    i++;
}
```

Những khác biệt chính giữa `break` và `continue`:
- `break` kết thúc toàn bộ vòng lặp
- `continue` chỉ bỏ qua lần lặp hiện tại
- Với `continue` trong vòng lặp while, cần nhớ cập nhật bộ đếm trước câu lệnh continue để tránh vòng lặp vô hạn