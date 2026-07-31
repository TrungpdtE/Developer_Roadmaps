# Lộ trình học Java Developer 2026 theo tuần

Kế hoạch này dành cho sinh viên. Mỗi tuần nên có 3 buổi học lý thuyết, 2 buổi code lại ví dụ, 1 buổi làm project và 1 buổi review lỗi.

## Tuần 1-2: Java core và terminal

- Học Java CLI, biến, hằng, kiểu dữ liệu, method, package.
- Làm bài tập: viết CLI quản lý danh sách sinh viên bằng `ArrayList`.
- Bắt buộc tự chạy bằng terminal: `javac`, `java`, sau đó mới dùng IDE.
- Kết quả cần có: bạn giải thích được source code -> bytecode -> JVM.

## Tuần 3: OOP, interface, exception

- Học class, object, interface, exception handling.
- Làm bài tập: `Student`, `Course`, `EnrollmentService`.
- Viết custom exception: `CourseFullException`, `DuplicateEnrollmentException`.
- Kết quả cần có: service không in console lung tung, method trả dữ liệu hoặc throw exception rõ.

## Tuần 4: Git, HTTP, SQL

- Học Git branch/commit/merge, HTTP method/status/header/body, SQL CRUD.
- Làm bài tập: thiết kế bảng `students`, `courses`, `enrollments`.
- Kết quả cần có: một repo có README chạy được, có script SQL tạo schema.

## Tuần 5-6: Spring + REST API

- Tạo Spring Boot project.
- Xây controller/service/repository cho sinh viên và môn học.
- Học validation, exception handler, DTO request/response.
- Kết quả cần có: API `GET/POST/PUT/DELETE /api/students`.

## Tuần 7: Database + ORM

- Kết nối PostgreSQL hoặc H2 trước, sau đó PostgreSQL thật.
- Học Hibernate/JPA entity, relationship, transaction, repository.
- Thêm migration bằng Flyway hoặc Liquibase.
- Kết quả cần có: API lưu dữ liệu bền vững, restart app không mất dữ liệu.

## Tuần 8: Testing

- Unit test service bằng JUnit, AssertJ, Mockito.
- Integration test repository/API bằng Testcontainers.
- Mock API ngoài bằng WireMock.
- Kết quả cần có: `./mvnw test` hoặc `./gradlew test` chạy xanh.

## Tuần 9: Logging, cache, API client

- Thêm structured logging có request id.
- Thêm Caffeine cache cho course lookup.
- Viết API client gọi service giả bằng OkHttp hoặc WebClient.
- Kết quả cần có: đọc log biết request nào lỗi và lỗi ở bước nào.

## Tuần 10: Messaging và reliability

- Publish event `StudentEnrolled`.
- Consumer gửi email giả.
- Xử lý idempotency, retry, dead-letter idea.
- Kết quả cần có: consumer nhận trùng event vẫn không gửi email trùng.

## Tuần 11: Search hoặc realtime

- Chọn một: Elasticsearch/OpenSearch cho search course, hoặc WebSocket/SSE cho notification realtime.
- Kết quả cần có: hiểu khi nào cần công nghệ đó và khi nào không cần.

## Tuần 12: AI/LLM và tổng kết

- Làm RAG mini: upload tài liệu môn học, chunk, embedding, tìm context, hỏi đáp.
- Viết tài liệu kiến trúc cuối cùng.
- Kết quả cần có: project có README, test, logging, database, API docs và ghi chú tradeoff.

[Quay lại README](README.md)
