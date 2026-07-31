# JDBC

> Nhóm: Database Access

## Mục tiêu

- Hiểu JDBC là API chuẩn kết nối SQL database.
- Biết Connection, PreparedStatement, ResultSet.
- Biết phòng SQL injection.

## Lý thuyết dễ hiểu

JDBC cho bạn thấy tầng thấp khi Java nói chuyện với database. Dù sau này dùng JPA/Hibernate, hiểu JDBC giúp debug query, transaction, connection.

## Facts cần nhớ

- JDBC là nền tảng phía dưới nhiều ORM.
- `PreparedStatement` giúp bind parameter an toàn.
- Connection nên lấy từ pool trong app thật.

## Code mẫu

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;

public class JdbcDemo {
    public static void main(String[] arguments) throws Exception {
        String url = "jdbc:postgresql://localhost:5432/school";
        String sql = "select student_code, full_name from students where student_code = ?";

        try (Connection connection = DriverManager.getConnection(url, "user", "password");
             PreparedStatement statement = connection.prepareStatement(sql)) {

            statement.setString(1, "S001");

            try (ResultSet resultSet = statement.executeQuery()) {
                while (resultSet.next()) {
                    System.out.println(resultSet.getString("full_name"));
                }
            }
        }
    }
}
```

## Cách triển khai thực tế

- Dùng connection pool như HikariCP.
- Dùng transaction cho nhiều thao tác cần atomic.
- Log slow query.

## Lỗi hay gặp

- Nối chuỗi SQL từ input user.
- Không đóng ResultSet/Statement/Connection.
- Mở connection mới cho từng dòng dữ liệu.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
