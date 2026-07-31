# Annotations

> Nhóm: Advanced Java

## Mục tiêu

- Hiểu annotation là metadata.
- Biết annotation dùng ở compile time/runtime.
- Biết ví dụ `@Override`, `@Deprecated`, Spring annotations.

## Lý thuyết dễ hiểu

Annotation gắn metadata lên class, method, field, parameter. Framework như Spring đọc annotation để tạo bean, map route, validate request.

Bạn không cần tự viết annotation sớm, nhưng cần hiểu annotation không phải logic trực tiếp. Nó là tín hiệu cho công cụ khác.

## Facts cần nhớ

- Annotation không tự làm gì nếu không có compiler/framework/reflection xử lý.
- `@Retention` quyết định annotation còn đến runtime không.
- `@Target` quyết định annotation đặt ở đâu.

## Code mẫu

```java
import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;

@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface Audited {
    String action();
}

public class UserService {
    @Audited(action = "CREATE_USER")
    public void createUser(String email) {
        System.out.println("Creating user " + email);
    }
}
```

## Cách triển khai thực tế

- Trong Spring, `@Service`, `@Repository`, `@RestController` giúp framework scan bean.
- Bean Validation dùng `@NotNull`, `@Size`, `@Email`.
- Annotation processor như Lombok tạo code lúc compile.

## Lỗi hay gặp

- Tưởng annotation tự chạy logic.
- Lạm dụng annotation làm code khó trace.
- Dùng reflection quét annotation trong hot path mà không cache.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
