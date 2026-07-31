# Type Casting

> Nhóm: Learn the Basics

## Mục tiêu

- Hiểu widening và narrowing conversion.
- Biết cast object an toàn với `instanceof`.
- Biết parse `String` sang số.

## Lý thuyết dễ hiểu

Casting là chuyển giá trị từ kiểu này sang kiểu khác. Có hai nhóm:

- Numeric casting: chuyển giữa kiểu số.
- Reference casting: chuyển giữa kiểu object trong cây kế thừa/interface.

`Integer.parseInt("123")` không phải cast mà là parse: chuyển text thành số. Với dữ liệu người dùng nhập, parse có thể lỗi nên cần xử lý exception.

## Facts cần nhớ

- Widening như `int` sang `long` thường tự động.
- Narrowing như `double` sang `int` cần cast và có thể mất dữ liệu.
- Ép kiểu object sai gây `ClassCastException`.

## Code mẫu

```java
public class TypeCastingDemo {
    public static void main(String[] arguments) {
        int smallNumber = 100;
        long biggerNumber = smallNumber;

        double price = 19.95;
        int truncatedPrice = (int) price;

        String quantityText = "42";
        int quantity = Integer.parseInt(quantityText);

        Object value = "Java";
        if (value instanceof String text) {
            System.out.println(text.toUpperCase());
        }

        System.out.println(biggerNumber);
        System.out.println(truncatedPrice);
        System.out.println(quantity);
    }
}
```

## Cách triển khai thực tế

- Validate input trước khi parse trong API/controller.
- Dùng DTO có kiểu rõ để giảm casting thủ công.
- Với tiền và tỷ lệ, ưu tiên kiểu dữ liệu chính xác thay vì cast qua lại.

## Lỗi hay gặp

- `(int) 19.95` thành `19`, không làm tròn.
- Parse chuỗi rỗng gây `NumberFormatException`.
- Cast object dựa vào đoán mò thay vì kiểm tra kiểu.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
