# Logback

> Nhóm: Logging Frameworks

## Mục tiêu

- Biết Logback là implementation logging phổ biến.
- Cấu hình appender/pattern/level.
- Hiểu Spring Boot mặc định dùng Logback trong nhiều setup.

## Lý thuyết dễ hiểu

Logback ghi log ra console/file/remote appender. Trong Spring Boot, bạn thường cấu hình qua `application.yml` hoặc `logback-spring.xml`.

## Facts cần nhớ

- Logback thường đi với SLF4J.
- Log level gồm TRACE, DEBUG, INFO, WARN, ERROR.
- Cấu hình sai có thể log quá nhiều hoặc quá ít.

## Code mẫu

```xml
<configuration>
    <appender name="CONSOLE" class="ch.qos.logback.core.ConsoleAppender">
        <encoder>
            <pattern>%d{yyyy-MM-dd HH:mm:ss} %-5level %logger{36} - %msg%n</pattern>
        </encoder>
    </appender>

    <root level="INFO">
        <appender-ref ref="CONSOLE" />
    </root>
</configuration>
```

## Cách triển khai thực tế

- Dùng INFO cho event nghiệp vụ quan trọng.
- Dùng DEBUG khi cần điều tra.
- Cấu hình rolling file nếu ghi file.

## Lỗi hay gặp

- Log dữ liệu nhạy cảm.
- Dùng System.out trong backend production.
- Đặt root DEBUG ở production lâu dài.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
