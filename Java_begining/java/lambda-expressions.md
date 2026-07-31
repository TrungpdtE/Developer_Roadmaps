# Lambda Expressions

> Nhóm: Advanced Java

## Mục tiêu

- Hiểu lambda là cách viết ngắn cho functional interface.
- Biết syntax `(input) -> output`.
- Dùng lambda với collection và callback.

## Lý thuyết dễ hiểu

Lambda giúp truyền hành vi như dữ liệu. Thay vì tạo class anonymous dài, bạn viết function nhỏ inline.

Lambda không phải phép màu. Nó vẫn có kiểu cụ thể, thường là `Predicate<T>`, `Function<T,R>`, `Consumer<T>`, `Supplier<T>` hoặc interface tự tạo có một abstract method.

## Facts cần nhớ

- Lambda xuất hiện từ Java 8.
- Lambda cần target type là functional interface.
- Biến bên ngoài lambda phải final hoặc effectively final.

## Code mẫu

```java
import java.util.List;
import java.util.function.Predicate;

public class LambdaDemo {
    public static void main(String[] arguments) {
        List<String> names = List.of("An", "Binh", "Chi");
        Predicate<String> hasThreeCharacters = name -> name.length() == 3;

        for (String name : names) {
            if (hasThreeCharacters.test(name)) {
                System.out.println(name);
            }
        }
    }
}
```

## Cách triển khai thực tế

- Dùng lambda cho filter, map, sort, event handler.
- Nếu lambda dài, tách thành method có tên.
- Đặt tên biến trong lambda rõ nghĩa.

## Lỗi hay gặp

- Nhồi business logic dài vào lambda.
- Không hiểu functional interface phía sau.
- Gây side effect trong stream/lambda làm khó debug.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
