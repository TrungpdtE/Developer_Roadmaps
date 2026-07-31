# Hibernate

> Nhóm: Database Access

## Mục tiêu

- Hiểu Hibernate là ORM phổ biến và implementation JPA.
- Biết entity, session/persistence context, lazy loading.
- Biết N+1 problem.

## Lý thuyết dễ hiểu

Hibernate map class/entity sang table/row. Nó giảm JDBC boilerplate nhưng thêm complexity: persistence context, dirty checking, lazy loading, cascade.

## Facts cần nhớ

- Hibernate triển khai JPA nhưng có extension riêng.
- Entity cần identity rõ.
- Lazy loading cần transaction/session còn mở.

## Code mẫu

```java
import jakarta.persistence.Entity;
import jakarta.persistence.GeneratedValue;
import jakarta.persistence.Id;
import jakarta.persistence.Table;

@Entity
@Table(name = "students")
public class StudentEntity {
    @Id
    @GeneratedValue
    private Long id;

    private String studentCode;
    private String fullName;

    protected StudentEntity() {
    }

    public StudentEntity(String studentCode, String fullName) {
        this.studentCode = studentCode;
        this.fullName = fullName;
    }
}
```

## Cách triển khai thực tế

- Hiểu entity lifecycle: transient, managed, detached, removed.
- Dùng fetch join/entity graph khi cần tránh N+1.
- Giữ transaction boundary rõ.

## Lỗi hay gặp

- Expose entity trực tiếp ra API.
- Cascade bừa bãi xóa dữ liệu.
- Không hiểu lazy loading nên lỗi ngoài transaction.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
