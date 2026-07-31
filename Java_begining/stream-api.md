# Stream API

> Nhóm: Functional Programming

## Mục tiêu

- Dùng stream để xử lý collection theo pipeline.
- Nắm intermediate và terminal operations.
- Biết khi nào loop thường tốt hơn.

## Lý thuyết dễ hiểu

Stream API giúp viết pipeline xử lý dữ liệu: lấy collection, lọc, biến đổi, gom kết quả. Nó hợp với logic dữ liệu tuyến tính và ít side effect.

## Facts cần nhớ

- Stream lazy cho đến terminal operation.
- `map` biến đổi, `filter` lọc, `collect` gom kết quả.
- Stream không phải luôn nhanh hơn loop.

## Code mẫu

```java
import java.util.List;

public class StreamApiDemo {
    public static void main(String[] arguments) {
        List<StudentScore> scores = List.of(
                new StudentScore("An", 8),
                new StudentScore("Binh", 5),
                new StudentScore("Chi", 9)
        );

        List<String> passedStudentNames = scores.stream()
                .filter(score -> score.value() >= 6)
                .map(StudentScore::studentName)
                .sorted()
                .toList();

        System.out.println(passedStudentNames);
    }
}

record StudentScore(String studentName, int value) {
}
```

## Cách triển khai thực tế

- Dùng stream cho filter/map/grouping.
- Dùng loop khi cần break phức tạp, nhiều side effect hoặc debug từng bước.
- Không mutate collection nguồn trong stream.

## Lỗi hay gặp

- Quên terminal operation nên stream không chạy.
- Dùng parallel stream bừa bãi.
- Stream quá dài không đặt biến trung gian.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
