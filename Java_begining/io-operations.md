# I/O Operations

> Nhóm: Advanced Java

## Mục tiêu

- Hiểu stream byte/char.
- Biết try-with-resources.
- Biết blocking I/O cơ bản.

## Lý thuyết dễ hiểu

I/O là nhập xuất dữ liệu: đọc file, ghi file, đọc network socket, nhận request. Java chia API theo byte stream và character stream.

Với text, luôn chỉ rõ charset như UTF-8 để tránh lỗi tiếng Việt.

## Facts cần nhớ

- InputStream/OutputStream xử lý byte.
- Reader/Writer xử lý character.
- Charset rất quan trọng khi đọc text.

## Code mẫu

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class IoDemo {
    public static void main(String[] arguments) throws IOException {
        Path path = Path.of("students.txt");

        try (BufferedReader reader = Files.newBufferedReader(path, StandardCharsets.UTF_8)) {
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
        }
    }
}
```

## Cách triển khai thực tế

- Dùng buffer khi đọc dữ liệu lớn.
- Đóng stream bằng try-with-resources.
- Tách parsing khỏi I/O để test dễ.

## Lỗi hay gặp

- Quên charset.
- Không đóng stream.
- Đọc toàn bộ file lớn vào memory không cần thiết.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
