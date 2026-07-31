# Static Keyword

> Nhóm: Object Oriented Programming

## Mục tiêu

- Hiểu static thuộc class, không thuộc object.
- Dùng static method cho utility thuần.
- Biết rủi ro static mutable state.

## Lý thuyết dễ hiểu

`static` gắn thành viên vào class. `Math.max` là ví dụ static method hợp lý vì không cần trạng thái object.

Static mutable state dễ gây lỗi trong test, server nhiều request và đa luồng. Nếu cần dependency, thường dùng object và dependency injection.

## Facts cần nhớ

- `main` là static vì JVM gọi mà chưa cần tạo object.
- Static field dùng chung giữa mọi instance.
- Static method không truy cập trực tiếp instance field.

## Code mẫu

```java
public class PasswordRules {
    public static final int MINIMUM_LENGTH = 8;

    private PasswordRules() {
    }

    public static boolean isStrongPassword(String password) {
        return password != null
                && password.length() >= MINIMUM_LENGTH
                && password.chars().anyMatch(Character::isDigit);
    }
}

public class StaticDemo {
    public static void main(String[] arguments) {
        System.out.println(PasswordRules.isStrongPassword("java2026"));
    }
}
```

## Cách triển khai thực tế

- Dùng `static final` cho hằng số.
- Utility class nên có constructor private.
- Trong Spring app, service thường không cần static.

## Lỗi hay gặp

- Dùng static field để lưu user hiện tại.
- Static làm test phụ thuộc thứ tự chạy.
- Gọi static qua object thay vì qua class.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
