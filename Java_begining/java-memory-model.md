# Java Memory Model

> Nhóm: Concurrency

## Mục tiêu

- Hiểu JMM quy định visibility và ordering.
- Biết happens-before.
- Biết synchronized/volatile/final tạo guarantee.

## Lý thuyết dễ hiểu

Java Memory Model định nghĩa khi nào thay đổi từ một thread được thread khác nhìn thấy và thứ tự thao tác có thể được quan sát.

`happens-before` là quan hệ quan trọng: nếu A happens-before B, thì B phải thấy kết quả của A. Ví dụ unlock trên monitor happens-before lock tiếp theo trên cùng monitor.

## Facts cần nhớ

- JMM không phải layout heap chi tiết.
- Data race làm hành vi khó dự đoán.
- Final field có guarantee đặc biệt sau constructor đúng.

## Code mẫu

```java
public class SynchronizedCounter {
    private int value = 0;

    public synchronized void increment() {
        value = value + 1;
    }

    public synchronized int getValue() {
        return value;
    }
}
```

## Cách triển khai thực tế

- Dùng `java.util.concurrent` thay vì tự quản lý low-level.
- Immutable object giúp tránh data race.
- Synchronized vừa mutual exclusion vừa visibility.

## Lỗi hay gặp

- Dựa vào test chạy đúng để kết luận thread-safe.
- Publish object khi constructor chưa xong.
- Dùng shared mutable state không bảo vệ.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
