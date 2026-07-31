# Project tổng hợp: Student Enrollment Platform

Project này nối các nhánh roadmap thành một backend ASP.NET Core đủ chất đi làm.

## Chức năng

- Admin tạo sinh viên.
- Admin tạo môn học và sức chứa.
- Sinh viên đăng ký môn.
- Không cho đăng ký trùng.
- Không cho đăng ký khi môn đầy.
- Gửi event khi đăng ký thành công.
- Có logs, tests, database, cache và CI.

## Stack đề xuất

- .NET 10 LTS.
- ASP.NET Core Minimal APIs.
- EF Core.
- PostgreSQL hoặc SQL Server.
- FluentValidation.
- Serilog + Seq.
- xUnit + FluentAssertions.
- Testcontainers.
- RabbitMQ + MassTransit.
- Docker.
- GitHub Actions.

## API

```text
POST   /api/students
GET    /api/students/{studentCode}
POST   /api/courses
GET    /api/courses/{courseCode}
POST   /api/enrollments
GET    /api/students/{studentCode}/enrollments
```

## Entity mẫu

```csharp
public sealed class Student
{
    public long Id { get; private set; }
    public string StudentCode { get; private set; }
    public string FullName { get; private set; }

    private Student()
    {
        StudentCode = string.Empty;
        FullName = string.Empty;
    }

    public Student(string studentCode, string fullName)
    {
        if (string.IsNullOrWhiteSpace(studentCode))
        {
            throw new ArgumentException("Student code is required.", nameof(studentCode));
        }

        if (string.IsNullOrWhiteSpace(fullName))
        {
            throw new ArgumentException("Full name is required.", nameof(fullName));
        }

        StudentCode = studentCode.Trim();
        FullName = fullName.Trim();
    }
}
```

## Minimal API mẫu

```csharp
app.MapPost("/api/students", async (
    CreateStudentRequest request,
    IStudentService studentService,
    CancellationToken cancellationToken) =>
{
    StudentResponse response = await studentService.CreateAsync(request, cancellationToken);
    return Results.Created($"/api/students/{response.StudentCode}", response);
});

public sealed record CreateStudentRequest(string StudentCode, string FullName);
public sealed record StudentResponse(string StudentCode, string FullName);
```

## Test bắt buộc

- `CreateStudent_ShouldReturnCreated_WhenRequestIsValid`
- `CreateStudent_ShouldReturnValidationProblem_WhenStudentCodeIsBlank`
- `Enroll_ShouldRejectDuplicateEnrollment`
- `Enroll_ShouldRejectWhenCourseIsFull`
- `EnrollmentConsumer_ShouldIgnoreDuplicateEvent`
- `Database_ShouldPersistEnrollment`

## Production checklist

- Có ProblemDetails/error response thống nhất.
- Có validation cho request.
- Có cancellation token trong async API.
- Có migration versioned.
- Có structured logging.
- Không log secrets/token/password.
- Có health check.
- Có unit và integration tests.
- Có Dockerfile.
- Có CI chạy `dotnet test`.

[Quay lại README](README.md)
