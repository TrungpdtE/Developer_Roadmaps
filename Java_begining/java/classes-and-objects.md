# Classes and Objects

> Nhóm: Object Oriented Programming

## Mục tiêu

- Tạo class có field, constructor và method.
- Hiểu object identity và object state.
- Biết tạo nhiều object từ cùng một class.

## Lý thuyết dễ hiểu

Class mô tả dữ liệu và hành vi. Object là một instance cụ thể. Khi gọi `new Student(...)`, JVM cấp phát object, chạy constructor, rồi trả về reference.

Một class tốt nên có trách nhiệm rõ. `Student` quản lý thông tin sinh viên, không nên tự gửi email, tự đọc file và tự render HTML trong cùng một class.

## Facts cần nhớ

- Constructor chạy khi dùng `new`.
- Hai object có dữ liệu giống nhau vẫn có identity khác nhau nếu không override `equals`.
- `this` trỏ đến object hiện tại.

## Code mẫu

```java
public class Student {
    private final String studentCode;
    private String fullName;

    public Student(String studentCode, String fullName) {
        this.studentCode = studentCode;
        this.fullName = fullName;
    }

    public void rename(String newFullName) {
        if (newFullName == null || newFullName.isBlank()) {
            throw new IllegalArgumentException("Name must not be blank");
        }
        this.fullName = newFullName;
    }

    public String introduce() {
        return "Student " + fullName + " has code " + studentCode;
    }
}
```

## Cách triển khai thực tế

- Dùng class để gom dữ liệu và hành vi liên quan.
- Constructor là nơi kiểm tra dữ liệu bắt buộc.
- Method public là API nhỏ của object.

## Lỗi hay gặp

- Để field public rồi sửa lung tung.
- Constructor quá nhiều tham số không rõ nghĩa.
- Class quá lớn làm mọi thứ.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
