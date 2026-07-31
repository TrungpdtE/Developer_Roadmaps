# Conditionals

> Nhóm: Learn the Basics

## Mục tiêu

- Dùng `if`, `else if`, `else` rõ ràng.
- Biết dùng `switch` cho nhiều nhánh theo giá trị.
- Biết viết điều kiện dễ đọc.

## Lý thuyết dễ hiểu

Conditional giúp chương trình rẽ nhánh theo điều kiện. Điều kiện càng phức tạp càng nên tách thành biến boolean có tên rõ nghĩa.

Ví dụ `boolean isEligibleForDiscount = age >= 18 && hasMembership;` dễ đọc hơn việc nhét toàn bộ biểu thức vào `if`.

## Facts cần nhớ

- `&&` short-circuit: vế phải không chạy nếu vế trái đã false.
- `||` short-circuit: vế phải không chạy nếu vế trái đã true.
- `switch` hiện đại có thể dùng arrow syntax trong Java mới.

## Code mẫu

```java
public class ConditionalsDemo {
    public static void main(String[] arguments) {
        int age = 20;
        boolean hasStudentCard = true;

        boolean canReceiveStudentDiscount = age <= 25 && hasStudentCard;

        if (canReceiveStudentDiscount) {
            System.out.println("Discount: 20%");
        } else if (age >= 60) {
            System.out.println("Discount: 15%");
        } else {
            System.out.println("No discount");
        }

        String orderStatus = "PAID";
        String message = switch (orderStatus) {
            case "NEW" -> "Order created";
            case "PAID" -> "Payment received";
            case "SHIPPED" -> "Order shipped";
            default -> "Unknown status";
        };

        System.out.println(message);
    }
}
```

## Cách triển khai thực tế

- Trong business logic, đặt tên biến boolean theo câu hỏi: `isValid`, `hasPermission`, `canCheckout`.
- Dùng guard clause để tránh lồng `if` quá sâu.
- Với trạng thái cố định, cân nhắc dùng enum thay vì string.

## Lỗi hay gặp

- Dùng `=` thay vì `==` trong điều kiện.
- Điều kiện phủ nhau làm nhánh sau không bao giờ chạy.
- So sánh string bằng `==`.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
