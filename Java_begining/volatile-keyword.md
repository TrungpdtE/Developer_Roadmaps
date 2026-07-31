# volatile keyword

> Nhóm: Concurrency

## Mục tiêu

- Hiểu visibility trong đa luồng.
- Biết volatile không thay thế lock cho thao tác phức tạp.
- Dùng volatile cho flag đơn giản.

## Lý thuyết dễ hiểu

Trong đa luồng, một thread có thể không thấy ngay thay đổi từ thread khác do cache/tối ưu. `volatile` tạo guarantee visibility cho biến.

Nó phù hợp cho flag dừng. Nếu cần tăng counter an toàn, dùng `AtomicInteger` hoặc lock.

## Facts cần nhớ

- `volatile` đảm bảo thread đọc thấy giá trị mới hơn.
- `count++` vẫn không atomic dù count volatile.
- Volatile có quan hệ với Java Memory Model.

## Code mẫu

```java
public class VolatileDemo {
    private volatile boolean running = true;

    public void stop() {
        running = false;
    }

    public void runLoop() {
        while (running) {
            System.out.println("Working");
        }
        System.out.println("Stopped");
    }
}
```

## Cách triển khai thực tế

- Dùng volatile cho trạng thái đơn giản một biến.
- Dùng atomic/lock cho read-modify-write.
- Đừng tự viết concurrency phức tạp nếu thư viện đã có.

## Lỗi hay gặp

- Dùng volatile cho `counter++`.
- Nghĩ volatile làm object bên trong thread-safe.
- Không hiểu visibility khác atomicity.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
