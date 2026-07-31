# Method Chaining

> Nhóm: More about OOP

## Mục tiêu

- Hiểu method trả về `this` hoặc object mới để gọi liên tiếp.
- Biết builder pattern.
- Biết khi nào chaining làm code khó debug.

## Lý thuyết dễ hiểu

Method chaining cho phép gọi nhiều method liên tiếp: `builder.name("An").age(20).build()`. Nó đọc tự nhiên khi các bước cùng xây dựng một object.

Có hai kiểu: mutable chaining thay đổi cùng object và immutable chaining trả về object mới. Với người mới, hãy đọc tài liệu API để biết method có mutate hay không.

## Facts cần nhớ

- Chaining thường thấy trong builder, stream, query DSL.
- Object immutable thường trả object mới trong chain.
- Method mutate rồi trả `this` cần được document rõ.

## Code mẫu

```java
public class UserBuilder {
    private String email;
    private String fullName;

    public UserBuilder email(String email) {
        this.email = email;
        return this;
    }

    public UserBuilder fullName(String fullName) {
        this.fullName = fullName;
        return this;
    }

    public User build() {
        return new User(email, fullName);
    }
}

public record User(String email, String fullName) {
}
```

## Cách triển khai thực tế

- Dùng builder khi constructor nhiều tham số.
- Chaining tốt khi thứ tự bước rõ.
- Với lỗi phức tạp, tách chain thành biến trung gian để debug.

## Lỗi hay gặp

- Chain quá dài gây khó đọc.
- Không validate trong `build`.
- Nhầm method mutable và immutable.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
