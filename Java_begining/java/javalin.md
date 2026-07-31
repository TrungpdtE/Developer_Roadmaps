# Javalin

> Nhóm: Web Frameworks

## Mục tiêu

- Biết Javalin là web framework nhẹ.
- Tạo route HTTP đơn giản.
- Hiểu phù hợp project nhỏ/API nhỏ.

## Lý thuyết dễ hiểu

Javalin phù hợp khi muốn học HTTP routing rõ ràng hoặc làm API nhỏ. Nó không cung cấp hệ sinh thái đầy đủ như Spring Boot, nhưng đơn giản và dễ hiểu.

## Facts cần nhớ

- Javalin ít magic hơn Spring.
- Có thể viết app rất ngắn.
- Bạn tự quyết định nhiều kiến trúc hơn.

## Code mẫu

```java
import io.javalin.Javalin;

public class JavalinDemo {
    public static void main(String[] arguments) {
        Javalin app = Javalin.create().start(7000);

        app.get("/hello/{name}", context -> {
            String name = context.pathParam("name");
            context.result("Hello " + name);
        });
    }
}
```

## Cách triển khai thực tế

- Dùng cho demo, tool nội bộ, API nhỏ.
- Tự thêm validation, persistence, auth nếu cần.
- Giữ route không chứa quá nhiều business logic.

## Lỗi hay gặp

- Nhét tất cả logic vào lambda route.
- Không có cấu trúc project rõ.
- So sánh trực tiếp với Spring mà bỏ qua mục tiêu khác nhau.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
