# Object Lifecycle

> Nhóm: More about OOP

## Mục tiêu

- Hiểu object được tạo, sử dụng và thu gom.
- Biết constructor, reference, eligibility for GC.
- Biết không quản lý memory thủ công như C/C++.

## Lý thuyết dễ hiểu

Object lifecycle bắt đầu khi bạn gọi `new`, constructor thiết lập trạng thái ban đầu. Object tồn tại khi còn được tham chiếu từ stack, static field, object khác hoặc JVM root. Khi không còn reachable, nó có thể được garbage collector thu hồi.

GC không chạy ngay lập tức khi biến ra khỏi scope. Bạn không nên dựa vào thời điểm GC để đóng file, socket, database connection; hãy dùng try-with-resources.

## Facts cần nhớ

- Object sống trên heap trong đa số trường hợp.
- GC thu hồi object không còn reachable.
- `finalize` đã lỗi thời và không nên dùng.

## Code mẫu

```java
public class ObjectLifecycleDemo {
    public static void main(String[] arguments) {
        Student temporaryStudent = new Student("S001", "An");
        System.out.println(temporaryStudent.introduce());

        temporaryStudent = null;
        // Object Student cũ có thể được GC thu hồi sau điểm này nếu không còn reference khác.
    }
}
```

## Cách triển khai thực tế

- Đóng tài nguyên bằng `try-with-resources`.
- Đừng gọi `System.gc()` trong app bình thường.
- Dùng profiler nếu nghi memory leak.

## Lỗi hay gặp

- Nghĩ `null` là xóa object ngay lập tức.
- Dùng finalizer để giải phóng tài nguyên.
- Giữ object trong static collection làm leak.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
