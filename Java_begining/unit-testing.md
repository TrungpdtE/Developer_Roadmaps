# Unit Testing

> Nhóm: Testing

## Mục tiêu

- Hiểu unit test kiểm tra đơn vị nhỏ.
- Biết arrange-act-assert.
- Viết test nhanh, độc lập.

## Lý thuyết dễ hiểu

Unit test kiểm tra class/method nhỏ trong isolation. Nó giúp bạn refactor tự tin và phát hiện bug sớm.

## Facts cần nhớ

- Unit test không cần database thật.
- Test tốt đặt tên theo hành vi.
- Test phải deterministic.

## Code mẫu

```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.assertEquals;

class CalculatorTest {
    @Test
    void addShouldReturnSumOfTwoNumbers() {
        Calculator calculator = new Calculator();

        int result = calculator.add(2, 3);

        assertEquals(5, result);
    }
}

class Calculator {
    int add(int firstNumber, int secondNumber) {
        return firstNumber + secondNumber;
    }
}
```

## Cách triển khai thực tế

- Test rule nghiệp vụ trước.
- Không test private method trực tiếp.
- Giữ test readable như tài liệu.

## Lỗi hay gặp

- Test phụ thuộc thứ tự chạy.
- Test quá nhiều implementation detail.
- Không có assert thật.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
