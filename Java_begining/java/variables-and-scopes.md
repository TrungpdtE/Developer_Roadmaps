# Variables and Scopes

> Nhóm: Learn the Basics

## Mục tiêu

- Biết local variable, parameter, field và static field.
- Hiểu phạm vi sống của biến trong block, method và object.
- Biết cách đặt tên biến rõ nghĩa.

## Lý thuyết dễ hiểu

Scope là vùng mà biến có thể được truy cập. Java có block scope rất rõ: biến khai báo trong `if`, `for`, `while` chỉ sống trong block đó.

Các loại biến thường gặp:

- Local variable: khai báo trong method.
- Parameter: biến đầu vào của method.
- Instance field: thuộc về từng object.
- Static field: thuộc về class, dùng chung.

Hãy giữ scope càng nhỏ càng tốt. Biến chỉ dùng trong vòng lặp thì khai báo trong vòng lặp, tránh field toàn cục nếu không cần.

## Facts cần nhớ

- Local variable phải được gán trước khi dùng.
- Field của object có giá trị mặc định nếu chưa gán.
- Biến trong block `{}` không thể dùng bên ngoài block đó.

## Code mẫu

```java
public class ScopeDemo {
    private String ownerName;
    private static int createdCounter = 0;

    public ScopeDemo(String ownerName) {
        this.ownerName = ownerName;
        createdCounter = createdCounter + 1;
    }

    public void printNumbers(int maximumNumber) {
        for (int currentNumber = 1; currentNumber <= maximumNumber; currentNumber++) {
            String message = ownerName + " sees number " + currentNumber;
            System.out.println(message);
        }

        // currentNumber và message không dùng được ở đây.
    }

    public static void main(String[] arguments) {
        ScopeDemo demo = new ScopeDemo("An");
        demo.printNumbers(3);
        System.out.println("Objects created: " + createdCounter);
    }
}
```

## Cách triển khai thực tế

- Trong service class, tránh field mutable nếu request có thể chạy song song.
- Dùng local variable cho dữ liệu tạm để code dễ test.
- Dùng `this.fieldName` khi tên parameter trùng tên field.

## Lỗi hay gặp

- Tưởng static field là biến riêng của từng object.
- Khai báo biến quá rộng làm khó debug.
- Shadowing: biến local che mất field cùng tên.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
