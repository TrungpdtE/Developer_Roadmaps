# Optionals

> Nhóm: Advanced Java

## Mục tiêu

- Dùng `Optional` để biểu diễn có/không có giá trị trả về.
- Biết `map`, `orElse`, `orElseGet`, `orElseThrow`.
- Tránh dùng Optional sai chỗ.

## Lý thuyết dễ hiểu

`Optional<T>` làm rõ method có thể không tìm thấy kết quả. Nó buộc caller xử lý case rỗng thay vì nhận `null` bất ngờ.

## Facts cần nhớ

- `Optional` không nên dùng cho field entity.
- `orElse` luôn tính giá trị default, `orElseGet` lazy.
- `Optional.get()` không kiểm tra có thể lỗi.

## Code mẫu

```java
import java.util.Map;
import java.util.Optional;

public class OptionalDemo {
    private static final Map<String, String> USERS = Map.of("1", "An");

    public static void main(String[] arguments) {
        String displayName = findUserName("2")
                .map(String::toUpperCase)
                .orElse("GUEST");

        System.out.println(displayName);
    }

    static Optional<String> findUserName(String userId) {
        return Optional.ofNullable(USERS.get(userId));
    }
}
```

## Cách triển khai thực tế

- Return Optional từ repository/service khi kết quả có thể vắng.
- Dùng `orElseThrow` khi thiếu dữ liệu là lỗi.
- Dùng `map` để biến đổi nếu có giá trị.

## Lỗi hay gặp

- Gọi `.get()` ngay lập tức.
- Dùng Optional cho parameter.
- Bọc collection trong Optional thay vì trả empty list.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
