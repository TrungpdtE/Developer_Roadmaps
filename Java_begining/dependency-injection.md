# Dependency Injection

> Nhóm: Advanced Java

## Mục tiêu

- Hiểu DI là truyền dependency từ ngoài vào.
- Biết constructor injection.
- Hiểu DI container như Spring.

## Lý thuyết dễ hiểu

Dependency là object/class mà class hiện tại cần để làm việc. Thay vì tự `new EmailSender()` bên trong, class nhận `EmailSender` từ constructor. Nhờ vậy bạn thay implementation thật bằng fake/mock khi test.

## Facts cần nhớ

- DI giảm coupling và giúp test dễ.
- Constructor injection làm dependency bắt buộc rõ ràng.
- Service locator khác DI vì class tự đi tìm dependency.

## Code mẫu

```java
public interface EmailSender {
    void sendEmail(String receiver, String subject, String body);
}

public class RegistrationService {
    private final EmailSender emailSender;

    public RegistrationService(EmailSender emailSender) {
        this.emailSender = emailSender;
    }

    public void register(String email) {
        System.out.println("Saving user " + email);
        emailSender.sendEmail(email, "Welcome", "Thanks for registering");
    }
}
```

## Cách triển khai thực tế

- Trong Spring, `@Service` class được container tạo và inject dependency.
- Ưu tiên constructor injection hơn field injection.
- DI không bắt buộc phải dùng framework; bạn có thể tự wire object.

## Lỗi hay gặp

- Tự `new` dependency hard-code trong service.
- Field injection làm test khó và dependency ẩn.
- Tạo quá nhiều abstraction chỉ để DI.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
