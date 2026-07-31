# JUnit

> Nhóm: Testing

## Mục tiêu

- Dùng JUnit 5.
- Biết `@Test`, assertions, lifecycle.
- Biết parameterized test cơ bản.

## Lý thuyết dễ hiểu

JUnit là framework test phổ biến nhất trong Java. Hầu hết build tool và IDE hỗ trợ rất tốt.

## Facts cần nhớ

- JUnit 5 gồm Platform, Jupiter, Vintage.
- `@BeforeEach` chạy trước mỗi test.
- Assertions nằm trong `org.junit.jupiter.api.Assertions`.

## Code mẫu

```java
import org.junit.jupiter.params.ParameterizedTest;
import org.junit.jupiter.params.provider.ValueSource;

import static org.junit.jupiter.api.Assertions.assertTrue;

class PasswordValidatorTest {
    @ParameterizedTest
    @ValueSource(strings = {"abc12345", "java2026"})
    void shouldAcceptPasswordWithAtLeastEightCharacters(String password) {
        assertTrue(password.length() >= 8);
    }
}
```

## Cách triển khai thực tế

- Dùng display name khi test phức tạp.
- Dùng parameterized test để tránh lặp.
- Chạy test bằng Maven/Gradle trên CI.

## Lỗi hay gặp

- Mix JUnit 4 và 5 không hiểu runner.
- Test tên mơ hồ.
- Không đọc failure message.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
