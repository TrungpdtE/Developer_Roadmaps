# Static vs Dynamic Binding

> Nhóm: More about OOP

## Mục tiêu

- Hiểu binding là chọn method nào được gọi.
- Biết static/private/final binding sớm.
- Biết overridden instance method binding động.

## Lý thuyết dễ hiểu

Static binding dùng kiểu khai báo để quyết định lời gọi. Dynamic binding dùng object thật lúc runtime. Đây là lý do `Animal animal = new Dog(); animal.speak();` gọi `Dog.speak`.

## Facts cần nhớ

- Static binding xảy ra lúc compile.
- Dynamic binding xảy ra lúc runtime.
- Field không polymorphic như method.

## Code mẫu

```java
interface Shape {
    double area();
}

class Circle implements Shape {
    private final double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double area() {
        return Math.PI * radius * radius;
    }
}

public class BindingDemo {
    public static void main(String[] arguments) {
        Shape shape = new Circle(2.0);
        System.out.println(shape.area());
    }
}
```

## Cách triển khai thực tế

- Dynamic binding giúp code mở rộng mà ít sửa caller.
- Static method không override thật, chỉ hide.
- Dùng interface để tận dụng dynamic binding.

## Lỗi hay gặp

- Tưởng static method polymorphic.
- Truy cập field qua superclass rồi kỳ vọng field subclass.
- Overload được chọn theo kiểu compile-time gây bất ngờ.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
