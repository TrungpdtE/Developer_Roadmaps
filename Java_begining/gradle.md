# Gradle

> Nhóm: Build Tools

## Mục tiêu

- Hiểu Gradle build bằng Groovy/Kotlin DSL.
- Biết task và plugin.
- Chạy test/package.

## Lý thuyết dễ hiểu

Gradle dùng build script để khai báo plugin, dependency và task. Kotlin DSL (`build.gradle.kts`) type-safe hơn Groovy DSL.

## Facts cần nhớ

- Gradle linh hoạt hơn Maven nhưng dễ cấu hình phức tạp.
- Gradle wrapper giúp team dùng cùng version.
- Spring Initializr hỗ trợ Maven và Gradle.

## Code mẫu

```kotlin
plugins {
    java
}

group = "com.example"
version = "1.0.0"

java {
    toolchain {
        languageVersion.set(JavaLanguageVersion.of(25))
    }
}

repositories {
    mavenCentral()
}

dependencies {
    testImplementation("org.junit.jupiter:junit-jupiter:5.11.0")
}

tasks.test {
    useJUnitPlatform()
}
```

## Cách triển khai thực tế

- Dùng `./gradlew test`.
- Giữ build script đơn giản.
- Dùng version catalog khi dự án lớn.

## Lỗi hay gặp

- Cấu hình task tùy biến quá sớm.
- Không commit gradle wrapper.
- Cache lỗi nhưng không biết clean.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
