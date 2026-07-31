# Deque

> Nhóm: Collections

## Mục tiêu

- Hiểu double-ended queue.
- Biết thêm/xóa hai đầu.
- Dùng Deque thay Stack legacy.

## Lý thuyết dễ hiểu

Deque cho phép thêm/xóa ở cả đầu và cuối. Nó có thể dùng như queue hoặc stack.

## Facts cần nhớ

- Deque đọc là deck.
- ArrayDeque thường tốt cho stack/queue đơn luồng.
- `Stack` class cũ thường không được khuyến nghị cho code mới.

## Code mẫu

```java
import java.util.ArrayDeque;
import java.util.Deque;

public class DequeDemo {
    public static void main(String[] arguments) {
        Deque<String> browserHistory = new ArrayDeque<>();
        browserHistory.push("home");
        browserHistory.push("courses");
        browserHistory.push("java");

        System.out.println("Current: " + browserHistory.pop());
        System.out.println("Back to: " + browserHistory.peek());
    }
}
```

## Cách triển khai thực tế

- Dùng Deque cho undo/backtracking.
- Dùng `addFirst`, `addLast`, `removeFirst`, `removeLast` khi cần rõ.
- Không cho null vào ArrayDeque.

## Lỗi hay gặp

- Nhầm push/pop đầu nào.
- Dùng Stack legacy.
- Không kiểm tra rỗng trước remove/pop.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
