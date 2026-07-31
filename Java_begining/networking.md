# Networking

> Nhóm: Advanced Java

## Mục tiêu

- Hiểu HTTP client cơ bản.
- Biết request/response, status code, header, body.
- Biết timeout và lỗi mạng.

## Lý thuyết dễ hiểu

Networking trong backend chủ yếu là HTTP API, database connection, message broker. Ở mức Java core, bạn nên biết `java.net.http.HttpClient` để gọi API.

## Facts cần nhớ

- Java có `HttpClient` chuẩn từ Java 11.
- Network call có thể chậm, fail, timeout.
- Không tin dữ liệu từ mạng nếu chưa validate.

## Code mẫu

```java
import java.net.URI;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;
import java.time.Duration;

public class NetworkingDemo {
    public static void main(String[] arguments) throws Exception {
        HttpClient httpClient = HttpClient.newBuilder()
                .connectTimeout(Duration.ofSeconds(5))
                .build();

        HttpRequest request = HttpRequest.newBuilder()
                .uri(URI.create("https://example.com"))
                .timeout(Duration.ofSeconds(10))
                .GET()
                .build();

        HttpResponse<String> response = httpClient.send(request, HttpResponse.BodyHandlers.ofString());
        System.out.println(response.statusCode());
        System.out.println(response.body());
    }
}
```

## Cách triển khai thực tế

- Luôn đặt timeout.
- Retry cần giới hạn và chỉ retry lỗi phù hợp.
- Log status code và correlation id nếu có.

## Lỗi hay gặp

- Không timeout làm thread treo lâu.
- Retry request không idempotent gây tạo đơn hàng hai lần.
- Bỏ qua TLS/certificate errors.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
