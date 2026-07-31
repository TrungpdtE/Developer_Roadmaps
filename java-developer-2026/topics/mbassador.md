# mbassador

> Nhóm: MicroServices  
> Mức ưu tiên: Possibilities

## Học để làm gì?

Event bus library cho Java, chủ yếu cần biết nếu gặp codebase dùng nó.

## Kiến thức cốt lõi

- Microservice chỉ đáng dùng khi team và domain cần deploy/scale độc lập.
- Distributed system làm tăng complexity: network failure, eventual consistency, tracing, versioning.
- Bắt đầu modular monolith tốt thường thực tế hơn cho dự án nhỏ.

## Facts cần nhớ

- Mức ưu tiên trong roadmap: **Possibilities**. Biết tên, biết use case, học sâu khi dự án thật cần.
- Nhóm học: **MicroServices**.
- Học bằng cách tự gõ lại ví dụ, tự đổi bài toán, rồi ghi chú lỗi gặp phải.
- Khi dùng trong production, luôn kiểm tra version, tài liệu chính thức, security advisory và compatibility với JDK/framework hiện tại.

## Ví dụ code hoặc cấu hình

```text
Service boundary example:
- student-service owns students table.
- course-service owns courses table.
- enrollment-service owns enrollments table.
- Services communicate through REST/gRPC/events, not shared tables.
```

## Cách triển khai thực tế

- Bắt đầu bằng ví dụ nhỏ chạy được, sau đó mới đưa vào Spring/service lớn.
- Viết README ngắn trong project về cách chạy, cách test và các biến môi trường cần có.
- Với thư viện/framework, tạo một wrapper/service mỏng nếu bạn muốn giảm phụ thuộc trực tiếp trong toàn bộ codebase.
- Luôn có test cho happy path, input lỗi và case biên.
- Khi có network, database, cache hoặc message broker, luôn cấu hình timeout, retry hợp lý và log đủ context.

## Lỗi hay gặp

- Học thuộc API nhưng không hiểu vấn đề mà công nghệ đó giải quyết.
- Copy code mẫu nhưng không hiểu dependency, import, version và lifecycle.
- Dùng công nghệ vì thấy trong roadmap, không kiểm tra dự án có thật sự cần không.
- Bỏ qua failure mode: timeout, null, duplicate request, retry, partial failure, dữ liệu cũ.
- Không viết test nên refactor hoặc nâng version rất rủi ro.

## Checklist tự học

1. Giải thích chủ đề này trong 5 câu bằng lời của bạn.
2. Gõ lại ví dụ trong file này, không copy paste.
3. Sửa ví dụ sang bài toán sinh viên, khóa học, đăng ký môn hoặc đơn hàng.
4. Tạo ít nhất một lỗi cố ý rồi đọc lỗi compile/runtime.
5. Viết một test hoặc một script kiểm tra hành vi chính.
6. Ghi lại khi nào nên dùng và khi nào không nên dùng chủ đề này.

## Từ khóa tra cứu thêm

- `mbassador Java official documentation`
- `mbassador best practices Java`
- `mbassador production pitfalls`
- `mbassador Spring Boot integration`


[Quay lại roadmap](../README.md)
