# Lộ trình học ASP.NET Core Developer 2026 theo tuần

Kế hoạch này dành cho sinh viên. Mỗi tuần nên có: 3 buổi đọc và gõ code, 2 buổi làm project, 1 buổi test/debug, 1 buổi ghi chú lỗi.

## Tuần 1-2: C# và .NET CLI

- Học C# 14, nullable, records, LINQ, async/await.
- Dùng `dotnet new`, `dotnet build`, `dotnet test`.
- Làm CLI quản lý sinh viên bằng List/Dictionary.

## Tuần 3: Git, HTTP, SQL

- Tạo repo Git, branch, PR giả lập.
- Học HTTP methods/status codes.
- Viết SQL tạo bảng students/courses/enrollments.

## Tuần 4: SOLID và DI

- Viết service nhỏ dùng constructor injection.
- Phân biệt scoped/transient/singleton.
- Viết unit test cho service.

## Tuần 5-6: ASP.NET Core API

- Tạo Minimal API hoặc Controller API.
- Thêm validation, ProblemDetails, exception handler.
- Thêm OpenAPI/Scalar.

## Tuần 7: EF Core và database

- Thêm DbContext, entity, migrations.
- Dùng PostgreSQL hoặc SQL Server.
- Học eager loading, tracking/no-tracking, transaction.

## Tuần 8: Testing nghiêm túc

- xUnit + FluentAssertions.
- Moq/NSubstitute cho dependency.
- WebApplicationFactory cho API tests.
- Testcontainers cho database thật.

## Tuần 9: Logging, caching, API clients

- Serilog + Seq.
- IMemoryCache, OutputCache.
- HttpClientFactory và retry/timeout.

## Tuần 10: Messaging và background jobs

- BackgroundService.
- RabbitMQ + MassTransit hoặc Kafka.
- Idempotent consumer và retry/DLQ.

## Tuần 11: Observability và CI/CD

- OpenTelemetry traces/metrics.
- GitHub Actions hoặc Azure Pipelines.
- Dockerfile và health checks.

## Tuần 12: Tổng hợp và review

- Viết README dự án.
- Kiểm tra security basic: auth, secrets, validation.
- Chạy full test suite.
- Viết phần “tradeoffs” cho các công nghệ đã dùng.

[Quay lại README](README.md)
