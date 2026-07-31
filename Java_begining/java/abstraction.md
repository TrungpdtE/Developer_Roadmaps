# Abstraction

> Nhóm: More about OOP

## Mục tiêu

- Hiểu abstraction là giấu chi tiết, lộ ý nghĩa.
- Biết abstract class và interface.
- Thiết kế API theo nhu cầu caller.

## Lý thuyết dễ hiểu

Abstraction trả lời câu hỏi: caller cần biết gì để dùng được chức năng? Ví dụ `PaymentGateway.charge(...)` giấu chi tiết HTTP request, token, retry.

Đừng tạo interface cho mọi class chỉ vì thói quen. Tạo khi có nhiều implementation, cần mock boundary ngoài, hoặc muốn tách domain khỏi framework.

## Facts cần nhớ

- Abstraction tốt làm code gọi không phụ thuộc chi tiết triển khai.
- Quá nhiều abstraction sớm làm code khó hiểu.
- Tên abstraction phải có ý nghĩa domain.

## Code mẫu

```java
import java.math.BigDecimal;

public interface PaymentGateway {
    PaymentResult charge(String customerId, BigDecimal amount);
}

public record PaymentResult(boolean successful, String transactionId) {
}

public class CheckoutService {
    private final PaymentGateway paymentGateway;

    public CheckoutService(PaymentGateway paymentGateway) {
        this.paymentGateway = paymentGateway;
    }

    public PaymentResult checkout(String customerId, BigDecimal totalAmount) {
        return paymentGateway.charge(customerId, totalAmount);
    }
}
```

## Cách triển khai thực tế

- Interface cho boundary như payment, email, storage.
- Abstract class khi cần chia sẻ template algorithm.
- Caller nên thấy intent, không thấy chi tiết kỹ thuật.

## Lỗi hay gặp

- Interface một implementation không có lý do.
- Tên `Manager`, `Processor` quá chung.
- Abstraction leak: caller vẫn phải biết chi tiết bên trong.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
