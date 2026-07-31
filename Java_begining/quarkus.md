# Quarkus

> Nhóm: Web Frameworks

## Mục tiêu

- Biết Quarkus tối ưu cloud/native.
- Hiểu developer experience hot reload.
- Biết khi nào chọn thay Spring.

## Lý thuyết dễ hiểu

Quarkus là framework Java hiện đại hướng container/Kubernetes/native image. Nó cố gắng giảm memory footprint và startup time.

## Facts cần nhớ

- Quarkus hỗ trợ GraalVM native image tốt.
- API có thể dùng JAX-RS style.
- Phù hợp microservice cần startup nhanh.

## Code mẫu

```java
import jakarta.ws.rs.GET;
import jakarta.ws.rs.Path;
import jakarta.ws.rs.Produces;
import jakarta.ws.rs.core.MediaType;

@Path("/hello")
public class HelloResource {
    @GET
    @Produces(MediaType.TEXT_PLAIN)
    public String hello() {
        return "Hello from Quarkus";
    }
}
```

## Cách triển khai thực tế

- Chọn Quarkus nếu team cần native/cloud tối ưu.
- Vẫn cần hiểu DI, REST, config.
- So sánh hệ sinh thái thư viện trước khi chọn.

## Lỗi hay gặp

- Chọn framework theo trend không theo nhu cầu.
- Tưởng native image tương thích mọi reflection dễ dàng.
- Bỏ qua learning curve.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
