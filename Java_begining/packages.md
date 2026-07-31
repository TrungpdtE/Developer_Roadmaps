# Packages

> Nhóm: Object Oriented Programming

## Mục tiêu

- Biết package tổ chức namespace.
- Hiểu import và fully qualified name.
- Biết cấu trúc package theo feature/layer.

## Lý thuyết dễ hiểu

Package giúp tránh trùng tên class và tổ chức code. Trong app backend, bạn thường gặp package theo layer như `controller`, `service`, `repository`, hoặc theo feature như `order`, `payment`, `user`.

Theo feature thường dễ bảo trì khi app lớn vì code cùng nghiệp vụ nằm gần nhau.

## Facts cần nhớ

- Package thường viết chữ thường: `com.example.project`.
- Thư mục source phải khớp package trong build chuẩn.
- `java.lang` được import mặc định.

## Code mẫu

```java
package com.example.school.student;

import java.time.LocalDate;

public class StudentProfile {
    private final String studentCode;
    private final LocalDate birthDate;

    public StudentProfile(String studentCode, LocalDate birthDate) {
        this.studentCode = studentCode;
        this.birthDate = birthDate;
    }
}
```

Cấu trúc thư mục Maven/Gradle thường là:

```text
src/main/java/com/example/school/student/StudentProfile.java
src/test/java/com/example/school/student/StudentProfileTest.java
```

## Cách triển khai thực tế

- Package theo feature: `order`, `payment`, `inventory`.
- Package theo layer phù hợp dự án nhỏ hoặc team quen MVC.
- Không để mọi class trong package gốc.

## Lỗi hay gặp

- Tên package có chữ hoa.
- Import wildcard quá nhiều làm khó biết class đến từ đâu.
- Package vòng phụ thuộc nhau.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
