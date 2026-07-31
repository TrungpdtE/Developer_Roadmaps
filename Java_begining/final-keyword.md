# Final Keyword

> Nhóm: Object Oriented Programming

## Mục tiêu

- Hiểu final variable, final method, final class.
- Biết final với reference không làm object immutable.
- Dùng final để thể hiện ý định không gán lại.

## Lý thuyết dễ hiểu

`final` giúp khóa việc gán lại hoặc kế thừa. Với object, `final List<String> names` nghĩa là biến `names` không trỏ sang list khác, nhưng nội dung list vẫn có thể thay đổi nếu list mutable.

## Facts cần nhớ

- Final local variable chỉ không được gán lại.
- Final class không thể bị kế thừa.
- Final method không thể override.

## Code mẫu

```java
import java.util.ArrayList;
import java.util.List;

public final class Classroom {
    private final List<String> studentNames = new ArrayList<>();

    public void addStudent(String studentName) {
        studentNames.add(studentName);
    }

    public List<String> getStudentNamesSnapshot() {
        return List.copyOf(studentNames);
    }
}
```

## Cách triển khai thực tế

- Dùng final cho dependency được inject qua constructor.
- Trả về bản copy immutable để bảo vệ collection nội bộ.
- Final class hợp lý cho value object hoặc class không thiết kế để kế thừa.

## Lỗi hay gặp

- Tưởng final list là list immutable.
- Final quá mức làm khó test/mocking nếu thiết kế sai.
- Không hiểu khác biệt giữa final và immutability.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
