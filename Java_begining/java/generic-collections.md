# Generic Collections

> Nhóm: Collections

## Mục tiêu

- Hiểu generics giúp type-safe.
- Biết `List<String>` khác raw `List`.
- Biết wildcard cơ bản.

## Lý thuyết dễ hiểu

Generics cho compiler biết collection chứa kiểu gì. Nhờ đó bạn tránh cast thủ công và bắt lỗi sớm.

## Facts cần nhớ

- Generics bị type erasure ở runtime.
- Không thể tạo `new T()` trực tiếp.
- `List<? extends Number>` đọc Number được, thêm khó.

## Code mẫu

```java
import java.util.ArrayList;
import java.util.List;

public class GenericCollectionsDemo {
    public static void main(String[] arguments) {
        List<String> names = new ArrayList<>();
        names.add("An");

        String firstName = names.get(0);
        System.out.println(firstName.toUpperCase());
    }

    public static double sumNumbers(List<? extends Number> numbers) {
        double total = 0;
        for (Number number : numbers) {
            total = total + number.doubleValue();
        }
        return total;
    }
}
```

## Cách triển khai thực tế

- Luôn dùng generic type rõ.
- Wildcard hữu ích cho API nhận nhiều subtype.
- PECS: producer extends, consumer super.

## Lỗi hay gặp

- Dùng raw type.
- Ép kiểu thủ công không cần thiết.
- Không hiểu invariance: `List<Integer>` không phải `List<Number>`.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
