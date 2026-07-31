# Interfaces

> Nhóm: More about OOP

## Mục tiêu

- Khai báo contract bằng interface.
- Biết default method và static method trong interface.
- Dùng interface để polymorphism.

## Lý thuyết dễ hiểu

Interface nói một object có thể làm gì, không nói nó làm như thế nào. Ví dụ `List` có `add`, `get`, `size`; `ArrayList` và `LinkedList` triển khai khác nhau.

## Facts cần nhớ

- Class có thể implement nhiều interface.
- Interface field mặc định là public static final.
- Default method giúp thêm behavior mà ít phá backward compatibility.

## Code mẫu

```java
public interface ReportExporter {
    byte[] export(String reportTitle, String reportContent);

    default String defaultFileName(String reportTitle) {
        return reportTitle.toLowerCase().replace(" ", "-") + ".txt";
    }
}

public class TextReportExporter implements ReportExporter {
    @Override
    public byte[] export(String reportTitle, String reportContent) {
        String fileText = reportTitle + "\n" + reportContent;
        return fileText.getBytes();
    }
}
```

## Cách triển khai thực tế

- Khai báo biến bằng interface khi có thể: `List<String> names = new ArrayList<>();`.
- Interface rất hợp cho dependency injection.
- Giữ interface nhỏ và tập trung.

## Lỗi hay gặp

- Interface quá to buộc class implement method không cần.
- Default method chứa business logic quá nặng.
- Dùng interface chỉ để né hiểu class thật.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
