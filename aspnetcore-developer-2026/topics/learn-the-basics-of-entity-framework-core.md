# Learn the basics of Entity Framework Core

> Nhóm: ORM  
> Mức: Must know

## Học để làm gì?

Nắm DbContext, entity, relationship, query LINQ, SaveChanges và transaction.

## Kiến thức cốt lõi

- DbContext là unit of work và identity map trong EF Core.
- LINQ query được dịch sang SQL; không phải mọi C# expression đều dịch được.
- Migrations phải được version-control và review như code.

## Facts cần nhớ

- Mức trong roadmap: **Must know**. Bắt buộc học nếu mục tiêu là đi ASP.NET Core backend nghiêm túc.
- Nhóm học: **ORM**.
- Với .NET/C# version, luôn kiểm tra `dotnet --info`, target framework và official docs của Microsoft.
- Học bằng cách tự gõ lại ví dụ, sửa sang bài toán riêng và viết test kiểm chứng.

## Ví dụ code hoặc cấu hình

```csharp
public sealed class StudentEntity
{
    public long Id { get; set; }
    public required string StudentCode { get; set; }
    public required string FullName { get; set; }
}

StudentEntity? student = await dbContext.Students
    .SingleOrDefaultAsync(student => student.StudentCode == "S001", cancellationToken);
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

- `Learn the basics of Entity Framework Core ASP.NET Core`
- `Learn the basics of Entity Framework Core .NET official documentation`
- `Learn the basics of Entity Framework Core production best practices`
- `Learn the basics of Entity Framework Core testing .NET`

[Quay lại roadmap](../README.md)
