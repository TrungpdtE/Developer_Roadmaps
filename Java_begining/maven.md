# Maven

> Nhóm: Build Tools

## Mục tiêu

- Hiểu Maven quản lý dependency/build/test/package.
- Biết `pom.xml`.
- Chạy lifecycle cơ bản.

## Lý thuyết dễ hiểu

Maven giúp dự án không phụ thuộc vào IDE. Nó tải thư viện, compile, chạy test, đóng gói theo lifecycle chuẩn.

## Facts cần nhớ

- Maven dùng convention over configuration.
- `mvn test` chạy test.
- `mvn package` tạo artifact như jar.

## Code mẫu

```xml
<project>
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>java-roadmap-demo</artifactId>
    <version>1.0.0</version>

    <properties>
        <maven.compiler.release>25</maven.compiler.release>
    </properties>
</project>
```

```bash
mvn test
mvn package
java -jar target/java-roadmap-demo-1.0.0.jar
```

## Cách triển khai thực tế

- Dùng Maven wrapper `./mvnw` trong dự án thật.
- Khóa version dependency rõ ràng.
- Đọc dependency tree khi xung đột thư viện.

## Lỗi hay gặp

- Chỉ chạy bằng IDE nên lên CI lỗi.
- Không hiểu scope dependency.
- Commit thư mục `target`.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
