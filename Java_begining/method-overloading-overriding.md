# Method Overloading / Overriding

> Nhóm: More about OOP

## Mục tiêu

- Phân biệt overload và override.
- Hiểu compile-time vs runtime dispatch.
- Biết annotation `@Override`.

## Lý thuyết dễ hiểu

Overloading được chọn lúc compile dựa vào kiểu tham số. Overriding được chọn lúc runtime dựa vào object thật.

Đây là nền tảng của polymorphism: biến kiểu interface có thể trỏ đến nhiều implementation khác nhau.

## Facts cần nhớ

- Overloading: cùng tên, khác danh sách tham số.
- Overriding: subclass triển khai lại method của superclass/interface.
- `@Override` giúp compiler bắt lỗi đánh máy.

## Code mẫu

```java
public class MessagePrinter {
    public void print(String message) {
        System.out.println(message);
    }

    public void print(String message, int repeatCount) {
        for (int count = 0; count < repeatCount; count++) {
            System.out.println(message);
        }
    }
}

interface Animal {
    void speak();
}

class Dog implements Animal {
    @Override
    public void speak() {
        System.out.println("Woof");
    }
}
```

## Cách triển khai thực tế

- Dùng overload khi cùng ý nghĩa nhưng input khác.
- Luôn thêm `@Override`.
- Tránh overload quá mơ hồ với `null`.

## Lỗi hay gặp

- Nhầm overload là override.
- Đổi return type không đủ để overload.
- Override nhưng giảm visibility làm lỗi compile.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
