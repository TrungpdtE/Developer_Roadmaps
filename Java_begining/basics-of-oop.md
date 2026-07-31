# Basics of OOP

> Nhóm: Learn the Basics

## Mục tiêu

- Hiểu object, class, state và behavior.
- Nắm bốn trụ cột OOP: encapsulation, abstraction, inheritance, polymorphism.
- Biết tư duy model hóa bài toán bằng object.

## Lý thuyết dễ hiểu

Class là bản thiết kế, object là thực thể được tạo từ class. Object có state (dữ liệu) và behavior (hành vi).

Ví dụ trong app bán hàng: `Product`, `Customer`, `Order` là các khái niệm tự nhiên. `Order` có danh sách item và có hành vi tính tổng tiền.

Bốn ý chính:

- Encapsulation: giấu dữ liệu bên trong, chỉ mở method cần thiết.
- Abstraction: chỉ lộ ra ý nghĩa quan trọng, giấu chi tiết.
- Inheritance: tái sử dụng/biểu diễn quan hệ "là một".
- Polymorphism: cùng interface nhưng nhiều cách triển khai.

## Facts cần nhớ

- Java là ngôn ngữ hướng đối tượng mạnh, nhưng primitive không phải object.
- OOP tốt không có nghĩa là kế thừa thật nhiều.
- Encapsulation thường quan trọng hơn inheritance trong code business.

## Code mẫu

```java
import java.math.BigDecimal;
import java.util.ArrayList;
import java.util.List;

public class Order {
    private final List<BigDecimal> itemPrices = new ArrayList<>();

    public void addItem(BigDecimal itemPrice) {
        if (itemPrice.compareTo(BigDecimal.ZERO) <= 0) {
            throw new IllegalArgumentException("Item price must be positive");
        }
        itemPrices.add(itemPrice);
    }

    public BigDecimal calculateTotal() {
        BigDecimal total = BigDecimal.ZERO;
        for (BigDecimal itemPrice : itemPrices) {
            total = total.add(itemPrice);
        }
        return total;
    }
}
```

## Cách triển khai thực tế

- Bắt đầu từ domain thật: sinh viên, môn học, đơn hàng, tài khoản.
- Class nên giữ invariant, ví dụ giá không âm, email hợp lệ.
- Không để mọi field public vì object sẽ mất kiểm soát trạng thái.

## Lỗi hay gặp

- Tạo class chỉ để chứa data mà không có quy tắc nào.
- Kế thừa khi chỉ cần composition.
- Nhầm object với database table 1-1 trong mọi trường hợp.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
