# Play Framework

> Nhóm: Web Frameworks

## Mục tiêu

- Biết Play là framework web reactive.
- Hiểu routing/controller/action.
- Biết vị trí trong hệ sinh thái Java/Scala.

## Lý thuyết dễ hiểu

Play Framework cung cấp mô hình web full-stack/reactive. Nếu mục tiêu chính của bạn là Java backend phổ thông, học Spring Boot trước thường thực tế hơn; Play nên học khi dự án/team dùng.

## Facts cần nhớ

- Play dùng nhiều trong Scala hơn Java ở một số cộng đồng.
- Nó hướng async/non-blocking.
- Không phải lựa chọn phổ biến nhất cho người mới Java backend hiện nay.

## Code mẫu

```java
import play.mvc.Controller;
import play.mvc.Result;

public class HomeController extends Controller {
    public Result index() {
        return ok("Hello from Play");
    }
}
```

## Cách triển khai thực tế

- Học khi gặp codebase Play.
- Nắm async programming nếu dùng Play sâu.
- So sánh routing/config với Spring để hiểu tradeoff.

## Lỗi hay gặp

- Học quá nhiều framework cùng lúc.
- Dùng async nhưng block thread bên trong.
- Bỏ qua tài liệu version cụ thể.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
