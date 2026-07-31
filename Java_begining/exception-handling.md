# Exception Handling

> Nhóm: Advanced Java

## Mục tiêu

- Hiểu checked và unchecked exception.
- Biết try-catch-finally và try-with-resources.
- Biết tạo custom exception có ý nghĩa.

## Lý thuyết dễ hiểu

Exception biểu diễn luồng lỗi. Lỗi dự kiến có thể xử lý thì catch gần nơi có đủ ngữ cảnh. Lỗi không xử lý được nên để bubble lên boundary như controller/filter để log và trả response phù hợp.

Try-with-resources tự đóng object implement `AutoCloseable`, rất quan trọng với file, stream, connection.

## Facts cần nhớ

- Checked exception phải catch hoặc declare.
- `RuntimeException` là unchecked.
- Không nuốt exception im lặng.

## Code mẫu

```java
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.util.List;

public class ExceptionDemo {
    public static List<String> readAllLines(Path filePath) {
        try {
            return Files.readAllLines(filePath);
        } catch (IOException exception) {
            throw new FileReadFailedException("Cannot read file: " + filePath, exception);
        }
    }
}

class FileReadFailedException extends RuntimeException {
    public FileReadFailedException(String message, Throwable cause) {
        super(message, cause);
    }
}
```

## Cách triển khai thực tế

- Log exception kèm context nhưng không lộ dữ liệu nhạy cảm.
- Custom exception nên nói lỗi domain, không chỉ kỹ thuật.
- Trong API, map exception sang HTTP status rõ ràng.

## Lỗi hay gặp

- Catch `Exception` quá rộng.
- In stack trace rồi tiếp tục như không có gì.
- Throw exception cho luồng điều kiện bình thường quá thường xuyên.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
