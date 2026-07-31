# Log4j2

> Nhóm: Logging Frameworks

## Mục tiêu

- Biết Log4j2 là logging implementation.
- Hiểu async logging và configuration.
- Phân biệt facade SLF4J với implementation.

## Lý thuyết dễ hiểu

Log4j2 là framework logging mạnh, hỗ trợ async logger, nhiều appender và layout. Trong app, code nên gọi SLF4J để có thể đổi implementation nếu cần.

## Facts cần nhớ

- Log4j2 khác Log4j 1.x cũ.
- Có thể dùng qua SLF4J binding.
- Cần theo dõi security update của logging libraries.

## Code mẫu

```xml
<Configuration status="WARN">
    <Appenders>
        <Console name="Console" target="SYSTEM_OUT">
            <PatternLayout pattern="%d %-5p %c - %m%n"/>
        </Console>
    </Appenders>
    <Loggers>
        <Root level="info">
            <AppenderRef ref="Console"/>
        </Root>
    </Loggers>
</Configuration>
```

## Cách triển khai thực tế

- Dùng async logging khi throughput cao và đã đo lường.
- Giữ dependency logging cập nhật.
- Cấu hình pattern có request id/correlation id.

## Lỗi hay gặp

- Trộn nhiều binding logging gây warning.
- Không cập nhật version bảo mật.
- Log exception thiếu stack trace.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
