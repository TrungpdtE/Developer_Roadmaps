# Functional Interfaces

> Nhóm: Functional Programming

## Mục tiêu

- Biết interface có một abstract method.
- Dùng `@FunctionalInterface`.
- Nắm Predicate, Function, Consumer, Supplier.

## Lý thuyết dễ hiểu

Functional interface là nền tảng để lambda có kiểu. Java chuẩn có nhiều interface trong `java.util.function`.

## Facts cần nhớ

- `@FunctionalInterface` không bắt buộc nhưng giúp compiler kiểm tra.
- Default method không phá functional interface.
- Method reference là dạng rút gọn của lambda.

## Code mẫu

```java
import java.util.function.Function;
import java.util.function.Supplier;

@FunctionalInterface
interface TextNormalizer {
    String normalize(String text);
}

public class FunctionalInterfaceDemo {
    public static void main(String[] arguments) {
        TextNormalizer normalizer = text -> text.trim().toLowerCase();
        Function<String, Integer> lengthFunction = String::length;
        Supplier<String> defaultNameSupplier = () -> "guest";

        System.out.println(normalizer.normalize("  JAVA  "));
        System.out.println(lengthFunction.apply("Java"));
        System.out.println(defaultNameSupplier.get());
    }
}
```

## Cách triển khai thực tế

- Predicate: kiểm tra đúng/sai.
- Function: biến đổi input thành output.
- Consumer: nhận input và không trả về.
- Supplier: không nhận input và trả về output.

## Lỗi hay gặp

- Nhầm `Function` và `Consumer`.
- Bỏ `@FunctionalInterface` rồi vô tình thêm method abstract thứ hai.
- Dùng custom interface khi interface chuẩn đã đủ.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
