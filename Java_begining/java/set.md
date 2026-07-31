# Set

> Nhóm: Collections

## Mục tiêu

- Hiểu Set không chứa phần tử trùng.
- Biết HashSet, LinkedHashSet, TreeSet.
- Biết equals/hashCode ảnh hưởng Set.

## Lý thuyết dễ hiểu

Set dùng khi bạn quan tâm tính duy nhất. Ví dụ danh sách role của user, danh sách tag, danh sách id đã xử lý.

## Facts cần nhớ

- HashSet không đảm bảo thứ tự.
- LinkedHashSet giữ thứ tự insertion.
- TreeSet sắp xếp theo natural order/comparator.

## Code mẫu

```java
import java.util.HashSet;
import java.util.Set;

public class SetDemo {
    public static void main(String[] arguments) {
        Set<String> uniqueEmails = new HashSet<>();
        uniqueEmails.add("an@example.com");
        uniqueEmails.add("an@example.com");
        uniqueEmails.add("binh@example.com");

        System.out.println(uniqueEmails.size());
        System.out.println(uniqueEmails.contains("an@example.com"));
    }
}
```

## Cách triển khai thực tế

- Dùng Set để loại trùng.
- Override equals/hashCode cho object custom.
- Chọn LinkedHashSet nếu cần thứ tự nhập.

## Lỗi hay gặp

- Kỳ vọng HashSet có thứ tự.
- Object mutable làm hashCode đổi sau khi đưa vào Set.
- Không hiểu duplicate dựa trên equals/hashCode.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
