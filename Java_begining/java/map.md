# Map

> Nhóm: Collections

## Mục tiêu

- Hiểu key-value.
- Biết HashMap, LinkedHashMap, TreeMap.
- Biết `getOrDefault`, `computeIfAbsent`.

## Lý thuyết dễ hiểu

Map dùng để tra cứu theo key: userId -> user, productCode -> price, word -> count. Key phải có equals/hashCode ổn định.

## Facts cần nhớ

- Key trong Map là duy nhất.
- HashMap cho phép một null key.
- Map lookup trung bình nhanh với hash tốt.

## Code mẫu

```java
import java.util.HashMap;
import java.util.Map;

public class MapDemo {
    public static void main(String[] arguments) {
        Map<String, Integer> wordCounts = new HashMap<>();
        String[] words = {"java", "spring", "java"};

        for (String word : words) {
            int currentCount = wordCounts.getOrDefault(word, 0);
            wordCounts.put(word, currentCount + 1);
        }

        System.out.println(wordCounts);
    }
}
```

## Cách triển khai thực tế

- Dùng Map làm index tạm để tránh loop lồng nhau.
- Dùng `computeIfAbsent` để gom nhóm.
- ConcurrentHashMap cho truy cập đa luồng.

## Lỗi hay gặp

- Key mutable.
- Gọi get rồi không xử lý null.
- Duyệt Map nhưng sửa cấu trúc sai cách.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
