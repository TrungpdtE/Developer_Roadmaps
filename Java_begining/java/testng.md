# TestNG

> Nhóm: Testing

## Mục tiêu

- Biết TestNG là test framework khác JUnit.
- Hiểu annotation và suite.
- Biết khi nào gặp trong dự án cũ/enterprise.

## Lý thuyết dễ hiểu

TestNG từng phổ biến nhờ suite, group, dependency, data provider. Nếu project dùng TestNG, cú pháp tương tự JUnit nhưng annotation/package khác.

## Facts cần nhớ

- TestNG hỗ trợ grouping/dependency test mạnh.
- JUnit phổ biến hơn trong nhiều dự án hiện đại.
- Không cần học sâu cả hai ngay từ đầu.

## Code mẫu

```java
import org.testng.Assert;
import org.testng.annotations.Test;

public class CalculatorTestNgTest {
    @Test
    public void addShouldReturnSum() {
        Calculator calculator = new Calculator();
        Assert.assertEquals(calculator.add(2, 3), 5);
    }
}
```

## Cách triển khai thực tế

- Học JUnit trước nếu không có yêu cầu cụ thể.
- Đọc test framework đang dùng trong project.
- Không mix framework nếu team không thống nhất.

## Lỗi hay gặp

- Import nhầm annotation JUnit/TestNG.
- Test phụ thuộc nhau quá nhiều.
- Suite XML phức tạp khó bảo trì.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
