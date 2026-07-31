# Functional Composition

> Nhóm: Functional Programming

## Mục tiêu

- Ghép nhiều function nhỏ.
- Dùng `andThen`, `compose`, `and`, `or`.
- Viết pipeline dễ đọc.

## Lý thuyết dễ hiểu

Functional composition tạo logic lớn từ nhiều bước nhỏ. Mỗi bước nên dễ hiểu, có input/output rõ và ít side effect.

## Facts cần nhớ

- Composition tốt khi function thuần và nhỏ.
- `andThen` chạy function hiện tại trước.
- `compose` chạy function truyền vào trước.

## Code mẫu

```java
import java.util.function.Function;
import java.util.function.Predicate;

public class FunctionalCompositionDemo {
    public static void main(String[] arguments) {
        Function<String, String> trim = String::trim;
        Function<String, String> lower = String::toLowerCase;
        Function<String, String> normalize = trim.andThen(lower);

        Predicate<String> notBlank = text -> !text.isBlank();
        Predicate<String> hasAtSign = text -> text.contains("@");
        Predicate<String> validEmailLikeText = notBlank.and(hasAtSign);

        System.out.println(normalize.apply("  JAVA  "));
        System.out.println(validEmailLikeText.test("student@example.com"));
    }
}
```

## Cách triển khai thực tế

- Dùng composition cho validation pipeline.
- Đặt tên từng function để debug dễ.
- Nếu pipeline dài, cân nhắc class/service rõ ràng.

## Lỗi hay gặp

- Composition quá thông minh làm người mới khó đọc.
- Function có side effect làm thứ tự khó đoán.
- Không xử lý exception trong function.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
