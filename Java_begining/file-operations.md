# File Operations

> Nhóm: Advanced Java

## Mục tiêu

- Dùng `java.nio.file.Files` và `Path`.
- Biết đọc/ghi file text.
- Biết kiểm tra tồn tại, tạo thư mục, duyệt file.

## Lý thuyết dễ hiểu

File operations trong Java hiện đại nên bắt đầu từ `Path` và `Files`. API này rõ ràng hơn `java.io.File` cũ, hỗ trợ nhiều thao tác như copy, move, walk, create directories.

## Facts cần nhớ

- `Path` hiện đại hơn `File` cho đa số thao tác.
- `Files.writeString` tiện cho file nhỏ.
- File operation có thể throw `IOException`.

## Code mẫu

```java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;
import java.util.List;

public class FileOperationsDemo {
    public static void main(String[] arguments) throws IOException {
        Path directory = Path.of("data");
        Files.createDirectories(directory);

        Path filePath = directory.resolve("students.txt");
        List<String> lines = List.of("An", "Binh", "Chi");
        Files.write(filePath, lines, StandardCharsets.UTF_8);

        List<String> loadedLines = Files.readAllLines(filePath, StandardCharsets.UTF_8);
        System.out.println(loadedLines);
    }
}
```

## Cách triển khai thực tế

- Validate path từ user để tránh path traversal.
- Với upload file, giới hạn size và loại file.
- Trong server, lưu file cần chiến lược backup và permission.

## Lỗi hay gặp

- Hard-code đường dẫn tuyệt đối.
- Ghi đè file quan trọng không backup.
- Không xử lý lỗi permission/disk full.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
