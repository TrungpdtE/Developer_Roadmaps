# Date and Time

> Nhóm: Advanced Java

## Mục tiêu

- Dùng `java.time`.
- Phân biệt `Instant`, `LocalDate`, `LocalDateTime`, `ZonedDateTime`.
- Biết timezone và format.

## Lý thuyết dễ hiểu

Date/time là nguồn lỗi lớn vì timezone, daylight saving, format theo locale. API `java.time` hiện đại immutable và rõ nghĩa hơn `Date`/`Calendar`.

Chọn kiểu:

- Ngày sinh: `LocalDate`.
- Thời điểm xảy ra event: `Instant`.
- Lịch theo timezone cụ thể: `ZonedDateTime`.
- Khoảng thời gian: `Duration` hoặc `Period`.

## Facts cần nhớ

- `java.time` xuất hiện từ Java 8.
- `LocalDateTime` không có timezone.
- Lưu mốc thời gian tuyệt đối nên dùng `Instant`.

## Code mẫu

```java
import java.time.Instant;
import java.time.LocalDate;
import java.time.ZoneId;
import java.time.ZonedDateTime;
import java.time.format.DateTimeFormatter;

public class DateTimeDemo {
    public static void main(String[] arguments) {
        LocalDate birthDate = LocalDate.of(2004, 5, 20);
        Instant createdAt = Instant.now();
        ZonedDateTime vietnamTime = createdAt.atZone(ZoneId.of("Asia/Ho_Chi_Minh"));

        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm");
        System.out.println(birthDate);
        System.out.println(vietnamTime.format(formatter));
    }
}
```

## Cách triển khai thực tế

- API response nên thống nhất timezone/format.
- Database thường lưu timestamp UTC.
- Inject `Clock` khi test logic thời gian.

## Lỗi hay gặp

- Dùng `LocalDateTime` cho event toàn cầu rồi mất timezone.
- Parse date không chỉ rõ format.
- Tự cộng milliseconds thay vì dùng `Duration`/`Period`.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
