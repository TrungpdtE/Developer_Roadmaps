# Arrays

> Nhóm: Learn the Basics

## Mục tiêu

- Biết tạo, đọc, ghi array.
- Hiểu index bắt đầu từ 0.
- Biết khi nào dùng array, khi nào dùng `ArrayList`.

## Lý thuyết dễ hiểu

Array là cấu trúc dữ liệu lưu nhiều phần tử cùng kiểu. Nó nhanh và đơn giản, nhưng không tự tăng kích thước. Nếu số lượng phần tử thay đổi thường xuyên, dùng `ArrayList`.

Index đầu tiên là `0`, index cuối là `array.length - 1`.

## Facts cần nhớ

- Array có kích thước cố định sau khi tạo.
- Truy cập index ngoài phạm vi gây `ArrayIndexOutOfBoundsException`.
- Array object có thể chứa `null`.

## Code mẫu

```java
import java.util.Arrays;

public class ArraysDemo {
    public static void main(String[] arguments) {
        int[] scores = {8, 9, 7, 10};
        int totalScore = 0;

        for (int index = 0; index < scores.length; index++) {
            totalScore = totalScore + scores[index];
        }

        double averageScore = (double) totalScore / scores.length;

        Arrays.sort(scores);
        System.out.println("Sorted scores: " + Arrays.toString(scores));
        System.out.println("Average: " + averageScore);
    }
}
```

## Cách triển khai thực tế

- Array phù hợp với dữ liệu cố định như bảng điểm nhập sẵn, tham số CLI, buffer.
- Dùng `Arrays.toString` để debug array một chiều.
- Dùng enhanced for khi không cần index.

## Lỗi hay gặp

- Lặp với `index <= array.length` thay vì `<`.
- In array trực tiếp ra mã hash thay vì nội dung.
- Nhầm `length` của array với `size()` của collection.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
