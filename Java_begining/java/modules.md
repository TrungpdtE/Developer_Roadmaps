# Modules

> Nhóm: Advanced Java

## Mục tiêu

- Hiểu Java Platform Module System.
- Biết `module-info.java`.
- Biết exports/requires.

## Lý thuyết dễ hiểu

Module là mức đóng gói cao hơn package. Nó giúp khai báo rõ dependency và package nào được public ra ngoài module.

Nhiều app Spring Boot vẫn chủ yếu dùng classpath thay vì module path, nhưng hiểu module giúp đọc JDK hiện đại và thiết kế thư viện tốt hơn.

## Facts cần nhớ

- JPMS xuất hiện từ Java 9.
- `requires` khai báo module phụ thuộc.
- `exports` mở package cho module khác dùng.

## Code mẫu

```java
// module-info.java
module com.example.school {
    requires java.sql;
    exports com.example.school.student;
}
```

```java
package com.example.school.student;

public class StudentApi {
    public String hello() {
        return "Hello from exported package";
    }
}
```

## Cách triển khai thực tế

- Dùng module khi xây thư viện hoặc app cần boundaries rõ.
- Không export package internal.
- JPMS khác Maven module; Maven module là cấu trúc build.

## Lỗi hay gặp

- Nhầm package với module.
- Export mọi package làm mất lợi ích.
- Đưa app framework phức tạp sang module mà chưa cần.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
