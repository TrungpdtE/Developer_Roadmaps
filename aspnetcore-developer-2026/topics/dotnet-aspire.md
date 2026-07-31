# .NET Aspire

> Nhóm: Microservices  
> Mức: Good to know

## Học để làm gì?

Stack của Microsoft cho cloud-native/distributed app local development, orchestration và observability.

## Kiến thức cốt lõi

- Microservices chỉ đáng dùng khi cần deploy/scale/team ownership độc lập.
- Distributed system thêm lỗi network, consistency, tracing, versioning.
- Modular monolith tốt thường là bước đầu thực tế hơn cho sinh viên/project nhỏ.

## Facts cần nhớ

- Mức trong roadmap: **Good to know**. Nên biết để đọc codebase, chọn công nghệ và mở rộng kỹ năng sau nền tảng.
- Nhóm học: **Microservices**.
- Với .NET/C# version, luôn kiểm tra `dotnet --info`, target framework và official docs của Microsoft.
- Học bằng cách tự gõ lại ví dụ, sửa sang bài toán riêng và viết test kiểm chứng.

## Ví dụ code hoặc cấu hình

```text
Suggested service boundaries:
- Student service owns students.
- Course service owns courses.
- Enrollment service owns enrollments.
- Notification service consumes enrollment events.
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

- `.NET Aspire ASP.NET Core`
- `.NET Aspire .NET official documentation`
- `.NET Aspire production best practices`
- `.NET Aspire testing .NET`

[Quay lại roadmap](../README.md)
