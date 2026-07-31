# Bazel

> Nhóm: Build Tools

## Mục tiêu

- Biết Bazel mạnh cho monorepo build lớn.
- Hiểu target và dependency explicit.
- Biết Java rule cơ bản.

## Lý thuyết dễ hiểu

Bazel phù hợp repo lớn, nhiều ngôn ngữ, cần build/test nhanh và cache tốt. Với sinh viên hoặc app Spring nhỏ, Maven/Gradle dễ bắt đầu hơn.

## Facts cần nhớ

- Bazel chú trọng reproducible build.
- Dependency phải khai báo rõ.
- Không phổ biến bằng Maven/Gradle trong dự án Java nhỏ.

## Code mẫu

```python
java_library(
    name = "school",
    srcs = glob(["src/main/java/**/*.java"]),
)

java_test(
    name = "school_tests",
    srcs = glob(["src/test/java/**/*.java"]),
    deps = [":school"],
)
```

## Cách triển khai thực tế

- Học Bazel sau khi đã vững build cơ bản.
- Dùng khi team/repo có nhu cầu build lớn.
- Target nhỏ giúp cache hiệu quả.

## Lỗi hay gặp

- Dùng Bazel cho app nhỏ rồi tăng complexity.
- Khai báo thiếu dependency.
- Không hiểu sandbox build.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
