# Integration Testing

> Nhóm: Testing

## Mục tiêu

- Hiểu integration test kiểm tra nhiều thành phần phối hợp.
- Biết test database/API thật hơn unit test.
- Biết tradeoff chậm nhưng tự tin hơn.

## Lý thuyết dễ hiểu

Integration test kiểm tra đường đi qua nhiều layer: controller-service-repository-database, hoặc service gọi message broker. Nó bắt lỗi wiring/config/query mà unit test không thấy.

## Facts cần nhớ

- Integration test thường chậm hơn unit test.
- Testcontainers rất hữu ích để chạy dependency thật.
- Spring Boot có `@SpringBootTest`.

## Code mẫu

```java
import org.junit.jupiter.api.Test;
import org.springframework.boot.test.context.SpringBootTest;

@SpringBootTest
class ApplicationContextTest {
    @Test
    void applicationContextShouldStart() {
    }
}
```

## Cách triển khai thực tế

- Dùng database test riêng hoặc container.
- Reset dữ liệu giữa test.
- Chỉ viết integration test cho flow quan trọng để giữ thời gian chạy hợp lý.

## Lỗi hay gặp

- Dùng chung database dev làm test flaky.
- Test quá chậm không ai chạy.
- Không kiểm soát dữ liệu seed.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
