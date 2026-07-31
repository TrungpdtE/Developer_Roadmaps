# Redis

> Nhóm: Databases  
> Mức ưu tiên: Personal must know

## Học để làm gì?

In-memory data store dùng cho cache, rate limit, queue nhẹ, session và distributed lock cẩn thận.

## Kiến thức cốt lõi

- Cache chỉ đúng khi bạn chấp nhận dữ liệu có thể cũ trong một khoảng thời gian.
- TTL, invalidation và key design quan trọng hơn việc gọi thư viện.
- Cache miss, cache penetration, cache stampede là lỗi production hay gặp.

## Facts cần nhớ

- Mức ưu tiên trong roadmap: **Personal must know**. Bắt buộc học nếu bạn muốn đi Java backend nghiêm túc.
- Nhóm học: **Databases**.
- Học bằng cách tự gõ lại ví dụ, tự đổi bài toán, rồi ghi chú lỗi gặp phải.
- Khi dùng trong production, luôn kiểm tra version, tài liệu chính thức, security advisory và compatibility với JDK/framework hiện tại.

## Ví dụ code hoặc cấu hình

```java
import com.github.benmanes.caffeine.cache.Cache;
import com.github.benmanes.caffeine.cache.Caffeine;

import java.time.Duration;

public class LocalCacheExample {
    private final Cache<String, String> courseTitleCache = Caffeine.newBuilder()
            .expireAfterWrite(Duration.ofMinutes(10))
            .maximumSize(10_000)
            .build();

    public String getCourseTitle(String courseCode) {
        return courseTitleCache.get(courseCode, this::loadCourseTitleFromDatabase);
    }

    private String loadCourseTitleFromDatabase(String courseCode) {
        return "Java Backend";
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

- `Redis Java official documentation`
- `Redis best practices Java`
- `Redis production pitfalls`
- `Redis Spring Boot integration`


[Quay lại roadmap](../README.md)
