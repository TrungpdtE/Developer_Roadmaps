# JMeter

> Nhóm: Testing

## Mục tiêu

- Biết JMeter dùng cho load/performance testing.
- Hiểu thread group, sampler, assertion.
- Biết đọc latency/throughput/error rate.

## Lý thuyết dễ hiểu

JMeter mô phỏng nhiều user/request để đo hiệu năng. Bạn dùng nó để hỏi: API chịu được bao nhiêu request/giây, latency p95 bao nhiêu, lỗi tăng khi tải cao không.

## Facts cần nhớ

- JMeter không thay unit/integration test.
- Load test cần môi trường gần production.
- Kết quả sai nếu máy chạy test là bottleneck.

## Code mẫu

```text
Kịch bản mẫu:
1. Thread Group: 100 users, ramp-up 60 seconds.
2. HTTP Request: GET /api/products.
3. Assertion: response code is 200.
4. Listener: Summary Report hoặc backend metrics.
```

## Cách triển khai thực tế

- Theo dõi CPU, memory, database, GC khi load test.
- Test từng endpoint quan trọng.
- Đặt mục tiêu p95/p99 latency rõ.

## Lỗi hay gặp

- Chỉ nhìn average latency.
- Chạy load test từ laptop yếu rồi kết luận server chậm.
- Không warm up JVM.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
