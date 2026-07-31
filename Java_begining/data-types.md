# Data Types

> Nhóm: Learn the Basics

## Mục tiêu

- Nắm primitive types và reference types.
- Biết chọn kiểu dữ liệu phù hợp cho số, ký tự, boolean và object.
- Hiểu wrapper classes như `Integer`, `Double`, `Boolean`.

## Lý thuyết dễ hiểu

Primitive lưu giá trị đơn giản, còn reference lưu tham chiếu đến object. Ví dụ `int age = 20` chứa trực tiếp số 20, còn `String name = "An"` là biến tham chiếu đến object chuỗi.

Wrapper class giúp primitive tham gia vào API cần object, ví dụ `List<Integer>` không thể là `List<int>`.

Chọn kiểu:

- Đếm số lượng bình thường: `int`.
- ID lớn hoặc timestamp milliseconds: `long`.
- Số thực khoa học: `double`.
- Tiền: `BigDecimal`.
- Đúng/sai: `boolean`.

## Facts cần nhớ

- Java có 8 primitive types: `byte`, `short`, `int`, `long`, `float`, `double`, `char`, `boolean`.
- `String` không phải primitive; nó là class.
- Giá trị tiền tệ không nên dùng `double`; dùng `BigDecimal` để tránh lỗi làm tròn nhị phân.

## Code mẫu

```java
import java.math.BigDecimal;

public class DataTypesDemo {
    public static void main(String[] arguments) {
        int productQuantity = 3;
        long userId = 9_000_000_000L;
        double temperature = 36.5;
        boolean isActive = true;
        char grade = 'A';
        String productName = "Notebook";
        BigDecimal price = new BigDecimal("19.99");

        System.out.println(productName + " x " + productQuantity);
        System.out.println("User ID: " + userId);
        System.out.println("Temperature: " + temperature);
        System.out.println("Active: " + isActive);
        System.out.println("Grade: " + grade);
        System.out.println("Price: " + price);
    }
}
```

## Cách triển khai thực tế

- Khi đọc JSON/API, kiểm tra kiểu dữ liệu thật: số có thể vượt `int`.
- Với database, map kiểu Java đúng với kiểu cột để tránh mất dữ liệu.
- Với form nhập liệu, dữ liệu ban đầu thường là `String`, cần parse và validate.

## Lỗi hay gặp

- Dùng `==` để so sánh `String`; hãy dùng `.equals`.
- Dùng `double` cho tiền.
- Quên hậu tố `L` khi literal long quá lớn.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
