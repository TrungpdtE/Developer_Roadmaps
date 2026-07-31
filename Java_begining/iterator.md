# Iterator

> Nhóm: Collections

## Mục tiêu

- Hiểu iterator duyệt collection.
- Biết `hasNext`, `next`, `remove`.
- Biết tránh ConcurrentModificationException.

## Lý thuyết dễ hiểu

Iterator là object điều khiển quá trình duyệt. Nó hữu ích khi cần xóa phần tử trong lúc duyệt collection.

## Facts cần nhớ

- Enhanced for dùng iterator phía sau với nhiều collection.
- Iterator remove an toàn hơn remove trực tiếp khi đang duyệt.
- Fail-fast iterator không phải cơ chế đồng bộ thread-safe.

## Code mẫu

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class IteratorDemo {
    public static void main(String[] arguments) {
        List<String> names = new ArrayList<>(List.of("An", "", "Binh"));
        Iterator<String> iterator = names.iterator();

        while (iterator.hasNext()) {
            String name = iterator.next();
            if (name.isBlank()) {
                iterator.remove();
            }
        }

        System.out.println(names);
    }
}
```

## Cách triển khai thực tế

- Dùng iterator remove khi cần xóa trong loop.
- Dùng `removeIf` cho điều kiện đơn giản.
- Hiểu collection nào cho iterator theo thứ tự nào.

## Lỗi hay gặp

- Remove trực tiếp khỏi list trong enhanced for.
- Gọi next mà không hasNext.
- Dùng iterator từ collection cũ sau khi collection đổi lớn.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
