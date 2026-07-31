# Lifecycle of a Program

> Nhóm: Learn the Basics

## Mục tiêu

- Biết code Java đi từ source code đến bytecode rồi chạy trên JVM.
- Hiểu compile time, runtime và class loading.
- Biết vì sao Java chạy được trên nhiều hệ điều hành.

## Lý thuyết dễ hiểu

Lifecycle cơ bản:

1. Bạn viết source code trong file `.java`.
2. `javac` kiểm tra cú pháp và kiểu dữ liệu rồi tạo file `.class`.
3. `java` khởi động JVM.
4. Class loader nạp class cần dùng.
5. Bytecode verifier kiểm tra tính hợp lệ.
6. Interpreter/JIT chạy và tối ưu chương trình.
7. Garbage collector thu hồi object không còn được tham chiếu.

Compile time là lúc lỗi cú pháp, lỗi kiểu dữ liệu, thiếu method... được phát hiện. Runtime là lúc chương trình thật sự chạy, có thể gặp lỗi như chia cho 0, file không tồn tại, kết nối database lỗi.

## Facts cần nhớ

- Java source `.java` được biên dịch thành bytecode `.class`.
- JVM chạy bytecode, không chạy trực tiếp source code.
- JIT compiler có thể tối ưu bytecode thành machine code khi chương trình đang chạy.

## Code mẫu

```java
public class ProgramLifecycleDemo {
    public static void main(String[] arguments) {
        int firstNumber = 10;
        int secondNumber = 2;
        int result = firstNumber / secondNumber;

        System.out.println("Result: " + result);
    }
}
```

```bash
javac ProgramLifecycleDemo.java
ls
java ProgramLifecycleDemo
```

Sau khi compile, bạn sẽ thấy `ProgramLifecycleDemo.class`. File này là bytecode để JVM chạy.

## Cách triển khai thực tế

- IDE như IntelliJ IDEA gọi build tool phía sau, nhưng bạn vẫn nên biết `javac` và `java` để debug môi trường.
- Trong production, bạn thường đóng gói app thành `.jar` hoặc container image.
- Log lúc startup rất quan trọng vì nó cho biết classpath, profile, port, database connection.

## Lỗi hay gặp

- Sửa source nhưng chạy lại file `.class` cũ do chưa compile.
- Nhầm lỗi compile với lỗi runtime.
- Classpath thiếu thư viện ngoài.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
