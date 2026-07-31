# Initializer Block

> Nhóm: More about OOP

## Mục tiêu

- Hiểu instance initializer và static initializer.
- Biết thứ tự chạy field initializer, block, constructor.
- Biết vì sao ít dùng trong code business.

## Lý thuyết dễ hiểu

Initializer block là block code đặt trực tiếp trong class. Static block dùng `static {}` và chạy một lần khi class load. Instance block dùng `{}` và chạy mỗi lần tạo object.

Trong thực tế, static block đôi khi dùng để chuẩn bị hằng số phức tạp, nhưng trong app hiện đại bạn thường dùng constructor, factory method hoặc dependency injection.

## Facts cần nhớ

- Static initializer chạy khi class được load.
- Instance initializer chạy trước constructor body.
- Hầu hết trường hợp constructor rõ ràng hơn initializer block.

## Code mẫu

```java
import java.util.HashMap;
import java.util.Map;

public class InitializerBlockDemo {
    private static final Map<String, String> COUNTRY_CODES = new HashMap<>();

    static {
        COUNTRY_CODES.put("VN", "Vietnam");
        COUNTRY_CODES.put("US", "United States");
    }

    private final long createdAtMillis;

    {
        createdAtMillis = System.currentTimeMillis();
    }
}
```

## Cách triển khai thực tế

- Ưu tiên `Map.of` nếu dữ liệu nhỏ và immutable.
- Dùng constructor cho logic tạo object có tham số.
- Static block có lỗi sẽ làm class load thất bại.

## Lỗi hay gặp

- Đặt logic nặng trong static block.
- Initializer làm người đọc khó theo thứ tự chạy.
- Dùng mutable static map công khai.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
