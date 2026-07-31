# Java Patterns

> Nhóm: Java Patterns  
> Mức ưu tiên: Personal must know

## Học để làm gì?

Design patterns và concurrency patterns giúp đặt tên giải pháp, không phải công thức dùng mù quáng.

## Kiến thức cốt lõi

- Pattern là ngôn ngữ chung để nói về giải pháp, không phải checklist bắt buộc.
- Nếu pattern làm code khó đọc hơn cho bài toán nhỏ, đừng dùng.
- Luôn ưu tiên requirement và code hiện có trước khi áp pattern.

## Facts cần nhớ

- Mức ưu tiên trong roadmap: **Personal must know**. Bắt buộc học nếu bạn muốn đi Java backend nghiêm túc.
- Nhóm học: **Java Patterns**.
- Học bằng cách tự gõ lại ví dụ, tự đổi bài toán, rồi ghi chú lỗi gặp phải.
- Khi dùng trong production, luôn kiểm tra version, tài liệu chính thức, security advisory và compatibility với JDK/framework hiện tại.

## Ví dụ code hoặc cấu hình

```java
public interface PaymentStrategy {
    void pay(int amountInCents);
}

public class CardPaymentStrategy implements PaymentStrategy {
    @Override
    public void pay(int amountInCents) {
        System.out.println("Paying by card: " + amountInCents);
    }
}

public class CheckoutService {
    private final PaymentStrategy paymentStrategy;

    public CheckoutService(PaymentStrategy paymentStrategy) {
        this.paymentStrategy = paymentStrategy;
    }

    public void checkout(int amountInCents) {
        paymentStrategy.pay(amountInCents);
    }
}
```

## Cách triển khai thực tế

- Bắt đầu bằng ví dụ nhỏ chạy được, sau đó mới đưa vào Spring/service lớn.
- Viết README ngắn trong project về cách chạy, cách test và các biến môi trường cần có.
- Với thư viện/framework, tạo một wrapper/service mỏng nếu bạn muốn giảm phụ thuộc trực tiếp trong toàn bộ codebase.
- Luôn có test cho happy path, input lỗi và case biên.
- Khi có network, database, cache hoặc message broker, luôn cấu hình timeout, retry hợp lý và log đủ context.

## Lỗi hay gặp

- Học thuộc API nhưng không hiểu vấn đề mà công nghệ đó giải quyết.
- Copy code mẫu nhưng không hiểu dependency, import, version và lifecycle.
- Dùng công nghệ vì thấy trong roadmap, không kiểm tra dự án có thật sự cần không.
- Bỏ qua failure mode: timeout, null, duplicate request, retry, partial failure, dữ liệu cũ.
- Không viết test nên refactor hoặc nâng version rất rủi ro.

## Checklist tự học

1. Giải thích chủ đề này trong 5 câu bằng lời của bạn.
2. Gõ lại ví dụ trong file này, không copy paste.
3. Sửa ví dụ sang bài toán sinh viên, khóa học, đăng ký môn hoặc đơn hàng.
4. Tạo ít nhất một lỗi cố ý rồi đọc lỗi compile/runtime.
5. Viết một test hoặc một script kiểm tra hành vi chính.
6. Ghi lại khi nào nên dùng và khi nào không nên dùng chủ đề này.

## Từ khóa tra cứu thêm

- `Java Patterns Java official documentation`
- `Java Patterns best practices Java`
- `Java Patterns production pitfalls`
- `Java Patterns Spring Boot integration`


[Quay lại roadmap](../README.md)
