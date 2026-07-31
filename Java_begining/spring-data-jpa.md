# Spring Data JPA

> Nhóm: Database Access

## Mục tiêu

- Biết repository abstraction.
- Tạo query từ method name.
- Hiểu nó dùng JPA/Hibernate phía dưới.

## Lý thuyết dễ hiểu

Spring Data JPA giảm boilerplate repository. Bạn khai báo interface, Spring tạo implementation runtime.

## Facts cần nhớ

- `JpaRepository` cung cấp CRUD sẵn.
- Method name query tiện nhưng quá dài thì nên viết `@Query`.
- Vẫn cần biết transaction và SQL.

## Code mẫu

```java
import org.springframework.data.jpa.repository.JpaRepository;
import java.util.Optional;

public interface StudentRepository extends JpaRepository<StudentEntity, Long> {
    Optional<StudentEntity> findByStudentCode(String studentCode);
    boolean existsByStudentCode(String studentCode);
}
```

## Cách triển khai thực tế

- Dùng DTO projection khi không cần load entity đầy đủ.
- Viết integration test cho repository query.
- Bật SQL log khi học để hiểu query sinh ra.

## Lỗi hay gặp

- Method name query dài khó đọc.
- Không phân trang query list lớn.
- Tưởng repository thay thế hoàn toàn hiểu biết SQL.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
