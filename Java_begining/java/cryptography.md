# Cryptography

> Nhóm: Advanced Java

## Mục tiêu

- Hiểu hash, encryption, signature ở mức ứng dụng.
- Biết dùng API chuẩn thay vì tự chế thuật toán.
- Biết password phải hash bằng thuật toán chuyên dụng.

## Lý thuyết dễ hiểu

Crypto có nhiều khái niệm dễ nhầm:

- Hash: một chiều, kiểm tra toàn vẹn.
- Encryption: hai chiều, cần key để giải mã.
- Signature: chứng minh dữ liệu do private key ký.
- MAC/HMAC: kiểm tra toàn vẹn và xác thực bằng shared secret.

Trong app thực tế, ưu tiên thư viện/framework đã kiểm chứng. Với Spring Security, dùng `PasswordEncoder` thay vì tự hash.

## Facts cần nhớ

- Không tự thiết kế crypto.
- Password không mã hóa hai chiều; password nên hash bằng bcrypt/Argon2/PBKDF2.
- AES cần mode an toàn và IV/nonce đúng.

## Code mẫu

```java
import java.nio.charset.StandardCharsets;
import java.security.MessageDigest;
import java.security.NoSuchAlgorithmException;
import java.util.HexFormat;

public class HashDemo {
    public static void main(String[] arguments) throws NoSuchAlgorithmException {
        String text = "hello";
        MessageDigest digest = MessageDigest.getInstance("SHA-256");
        byte[] hashBytes = digest.digest(text.getBytes(StandardCharsets.UTF_8));
        String hexHash = HexFormat.of().formatHex(hashBytes);
        System.out.println(hexHash);
    }
}
```

Ví dụ này dùng hash cho dữ liệu thường, không dùng trực tiếp cho password.

## Cách triển khai thực tế

- Dùng TLS cho dữ liệu qua mạng.
- Quản lý key bằng secret manager, không commit vào Git.
- Dùng thư viện password hashing chuyên dụng.

## Lỗi hay gặp

- Tự viết thuật toán mã hóa.
- Dùng MD5/SHA-1 cho bảo mật.
- Log token/password/key.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
