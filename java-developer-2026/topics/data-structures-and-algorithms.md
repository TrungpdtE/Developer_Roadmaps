# Data Structures and Algorithms

> Nhóm: General Development Skills  
> Mức ưu tiên: Personal must know

## Học để làm gì?

Biết chọn cấu trúc dữ liệu và phân tích độ phức tạp để code không chậm bất ngờ.

## Kiến thức cốt lõi

- Big-O giúp dự đoán code chạy ra sao khi dữ liệu tăng.
- Array/List, Map, Set, Queue, Stack là nền tảng trước khi học thuật toán phức tạp.
- Chọn cấu trúc dữ liệu sai có thể làm API chậm dù code nhìn đơn giản.

## Facts cần nhớ

- Mức ưu tiên trong roadmap: **Personal must know**. Bắt buộc học nếu bạn muốn đi Java backend nghiêm túc.
- Nhóm học: **General Development Skills**.
- Học bằng cách tự gõ lại ví dụ, tự đổi bài toán, rồi ghi chú lỗi gặp phải.
- Khi dùng trong production, luôn kiểm tra version, tài liệu chính thức, security advisory và compatibility với JDK/framework hiện tại.

## Ví dụ code hoặc cấu hình

```java
import java.util.HashMap;
import java.util.List;
import java.util.Map;

public class FrequencyCounter {
    public static Map<String, Integer> countWords(List<String> words) {
        Map<String, Integer> frequencyByWord = new HashMap<>();
        for (String word : words) {
            int currentCount = frequencyByWord.getOrDefault(word, 0);
            frequencyByWord.put(word, currentCount + 1);
        }
        return frequencyByWord;
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

- `Data Structures and Algorithms Java official documentation`
- `Data Structures and Algorithms best practices Java`
- `Data Structures and Algorithms production pitfalls`
- `Data Structures and Algorithms Spring Boot integration`


[Quay lại roadmap](../README.md)
