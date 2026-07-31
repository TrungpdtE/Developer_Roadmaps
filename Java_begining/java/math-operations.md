# Math Operations

> Nhóm: Learn the Basics

## Mục tiêu

- Nắm toán tử số học và thứ tự ưu tiên.
- Biết chia nguyên khác chia thực.
- Biết dùng `Math` và `BigDecimal` đúng chỗ.

## Lý thuyết dễ hiểu

Toán tử cơ bản gồm `+`, `-`, `*`, `/`, `%`. Toán tử `%` lấy phần dư, hữu ích để kiểm tra chẵn lẻ, chia trang, xử lý lịch.

Với số nguyên, phép chia bỏ phần thập phân. Nếu muốn kết quả số thực, ít nhất một toán hạng phải là `double` hoặc `float`.

## Facts cần nhớ

- `5 / 2` bằng `2` nếu cả hai toán hạng là `int`.
- `Math.round`, `Math.ceil`, `Math.floor` xử lý làm tròn khác nhau.
- `BigDecimal` nên tạo từ chuỗi, ví dụ `new BigDecimal("0.1")`.

## Code mẫu

```java
import java.math.BigDecimal;
import java.math.RoundingMode;

public class MathOperationsDemo {
    public static void main(String[] arguments) {
        int totalItems = 23;
        int pageSize = 10;
        int totalPages = (int) Math.ceil((double) totalItems / pageSize);

        BigDecimal price = new BigDecimal("19.99");
        BigDecimal quantity = new BigDecimal("3");
        BigDecimal total = price.multiply(quantity).setScale(2, RoundingMode.HALF_UP);

        System.out.println("Total pages: " + totalPages);
        System.out.println("Total price: " + total);
        System.out.println("Is even: " + (totalItems % 2 == 0));
    }
}
```

## Cách triển khai thực tế

- Trong pagination backend, dùng `ceil` để tính tổng số trang.
- Trong đơn hàng, dùng `BigDecimal` cho giá, thuế, giảm giá.
- Trong game/simulation, `double` thường chấp nhận được.

## Lỗi hay gặp

- Chia nguyên làm mất phần lẻ.
- So sánh `double` bằng `==` khi có sai số.
- Dùng `new BigDecimal(0.1)` tạo ra giá trị nhị phân không như mong đợi.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
