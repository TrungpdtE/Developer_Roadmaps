# GitHub Actions

> Nhóm: CI/CD  
> Mức: Must know

## Học để làm gì?

CI/CD phổ biến cho repo GitHub.

## Kiến thức cốt lõi

- CI phải chạy restore, build, test và optional static analysis/security scan.
- CD cần environment config, migration strategy, rollback và approval khi cần.
- Pipeline phải reproducible; tránh bước thủ công không ghi lại.

## Facts cần nhớ

- Mức trong roadmap: **Must know**. Bắt buộc học nếu mục tiêu là đi ASP.NET Core backend nghiêm túc.
- Nhóm học: **CI/CD**.
- Với .NET/C# version, luôn kiểm tra `dotnet --info`, target framework và official docs của Microsoft.
- Học bằng cách tự gõ lại ví dụ, sửa sang bài toán riêng và viết test kiểm chứng.

## Ví dụ code hoặc cấu hình

```yaml
name: build

on:
  push:
    branches: [ main ]
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-dotnet@v4
        with:
          dotnet-version: '10.0.x'
      - run: dotnet test --configuration Release
```

## Cách triển khai thực tế

- Bắt đầu bằng ví dụ nhỏ chạy được bằng `dotnet` CLI trước khi đưa vào solution lớn.
- Viết README ngắn cho cách chạy, cách test, biến môi trường và dependency cần có.
- Tách request/response DTO, domain model, persistence model khi boundary bắt đầu phức tạp.
- Với network/database/cache/message broker, luôn có timeout, cancellation token, retry hợp lý và log đủ context.
- Viết test cho happy path, lỗi input, case biên và failure mode quan trọng.

## Lỗi hay gặp

- Học thuộc API nhưng không hiểu vấn đề công nghệ đó giải quyết.
- Copy code nhưng không hiểu package, namespace, lifetime, async flow hoặc version.
- Đưa công nghệ vào project chỉ vì roadmap có, không kiểm tra use case thật.
- Bỏ qua cancellation token, timeout, duplicate request, retry và partial failure.
- Không chạy test bằng CLI nên CI/CD dễ fail dù IDE chạy được.

## Checklist tự học

1. Giải thích chủ đề này bằng 5 câu của bạn.
2. Gõ lại ví dụ trong file này.
3. Sửa ví dụ sang bài toán sinh viên, khóa học, đăng ký môn hoặc đơn hàng.
4. Tạo một lỗi cố ý rồi đọc compile/runtime exception.
5. Viết ít nhất một unit test hoặc integration test nhỏ.
6. Ghi rõ khi nào nên dùng và khi nào không nên dùng chủ đề này.

## Từ khóa tra cứu thêm

- `GitHub Actions ASP.NET Core`
- `GitHub Actions .NET official documentation`
- `GitHub Actions production best practices`
- `GitHub Actions testing .NET`

[Quay lại roadmap](../README.md)
