# Enums

> Nhóm: More about OOP

## Mục tiêu

- Dùng enum cho tập giá trị cố định.
- Biết enum có field, constructor và method.
- Tránh string magic cho trạng thái.

## Lý thuyết dễ hiểu

Enum biểu diễn danh sách giá trị hữu hạn như trạng thái đơn hàng, loại user, vai trò. So với string, enum giúp compiler bắt lỗi chính tả và hỗ trợ refactor.

## Facts cần nhớ

- Enum instance là singleton theo từng constant.
- Constructor enum luôn private ngầm định.
- Enum dùng tốt với `switch`.

## Code mẫu

```java
public enum OrderStatus {
    NEW("New order"),
    PAID("Payment received"),
    SHIPPED("Order shipped"),
    CANCELLED("Order cancelled");

    private final String displayName;

    OrderStatus(String displayName) {
        this.displayName = displayName;
    }

    public String getDisplayName() {
        return displayName;
    }

    public boolean canCancel() {
        return this == NEW || this == PAID;
    }
}
```

## Cách triển khai thực tế

- Dùng enum cho state machine đơn giản.
- Map enum sang database bằng string để dễ đọc.
- Thêm method vào enum khi logic phụ thuộc vào constant.

## Lỗi hay gặp

- Dùng ordinal trong database, dễ vỡ khi đổi thứ tự.
- Enum quá lớn chứa quá nhiều business logic.
- Cần config động mà lại hard-code enum.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
