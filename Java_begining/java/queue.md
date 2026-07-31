# Queue

> Nhóm: Collections

## Mục tiêu

- Hiểu FIFO.
- Biết `offer`, `poll`, `peek`.
- Ứng dụng hàng đợi xử lý task.

## Lý thuyết dễ hiểu

Queue phù hợp khi xử lý theo thứ tự đến: in tài liệu, task background, BFS trong thuật toán.

## Facts cần nhớ

- Queue thường vào trước ra trước.
- `poll` trả null nếu rỗng, `remove` throw exception.
- PriorityQueue lấy theo độ ưu tiên, không phải FIFO thuần.

## Code mẫu

```java
import java.util.ArrayDeque;
import java.util.Queue;

public class QueueDemo {
    public static void main(String[] arguments) {
        Queue<String> tasks = new ArrayDeque<>();
        tasks.offer("send email");
        tasks.offer("generate invoice");

        while (!tasks.isEmpty()) {
            String task = tasks.poll();
            System.out.println("Processing " + task);
        }
    }
}
```

## Cách triển khai thực tế

- Dùng ArrayDeque cho queue đơn luồng.
- Dùng BlockingQueue cho producer-consumer đa luồng.
- Chọn PriorityQueue khi cần priority.

## Lỗi hay gặp

- Dùng LinkedList làm queue khi ArrayDeque đủ tốt.
- Không xử lý queue rỗng.
- Nhầm PriorityQueue với sorted list hoàn toàn.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
