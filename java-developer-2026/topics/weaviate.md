# Weaviate

> Nhóm: Databases  
> Mức ưu tiên: Personal must know

## Học để làm gì?

Vector database phục vụ semantic search và AI/RAG.

## Kiến thức cốt lõi

- Vector database lưu embedding để tìm kiếm theo độ tương đồng ngữ nghĩa.
- RAG cần chunking, embedding model, metadata filter và đánh giá chất lượng retrieval.
- Không đưa dữ liệu nhạy cảm vào vector store nếu chưa có chính sách bảo mật rõ.

## Facts cần nhớ

- Mức ưu tiên trong roadmap: **Personal must know**. Bắt buộc học nếu bạn muốn đi Java backend nghiêm túc.
- Nhóm học: **Databases**.
- Học bằng cách tự gõ lại ví dụ, tự đổi bài toán, rồi ghi chú lỗi gặp phải.
- Khi dùng trong production, luôn kiểm tra version, tài liệu chính thức, security advisory và compatibility với JDK/framework hiện tại.

## Ví dụ code hoặc cấu hình

```text
RAG pipeline:
1. Tách tài liệu thành chunks.
2. Tạo embedding cho từng chunk.
3. Lưu vector + metadata vào vector database.
4. Khi user hỏi, embed câu hỏi.
5. Tìm top-k chunks gần nhất.
6. Đưa context vào LLM để trả lời có căn cứ.
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

- `Weaviate Java official documentation`
- `Weaviate best practices Java`
- `Weaviate production pitfalls`
- `Weaviate Spring Boot integration`


[Quay lại roadmap](../README.md)
