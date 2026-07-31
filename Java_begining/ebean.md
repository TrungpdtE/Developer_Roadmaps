# EBean

> Nhóm: Database Access

## Mục tiêu

- Biết EBean là ORM cho Java.
- Hiểu entity/query ở mức khái niệm.
- Biết nó là lựa chọn ít phổ biến hơn JPA/Hibernate trong nhiều dự án.

## Lý thuyết dễ hiểu

EBean là ORM giúp map object Java với bảng database. Bạn làm việc với entity thay vì viết toàn bộ JDBC thủ công.

## Facts cần nhớ

- EBean cố gắng đơn giản hóa ORM.
- Có query bean/type-safe query tùy setup.
- Nên học JDBC/JPA trước để có nền.

## Code mẫu

```java
import io.ebean.Model;
import jakarta.persistence.Entity;
import jakarta.persistence.Id;

@Entity
public class Student extends Model {
    @Id
    private Long id;

    private String studentCode;
    private String fullName;
}
```

## Cách triển khai thực tế

- Chỉ học sâu nếu dự án dùng EBean.
- Vẫn cần hiểu transaction và lazy loading.
- Đọc SQL generated để tránh query tệ.

## Lỗi hay gặp

- Tưởng ORM loại bỏ nhu cầu biết SQL.
- Entity phình to chứa mọi logic.
- N+1 query.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
