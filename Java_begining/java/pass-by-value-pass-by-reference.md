# Pass by Value / Pass by Reference

> Nhóm: More about OOP

## Mục tiêu

- Hiểu Java luôn pass-by-value.
- Biết giá trị của reference được copy.
- Phân biệt mutate object và gán lại parameter.

## Lý thuyết dễ hiểu

Java luôn truyền tham số theo value. Với object, value được truyền là reference. Vì vậy method có thể sửa state của object được reference trỏ tới, nhưng không thể làm biến bên ngoài trỏ sang object khác bằng cách gán lại parameter.

## Facts cần nhớ

- Java không pass-by-reference theo nghĩa C++.
- Method nhận bản copy của primitive hoặc bản copy của reference.
- Gán parameter sang object mới không đổi biến bên ngoài.

## Code mẫu

```java
import java.util.ArrayList;
import java.util.List;

public class PassingDemo {
    public static void main(String[] arguments) {
        List<String> names = new ArrayList<>();
        addName(names);
        replaceList(names);
        System.out.println(names);
    }

    static void addName(List<String> inputNames) {
        inputNames.add("An");
    }

    static void replaceList(List<String> inputNames) {
        inputNames = new ArrayList<>();
        inputNames.add("Binh");
    }
}
```

Kết quả là `[An]`, không phải `[Binh]`.

## Cách triển khai thực tế

- Muốn trả object mới, hãy return rõ ràng.
- Với object mutable, method có thể gây side effect.
- Dùng immutable object để giảm bất ngờ.

## Lỗi hay gặp

- Nói Java pass-by-reference.
- Gán parameter rồi kỳ vọng caller đổi.
- Không document method có mutate collection đầu vào.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
