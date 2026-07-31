# Regular Expressions

> Nhóm: Advanced Java

## Mục tiêu

- Biết regex dùng để match pattern text.
- Dùng `Pattern` và `Matcher`.
- Biết khi nào không nên dùng regex.

## Lý thuyết dễ hiểu

Regex phù hợp validate format đơn giản, tách token, tìm pattern. Nó không phù hợp parse HTML/JSON phức tạp; hãy dùng parser chuyên dụng.

## Facts cần nhớ

- Regex mạnh nhưng khó đọc nếu quá phức tạp.
- Compile `Pattern` một lần nếu dùng nhiều.
- Một số regex xấu có thể gây backtracking rất chậm.

## Code mẫu

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegexDemo {
    private static final Pattern EMAIL_PATTERN = Pattern.compile(
            "^[A-Za-z0-9+_.-]+@[A-Za-z0-9.-]+$"
    );

    public static void main(String[] arguments) {
        String email = "student@example.com";
        Matcher matcher = EMAIL_PATTERN.matcher(email);
        System.out.println("Valid: " + matcher.matches());
    }
}
```

## Cách triển khai thực tế

- Dùng regex đơn giản cho client/server validation sơ bộ.
- Với email thật, validation hoàn hảo rất phức tạp; thường chỉ kiểm tra format vừa đủ.
- Đặt regex phức tạp thành hằng số có tên.

## Lỗi hay gặp

- Regex quá tham lam.
- Không escape ký tự đặc biệt.
- Dùng regex parse cấu trúc lồng nhau.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
