# Encapsulation

> Nhóm: More about OOP

## Mục tiêu

- Giấu state bên trong object.
- Mở method nghiệp vụ thay vì setter tràn lan.
- Bảo vệ invariant.

## Lý thuyết dễ hiểu

Encapsulation giúp object giữ trạng thái hợp lệ. Bên ngoài không nên sửa trực tiếp field quan trọng. Thay vào đó, object cung cấp method có kiểm tra quy tắc.

## Facts cần nhớ

- Encapsulation không chỉ là private field + getter/setter.
- Collection mutable cần copy khi nhận/trả.
- Object tự kiểm soát dữ liệu của nó dễ test hơn.

## Code mẫu

```java
import java.util.ArrayList;
import java.util.List;

public class ShoppingCart {
    private final List<String> productIds = new ArrayList<>();

    public void addProduct(String productId) {
        if (productId == null || productId.isBlank()) {
            throw new IllegalArgumentException("Product ID is required");
        }
        productIds.add(productId);
    }

    public List<String> getProductIds() {
        return List.copyOf(productIds);
    }
}
```

## Cách triển khai thực tế

- Domain object nên giữ rule cốt lõi.
- DTO có thể đơn giản hơn domain object.
- Copy collection để tránh bên ngoài sửa dữ liệu nội bộ.

## Lỗi hay gặp

- Getter trả list gốc.
- Setter bỏ qua validate.
- Để service ngoài tự sửa mọi field của entity.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
