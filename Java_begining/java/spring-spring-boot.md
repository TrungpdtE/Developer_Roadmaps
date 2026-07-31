# Spring (Spring Boot)

> Nhóm: Web Frameworks

## Mục tiêu

- Hiểu Spring IoC/DI.
- Biết Spring Boot auto-configuration.
- Tạo REST API cơ bản.

## Lý thuyết dễ hiểu

Spring là hệ sinh thái lớn cho DI, web, data, security. Spring Boot giúp cấu hình nhanh bằng auto-configuration và starter dependencies.

Luồng REST API thường là Controller -> Service -> Repository -> Database.

## Facts cần nhớ

- Spring Boot là lựa chọn phổ biến cho backend Java.
- Bean do Spring container quản lý.
- Annotation như `@RestController`, `@Service`, `@Repository` rất thường gặp.

## Code mẫu

```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
@RequestMapping("/api/students")
public class StudentController {
    private final StudentService studentService;

    public StudentController(StudentService studentService) {
        this.studentService = studentService;
    }

    @GetMapping("/{studentCode}")
    public StudentResponse findStudent(@PathVariable String studentCode) {
        return studentService.findStudent(studentCode);
    }
}
```

## Cách triển khai thực tế

- Học Java core trước Spring để hiểu annotation/DI/exception.
- Dùng Spring Initializr tạo project.
- Tách DTO, entity, service rõ ràng.

## Lỗi hay gặp

- Nhét business logic vào controller.
- Field injection.
- Không hiểu auto-configuration nên debug khó.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
