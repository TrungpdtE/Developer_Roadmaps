# Attributes and Methods

> Nhóm: Object Oriented Programming

## Mục tiêu

- Phân biệt field/attribute và method.
- Biết getter/setter khi thật sự cần.
- Biết method trả về giá trị thay vì chỉ in ra console.

## Lý thuyết dễ hiểu

Attribute/field biểu diễn trạng thái. Method biểu diễn hành vi. Trong Java, field nằm trong class nhưng ngoài method.

Người mới hay viết object chỉ có getter/setter. Cách tốt hơn là đặt hành vi vào object: thay vì `setBalance`, hãy có `deposit` và `withdraw` để kiểm soát quy tắc.

## Facts cần nhớ

- Field nên để `private` trong đa số trường hợp.
- Getter không bắt buộc nếu object có method nghiệp vụ tốt hơn.
- Method có thể overload cùng tên nhưng khác tham số.

## Code mẫu

```java
import java.math.BigDecimal;

public class BankAccount {
    private BigDecimal balance = BigDecimal.ZERO;

    public void deposit(BigDecimal amount) {
        if (amount.compareTo(BigDecimal.ZERO) <= 0) {
            throw new IllegalArgumentException("Deposit amount must be positive");
        }
        balance = balance.add(amount);
    }

    public boolean canWithdraw(BigDecimal amount) {
        return amount.compareTo(BigDecimal.ZERO) > 0 && balance.compareTo(amount) >= 0;
    }

    public void withdraw(BigDecimal amount) {
        if (!canWithdraw(amount)) {
            throw new IllegalArgumentException("Invalid withdraw amount");
        }
        balance = balance.subtract(amount);
    }

    public BigDecimal getBalance() {
        return balance;
    }
}
```

## Cách triển khai thực tế

- Đưa rule vào method để tránh dữ liệu sai.
- Getter dùng cho đọc dữ liệu; setter chỉ dùng khi mutation hợp lệ và cần thiết.
- Method trả về dữ liệu giúp viết test dễ hơn in console.

## Lỗi hay gặp

- Setter public cho mọi field.
- Method tên không nói lên hành động.
- Method phụ thuộc quá nhiều biến global/static.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
