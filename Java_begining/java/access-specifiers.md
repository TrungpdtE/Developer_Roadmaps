# Access Specifiers

> Nhóm: Object Oriented Programming

## Mục tiêu

- Nắm `public`, `protected`, package-private và `private`.
- Biết giảm bề mặt API public.
- Hiểu đóng gói trong package.

## Lý thuyết dễ hiểu

Access specifier quyết định ai được gọi field/method/class. Nguyên tắc thực tế: bắt đầu chặt nhất có thể, mở rộng khi có nhu cầu thật.

Public API khó thay đổi vì code bên ngoài có thể phụ thuộc vào nó. Private implementation dễ refactor hơn.

## Facts cần nhớ

- Không ghi modifier nghĩa là package-private.
- `private` chỉ dùng trong cùng class.
- `protected` cho subclass và cùng package, không chỉ subclass.

## Code mẫu

```java
package university;

public class Course {
    private final String courseCode;
    private String title;

    public Course(String courseCode, String title) {
        this.courseCode = courseCode;
        this.title = title;
    }

    public String getCourseCode() {
        return courseCode;
    }

    void renameInsidePackage(String newTitle) {
        this.title = newTitle;
    }

    private boolean hasValidTitle() {
        return title != null && !title.isBlank();
    }
}
```

## Cách triển khai thực tế

- Trong thư viện, public method là contract.
- Trong app, package-private rất hữu ích cho helper nội bộ.
- Private method giúp chia nhỏ logic nhưng không nên test trực tiếp.

## Lỗi hay gặp

- Dùng public cho mọi thứ.
- Lạm dụng protected làm kế thừa rối.
- Tưởng package-private truy cập được từ package con.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
