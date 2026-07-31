# Array vs ArrayList

> Nhóm: Collections

## Mục tiêu

- Phân biệt kích thước cố định và động.
- Biết API `add`, `get`, `size`.
- Chọn cấu trúc phù hợp.

## Lý thuyết dễ hiểu

Array đơn giản và cố định. ArrayList tiện hơn khi thêm/xóa phần tử. Trong app business, `List`/`ArrayList` xuất hiện nhiều hơn array.

## Facts cần nhớ

- Array dùng `.length`, ArrayList dùng `.size()`.
- ArrayList bên trong dùng array động.
- ArrayList không lưu primitive trực tiếp, dùng wrapper.

## Code mẫu

```java
import java.util.ArrayList;
import java.util.List;

public class ArrayListDemo {
    public static void main(String[] arguments) {
        int[] fixedScores = {8, 9, 10};
        List<Integer> dynamicScores = new ArrayList<>();
        dynamicScores.add(8);
        dynamicScores.add(9);
        dynamicScores.add(10);

        System.out.println(fixedScores.length);
        System.out.println(dynamicScores.size());
    }
}
```

## Cách triển khai thực tế

- Khai báo bằng interface: `List<String> names = new ArrayList<>();`.
- Dùng array cho API thấp, buffer, dữ liệu cố định.
- Dùng list cho dữ liệu nghiệp vụ thay đổi.

## Lỗi hay gặp

- Nhầm length và size.
- Xóa trong lúc duyệt sai cách.
- Dùng raw type `ArrayList` không generic.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
