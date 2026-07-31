# Learn the basics of C# 14

> Nhóm: C# and .NET Prerequisites  
> Mức: Must know

## Học để làm gì?

Nắm cú pháp C# hiện đại theo .NET 10, nhưng vẫn hiểu codebase cũ dùng C# 10/11/12/13.

## Kiến thức cốt lõi

- Nắm type system: value type, reference type, nullable reference type, generics.
- Hiểu OOP trong C#: class, interface, record, inheritance, composition.
- Dùng LINQ và async/await đúng cách; không block async bằng `.Result`/`.Wait()` trong web app.

## Facts cần nhớ

- Mức trong roadmap: **Must know**. Bắt buộc học nếu mục tiêu là đi ASP.NET Core backend nghiêm túc.
- Nhóm học: **C# and .NET Prerequisites**.
- Với .NET/C# version, luôn kiểm tra `dotnet --info`, target framework và official docs của Microsoft.
- Học bằng cách tự gõ lại ví dụ, sửa sang bài toán riêng và viết test kiểm chứng.

## Ví dụ code hoặc cấu hình

```csharp
public sealed record StudentDto(string StudentCode, string FullName);

public sealed class StudentService
{
    private readonly List<StudentDto> students = new();

    public void AddStudent(string studentCode, string fullName)
    {
        if (string.IsNullOrWhiteSpace(studentCode))
        {
            throw new ArgumentException("Student code is required.", nameof(studentCode));
        }

        students.Add(new StudentDto(studentCode.Trim(), fullName.Trim()));
    }

    public IReadOnlyList<StudentDto> GetStudents()
    {
        return students.AsReadOnly();
    }
}
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

- `Learn the basics of C# 14 ASP.NET Core`
- `Learn the basics of C# 14 .NET official documentation`
- `Learn the basics of C# 14 production best practices`
- `Learn the basics of C# 14 testing .NET`

[Quay lại roadmap](../README.md)
