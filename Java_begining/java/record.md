# Record

> Nhóm: More about OOP

## Mục tiêu

- Biết record dùng cho immutable data carrier.
- Hiểu constructor compact.
- Biết record tự có accessor, equals, hashCode, toString.

## Lý thuyết dễ hiểu

Record giảm boilerplate khi bạn cần object chủ yếu để chứa dữ liệu bất biến. Nó tự tạo constructor, accessor, `equals`, `hashCode`, `toString`.

Record không thay thế mọi class. Nếu object có nhiều mutation hoặc lifecycle phức tạp, class thường rõ hơn.

## Facts cần nhớ

- Record là final.
- Field của record là private final.
- Record phù hợp DTO/value object nhỏ.

## Code mẫu

```java
public record EmailAddress(String value) {
    public EmailAddress {
        if (value == null || !value.contains("@")) {
            throw new IllegalArgumentException("Invalid email address");
        }
        value = value.trim().toLowerCase();
    }
}

public class RecordDemo {
    public static void main(String[] arguments) {
        EmailAddress emailAddress = new EmailAddress(" AN@example.com ");
        System.out.println(emailAddress.value());
    }
}
```

## Cách triển khai thực tế

- Dùng record cho request/response DTO.
- Dùng record cho key trong map nếu dữ liệu immutable.
- Validate trong compact constructor.

## Lỗi hay gặp

- Tưởng record không thể có method.
- Dùng record cho entity mutable phức tạp.
- Accessor record là `value()`, không phải `getValue()`.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
