# Nested Classes

> Nhóm: Object Oriented Programming

## Mục tiêu

- Biết static nested class, inner class, local class, anonymous class.
- Dùng nested class khi concept phụ thuộc mạnh vào class ngoài.
- Tránh nested class quá sâu.

## Lý thuyết dễ hiểu

Nested class là class khai báo bên trong class khác. Nó hữu ích khi class con chỉ có ý nghĩa trong ngữ cảnh class ngoài, ví dụ `Order.OrderLine`.

Ưu tiên static nested class nếu không cần truy cập state của object ngoài, vì ít phụ thuộc và tránh giữ reference không cần thiết.

## Facts cần nhớ

- Static nested class không giữ reference tự động đến object ngoài.
- Inner class giữ reference đến instance ngoài.
- Anonymous class trước đây hay dùng cho callback, nay lambda thường gọn hơn.

## Code mẫu

```java
import java.math.BigDecimal;
import java.util.ArrayList;
import java.util.List;

public class Invoice {
    private final List<LineItem> lineItems = new ArrayList<>();

    public void addLine(String name, BigDecimal price) {
        lineItems.add(new LineItem(name, price));
    }

    public static class LineItem {
        private final String name;
        private final BigDecimal price;

        public LineItem(String name, BigDecimal price) {
            this.name = name;
            this.price = price;
        }
    }
}
```

## Cách triển khai thực tế

- Dùng nested DTO nhỏ khi chỉ phục vụ một API response.
- Builder pattern thường dùng static nested `Builder`.
- Không lạm dụng nếu class có thể sống độc lập.

## Lỗi hay gặp

- Inner class vô tình giữ object ngoài lâu hơn cần thiết.
- Nested class quá nhiều tầng khó đọc.
- Dùng nested class để che giấu thiết kế domain chưa rõ.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
