# TinyLog

> Nhóm: Logging Frameworks

## Mục tiêu

- Biết TinyLog là logging framework nhẹ.
- Hiểu dùng cho app nhỏ/tool.
- Biết khác với hệ sinh thái SLF4J phổ biến.

## Lý thuyết dễ hiểu

TinyLog cung cấp API logging gọn, cấu hình đơn giản. Nếu bạn làm app nhỏ hoặc tool học tập, nó dễ bắt đầu. Nếu dự án dùng Spring Boot, thường bạn sẽ gặp SLF4J/Logback trước.

## Facts cần nhớ

- TinyLog hướng đơn giản.
- Có thể phù hợp CLI/tool nhỏ.
- Trong enterprise Java, SLF4J + Logback/Log4j2 phổ biến hơn.

## Code mẫu

```java
import org.tinylog.Logger;

public class TinyLogDemo {
    public static void main(String[] arguments) {
        Logger.info("Application started");
        Logger.warn("This is a warning");
    }
}
```

## Cách triển khai thực tế

- Chọn logging stack theo project.
- Đồng nhất một logging approach trong repo.
- Cấu hình output phù hợp môi trường.

## Lỗi hay gặp

- Trộn quá nhiều logging framework.
- Không biết log đi đâu.
- Không đặt level theo môi trường.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
