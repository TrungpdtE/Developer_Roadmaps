# High Order Functions

> Nhóm: Functional Programming

## Mục tiêu

- Hiểu function nhận function hoặc trả function.
- Dùng functional interface làm tham số.
- Biết ứng dụng cho filter/map/strategy.

## Lý thuyết dễ hiểu

High-order function là method nhận hành vi như tham số. Trong Java, hành vi đó là object implement functional interface.

## Facts cần nhớ

- Java không có function type riêng; dùng functional interface.
- Higher-order style giúp tái sử dụng logic lặp.
- Lambda làm high-order function dễ viết hơn.

## Code mẫu

```java
import java.util.ArrayList;
import java.util.List;
import java.util.function.Predicate;

public class HighOrderDemo {
    public static List<String> filterNames(List<String> names, Predicate<String> condition) {
        List<String> result = new ArrayList<>();
        for (String name : names) {
            if (condition.test(name)) {
                result.add(name);
            }
        }
        return result;
    }
}
```

## Cách triển khai thực tế

- Dùng strategy bằng lambda cho rule nhỏ.
- Tách condition thành Predicate có tên khi cần đọc rõ.
- Không dùng high-order function nếu loop thường dễ hiểu hơn.

## Lỗi hay gặp

- Lambda side effect khó debug.
- Generic quá mức.
- Tạo abstraction functional khi team chưa cần.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
