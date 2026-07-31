# Mocking > Mockito

> Nhóm: Testing

## Mục tiêu

- Hiểu mock thay dependency ngoài.
- Dùng Mockito verify/stub.
- Biết không mock mọi thứ.

## Lý thuyết dễ hiểu

Mocking giúp kiểm tra class trong isolation. Bạn thay dependency thật bằng mock để kiểm soát output và verify interaction.

## Facts cần nhớ

- Mockito phổ biến cho unit test Java.
- Mock phù hợp boundary như email/payment/repository.
- Mock quá nhiều làm test bám implementation.

## Code mẫu

```java
import org.junit.jupiter.api.Test;

import static org.mockito.Mockito.mock;
import static org.mockito.Mockito.verify;

class RegistrationServiceTest {
    @Test
    void registerShouldSendWelcomeEmail() {
        EmailSender emailSender = mock(EmailSender.class);
        RegistrationService registrationService = new RegistrationService(emailSender);

        registrationService.register("an@example.com");

        verify(emailSender).sendEmail(
                "an@example.com",
                "Welcome",
                "Thanks for registering"
        );
    }
}
```

## Cách triển khai thực tế

- Mock dependency chậm/ngoài hệ thống.
- Không mock value object.
- Ưu tiên assert output hơn verify interaction nếu có thể.

## Lỗi hay gặp

- Mock class đang test.
- Mock chain quá sâu.
- Test pass nhưng behavior thật fail vì mock không giống dependency thật.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
