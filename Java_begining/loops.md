# Loops

> Nhóm: Learn the Basics

## Mục tiêu

- Nắm `for`, enhanced `for`, `while`, `do while`.
- Biết dùng `break` và `continue` đúng chỗ.
- Biết tránh vòng lặp vô hạn.

## Lý thuyết dễ hiểu

Vòng lặp dùng để xử lý công việc lặp lại. Chọn loại vòng lặp theo ý định:

- Biết số lần lặp: `for`.
- Duyệt collection/array: enhanced `for`.
- Lặp đến khi điều kiện thay đổi: `while`.
- Muốn chạy ít nhất một lần: `do while`.

## Facts cần nhớ

- Enhanced for không cho sửa index trực tiếp.
- `break` thoát vòng lặp gần nhất.
- `continue` bỏ qua phần còn lại của lượt hiện tại.

## Code mẫu

```java
import java.util.List;

public class LoopsDemo {
    public static void main(String[] arguments) {
        List<String> names = List.of("An", "Binh", "Chi");

        for (int index = 0; index < names.size(); index++) {
            System.out.println(index + ": " + names.get(index));
        }

        for (String name : names) {
            if (name.equals("Binh")) {
                continue;
            }
            System.out.println("Hello " + name);
        }

        int countdown = 3;
        while (countdown > 0) {
            System.out.println(countdown);
            countdown = countdown - 1;
        }
    }
}
```

## Cách triển khai thực tế

- Duyệt dữ liệu nhỏ bằng loop thường rất rõ ràng.
- Với xử lý collection phức tạp, có thể dùng Stream API sau khi đã vững loop.
- Luôn đảm bảo biến điều kiện trong `while` được cập nhật.

## Lỗi hay gặp

- Off-by-one: chạy thiếu hoặc thừa một phần tử.
- Xóa phần tử khỏi list trong enhanced for gây lỗi.
- Vòng lặp vô hạn do quên cập nhật biến.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
