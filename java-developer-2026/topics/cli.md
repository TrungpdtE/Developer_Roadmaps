# CLI

> Nhóm: CLI  
> Mức ưu tiên: Personal must know

## Học để làm gì?

Tạo command-line app trong Java để chạy tool, batch job, script nội bộ.

## Kiến thức cốt lõi

- CLI app cần input rõ, output rõ, exit code rõ.
- Không in stack trace thô cho người dùng cuối; log chi tiết nếu cần.
- Config nên nhận từ argument, environment variable hoặc file config.

## Facts cần nhớ

- Mức ưu tiên trong roadmap: **Personal must know**. Bắt buộc học nếu bạn muốn đi Java backend nghiêm túc.
- Nhóm học: **CLI**.
- Học bằng cách tự gõ lại ví dụ, tự đổi bài toán, rồi ghi chú lỗi gặp phải.
- Khi dùng trong production, luôn kiểm tra version, tài liệu chính thức, security advisory và compatibility với JDK/framework hiện tại.

## Ví dụ code hoặc cấu hình

```java
public class SimpleCli {
    public static void main(String[] arguments) {
        if (arguments.length == 0) {
            System.err.println("Usage: java SimpleCli <name>");
            System.exit(1);
        }

        String name = arguments[0];
        System.out.println("Hello " + name);
    }
}
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

- `CLI Java official documentation`
- `CLI best practices Java`
- `CLI production pitfalls`
- `CLI Spring Boot integration`


[Quay lại roadmap](../README.md)
