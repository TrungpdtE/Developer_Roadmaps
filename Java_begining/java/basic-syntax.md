# Basic Syntax

> Nhóm: Learn the Basics

## Mục tiêu

- Hiểu cấu trúc tối thiểu của một file Java.
- Biết phân biệt package, class, method, statement, block và comment.
- Biết compile và chạy chương trình bằng `javac`/`java`.

## Lý thuyết dễ hiểu

Cú pháp Java xoay quanh class. Code chạy được nằm trong method, method nằm trong class, class thường nằm trong package.

Một statement thường kết thúc bằng dấu chấm phẩy `;`. Một block dùng cặp `{ }` để gom nhiều statement. Comment có ba dạng chính: `//` cho một dòng, `/* ... */` cho nhiều dòng, và `/** ... */` cho JavaDoc.

Khi mới học, bạn nên viết rõ ràng thay vì viết tắt. Đặt tên biến bằng tiếng Anh có nghĩa, ví dụ `studentAge` thay vì `a`, vì code Java trong dự án thực tế thường dài và cần đọc lại nhiều lần.

## Facts cần nhớ

- Tên file public class phải trùng tên class, ví dụ `HelloWorld.java` chứa `public class HelloWorld`.
- `main` là điểm vào phổ biến của ứng dụng console: `public static void main(String[] args)`.
- Java phân biệt chữ hoa chữ thường: `Name`, `name`, `NAME` là ba định danh khác nhau.

## Code mẫu

```java
public class HelloWorld {
    public static void main(String[] arguments) {
        String studentName = "An";
        int studentAge = 20;

        System.out.println("Hello " + studentName);
        System.out.println("Age: " + studentAge);
    }
}
```

Chạy:

```bash
javac HelloWorld.java
java HelloWorld
```

Giải thích:

- `public class HelloWorld`: khai báo một class công khai tên `HelloWorld`.
- `main`: method JVM gọi đầu tiên khi chạy chương trình.
- `String[] arguments`: mảng tham số dòng lệnh.
- `System.out.println`: in ra màn hình và xuống dòng.

## Cách triển khai thực tế

- Trong dự án thật, mỗi class thường nằm trong một file riêng.
- Luôn format code bằng IDE hoặc build tool để người khác đọc dễ.
- Tránh copy code mà không hiểu từng dòng; Java lỗi compile khá rõ, hãy đọc từ dòng đầu tiên của stack trace.

## Lỗi hay gặp

- Quên dấu `;` sau statement.
- Tên file không trùng public class.
- Viết `Main` nhưng chạy `java main` hoặc ngược lại.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
