# SLF4J

> Nhóm: Logging Frameworks

## Mục tiêu

- Hiểu SLF4J là facade API.
- Biết parameterized logging.
- Dùng logger đúng cách.

## Lý thuyết dễ hiểu

SLF4J là API facade để code không phụ thuộc trực tiếp Logback/Log4j2. Bạn viết `LoggerFactory.getLogger(...)`, implementation phía sau quyết định ghi thế nào.

## Facts cần nhớ

- SLF4J không tự ghi log nếu không có implementation.
- Parameterized logging tránh nối chuỗi khi level tắt.
- Logger thường static final hoặc instance final.

## Code mẫu

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class StudentService {
    private static final Logger logger = LoggerFactory.getLogger(StudentService.class);

    public void enroll(String studentCode, String courseCode) {
        logger.info("Enrolling student {} to course {}", studentCode, courseCode);
        try {
            System.out.println("Saving enrollment");
        } catch (RuntimeException exception) {
            logger.error("Cannot enroll student {} to course {}", studentCode, courseCode, exception);
            throw exception;
        }
    }
}
```

## Cách triển khai thực tế

- Dùng `{}` placeholder thay nối chuỗi.
- Log exception bằng argument cuối.
- Không log password/token.

## Lỗi hay gặp

- `logger.error(exception.getMessage())` làm mất stack trace.
- Nối chuỗi trong debug log nặng.
- Dùng sai level.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
