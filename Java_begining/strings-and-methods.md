# Strings and Methods

> Nhóm: Learn the Basics

## Mục tiêu

- Hiểu `String` immutable.
- Biết viết method rõ input/output.
- Biết dùng `StringBuilder` khi nối chuỗi nhiều lần.

## Lý thuyết dễ hiểu

Method là khối code có tên, có thể nhận tham số và trả về kết quả. Viết method giúp tách logic thành phần nhỏ dễ đọc, dễ test.

`String` là object rất hay dùng. Vì immutable, mỗi lần biến đổi chuỗi là tạo kết quả mới. Điều này an toàn nhưng nếu nối chuỗi trong vòng lặp lớn, `StringBuilder` hiệu quả hơn.

## Facts cần nhớ

- `String` immutable: method như `toUpperCase` trả về chuỗi mới.
- So sánh nội dung chuỗi bằng `.equals`, không dùng `==`.
- Method nên có một trách nhiệm rõ ràng.

## Code mẫu

```java
public class StringMethodDemo {
    public static void main(String[] arguments) {
        String rawName = "  nguyen van an  ";
        String normalizedName = normalizeName(rawName);

        System.out.println(normalizedName);
        System.out.println(createCsvLine("Java", 25, true));
    }

    public static String normalizeName(String inputName) {
        String trimmedName = inputName.trim();
        String lowerCaseName = trimmedName.toLowerCase();
        return lowerCaseName;
    }

    public static String createCsvLine(String courseName, int version, boolean active) {
        StringBuilder builder = new StringBuilder();
        builder.append(courseName);
        builder.append(",");
        builder.append(version);
        builder.append(",");
        builder.append(active);
        return builder.toString();
    }
}
```

## Cách triển khai thực tế

- Tách validate, normalize, calculate thành method riêng.
- Tên method nên bắt đầu bằng động từ: `calculateTotal`, `findUserById`, `validateEmail`.
- Method quá dài là dấu hiệu cần chia nhỏ.

## Lỗi hay gặp

- Gọi `name.trim()` nhưng quên gán lại kết quả.
- Method vừa đọc database vừa format UI vừa gửi email.
- Tên method mơ hồ như `handle`, `process` nhưng làm quá nhiều việc.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
