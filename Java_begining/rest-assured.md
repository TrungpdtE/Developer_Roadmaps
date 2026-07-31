# REST Assured

> Nhóm: Testing

## Mục tiêu

- Biết test REST API bằng cú pháp fluent.
- Kiểm tra status/body/header.
- Dùng cho API integration/e2e test.

## Lý thuyết dễ hiểu

REST Assured giúp viết test HTTP dễ đọc: given request, when call endpoint, then assert response.

## Facts cần nhớ

- REST Assured phổ biến trong Java API testing.
- Có thể kết hợp JUnit/TestNG.
- Test API nên rõ contract.

## Code mẫu

```java
import org.junit.jupiter.api.Test;

import static io.restassured.RestAssured.given;
import static org.hamcrest.Matchers.equalTo;

class StudentApiTest {
    @Test
    void shouldReturnStudent() {
        given()
                .baseUri("http://localhost:8080")
        .when()
                .get("/api/students/S001")
        .then()
                .statusCode(200)
                .body("studentCode", equalTo("S001"));
    }
}
```

## Cách triển khai thực tế

- Chạy app test trên port riêng.
- Assert cả lỗi 400/404, không chỉ happy path.
- Không phụ thuộc thứ tự test API.

## Lỗi hay gặp

- Test gọi môi trường thật không ổn định.
- Hard-code token hết hạn.
- Không dọn dữ liệu tạo ra.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
