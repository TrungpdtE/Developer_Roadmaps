# Inheritance

> Nhóm: More about OOP

## Mục tiêu

- Hiểu `extends` và quan hệ is-a.
- Biết override method.
- Biết ưu tiên composition khi không phải is-a thật.

## Lý thuyết dễ hiểu

Inheritance cho phép class con tái sử dụng và mở rộng class cha. Nó phù hợp khi quan hệ thật sự là "là một", ví dụ `SavingsAccount` là một `BankAccount`.

Nếu chỉ muốn dùng lại hành vi, composition thường sạch hơn: class có một dependency thay vì kế thừa dependency đó.

## Facts cần nhớ

- Java chỉ cho class extends một class.
- Subclass gọi constructor superclass bằng `super(...)`.
- Method `final` không override được.

## Code mẫu

```java
public abstract class NotificationSender {
    public void send(String receiver, String message) {
        validate(receiver, message);
        doSend(receiver, message);
    }

    private void validate(String receiver, String message) {
        if (receiver == null || receiver.isBlank() || message == null || message.isBlank()) {
            throw new IllegalArgumentException("Receiver and message are required");
        }
    }

    protected abstract void doSend(String receiver, String message);
}

public class EmailNotificationSender extends NotificationSender {
    @Override
    protected void doSend(String receiver, String message) {
        System.out.println("Sending email to " + receiver + ": " + message);
    }
}
```

## Cách triển khai thực tế

- Dùng abstract class khi muốn chia sẻ state/logic chung.
- Dùng interface khi muốn contract linh hoạt.
- Override phải giữ ý nghĩa contract của method cha.

## Lỗi hay gặp

- Kế thừa chỉ để lấy vài method tiện ích.
- Cây kế thừa quá sâu.
- Superclass thay đổi làm subclass lỗi dây chuyền.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
