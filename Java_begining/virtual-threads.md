# Virtual Threads

> Nhóm: Concurrency

## Mục tiêu

- Hiểu virtual thread nhẹ hơn platform thread.
- Biết phù hợp I/O blocking nhiều.
- Biết giới hạn với CPU-bound và synchronized pinning.

## Lý thuyết dễ hiểu

Virtual thread là thread nhẹ do JVM quản lý, giúp server xử lý nhiều tác vụ blocking I/O với mô hình code tuần tự dễ đọc.

Nó không làm CPU nhanh hơn. Với tác vụ CPU-bound, số core vẫn là giới hạn chính. Với I/O-bound, virtual thread giúp giảm chi phí chờ.

## Facts cần nhớ

- Virtual threads finalized trong Java 21.
- Mỗi request/task blocking có thể dùng một virtual thread.
- Không dùng pooling virtual threads như platform threads.

## Code mẫu

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class VirtualThreadDemo {
    public static void main(String[] arguments) {
        try (ExecutorService executorService = Executors.newVirtualThreadPerTaskExecutor()) {
            for (int taskNumber = 1; taskNumber <= 5; taskNumber++) {
                int currentTaskNumber = taskNumber;
                executorService.submit(() -> {
                    System.out.println("Running task " + currentTaskNumber
                            + " on " + Thread.currentThread());
                });
            }
        }
    }
}
```

## Cách triển khai thực tế

- Phù hợp HTTP calls, database calls, file I/O blocking.
- Vẫn đặt timeout và giới hạn tài nguyên như database connection pool.
- Kiểm tra framework/library đã hỗ trợ tốt chưa.

## Lỗi hay gặp

- Dùng virtual thread để chạy CPU-heavy vô hạn.
- Tạo pool virtual thread cố định.
- Giữ synchronized block lâu quanh I/O.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
