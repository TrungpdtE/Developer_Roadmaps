# Scrum, Kanban or Other Project Strategies

> Nhóm: General Development Skills  
> Mức ưu tiên: Good to know

## Học để làm gì?

Hiểu cách team chia việc, theo dõi tiến độ, review và giao phần mềm theo sprint/flow.

## Kiến thức cốt lõi

- Scrum chia việc theo sprint; Kanban tối ưu flow liên tục.
- Definition of Done phải gồm code, test, review và deploy/document nếu cần.
- Ticket tốt có context, acceptance criteria và cách verify.

## Facts cần nhớ

- Mức ưu tiên trong roadmap: **Good to know**. Nên biết để đọc codebase/thảo luận kỹ thuật, học sau nhóm bắt buộc.
- Nhóm học: **General Development Skills**.
- Học bằng cách tự gõ lại ví dụ, tự đổi bài toán, rồi ghi chú lỗi gặp phải.
- Khi dùng trong production, luôn kiểm tra version, tài liệu chính thức, security advisory và compatibility với JDK/framework hiện tại.

## Ví dụ code hoặc cấu hình

```text
User story:
As a student
I want to enroll in an open course
So that I can attend the course this semester

Acceptance criteria:
- Given the course is open, when I enroll, then enrollment is created.
- Given the course is full, when I enroll, then I receive a clear error.
- Given I already enrolled, when I enroll again, then the system rejects duplicate enrollment.
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

- `Scrum, Kanban or Other Project Strategies Java official documentation`
- `Scrum, Kanban or Other Project Strategies best practices Java`
- `Scrum, Kanban or Other Project Strategies production pitfalls`
- `Scrum, Kanban or Other Project Strategies Spring Boot integration`


[Quay lại roadmap](../README.md)
