# Threads

> Nhóm: Concurrency

## Mục tiêu

- Hiểu thread là luồng thực thi.
- Biết tạo task bằng `Runnable`/`Callable`.
- Biết dùng executor thay vì tạo thread thủ công nhiều.

## Lý thuyết dễ hiểu

Thread cho phép nhiều việc chạy đồng thời. Trong Java hiện đại, bạn thường submit task vào executor thay vì tự tạo thread ở mọi nơi.

## Facts cần nhớ

- Thread có chi phí tạo và stack.
- `ExecutorService` quản lý chạy task tốt hơn `new Thread` rải rác.
- Shared mutable state cần đồng bộ.

## Code mẫu

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;
import java.util.concurrent.Future;

public class ThreadsDemo {
    public static void main(String[] arguments) throws Exception {
        ExecutorService executorService = Executors.newFixedThreadPool(2);
        try {
            Future<Integer> future = executorService.submit(() -> {
                int total = 0;
                for (int number = 1; number <= 100; number++) {
                    total = total + number;
                }
                return total;
            });

            System.out.println(future.get());
        } finally {
            executorService.shutdown();
        }
    }
}
```

## Cách triển khai thực tế

- Dùng executor cho background jobs.
- Dùng concurrent collections khi cần shared collection.
- Đặt tên thread trong production để log dễ đọc.

## Lỗi hay gặp

- Tạo thread không giới hạn.
- Quên shutdown executor.
- Dùng shared list thường từ nhiều thread.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
