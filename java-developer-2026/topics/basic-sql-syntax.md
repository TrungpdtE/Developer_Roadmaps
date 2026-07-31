# Basic SQL Syntax

> Nhóm: Learn the Prerequisites  
> Mức ưu tiên: Personal must know

## Học để làm gì?

Cú pháp SQL tối thiểu để đọc/ghi dữ liệu và debug query sinh ra từ ORM.

## Kiến thức cốt lõi

- SQL là kỹ năng backend bắt buộc dù bạn dùng ORM.
- Luôn phân biệt query đọc dữ liệu, query ghi dữ liệu và transaction.
- Index giúp đọc nhanh hơn nhưng làm ghi dữ liệu tốn chi phí hơn.

## Facts cần nhớ

- Mức ưu tiên trong roadmap: **Personal must know**. Bắt buộc học nếu bạn muốn đi Java backend nghiêm túc.
- Nhóm học: **Learn the Prerequisites**.
- Học bằng cách tự gõ lại ví dụ, tự đổi bài toán, rồi ghi chú lỗi gặp phải.
- Khi dùng trong production, luôn kiểm tra version, tài liệu chính thức, security advisory và compatibility với JDK/framework hiện tại.

## Ví dụ code hoặc cấu hình

```sql
create table students (
    id bigserial primary key,
    student_code varchar(30) not null unique,
    full_name varchar(200) not null,
    created_at timestamp not null default current_timestamp
);

insert into students (student_code, full_name)
values ('S001', 'Nguyen Van An');

select student_code, full_name
from students
where student_code = 'S001';
```

## Cách triển khai thực tế

- Bắt đầu bằng ví dụ nhỏ chạy được, sau đó mới đưa vào Spring/service lớn.
- Viết README ngắn trong project về cách chạy, cách test và các biến môi trường cần có.
- Với thư viện/framework, tạo một wrapper/service mỏng nếu bạn muốn giảm phụ thuộc trực tiếp trong toàn bộ codebase.
- Luôn có test cho happy path, input lỗi và case biên.
- Khi có network, database, cache hoặc message broker, luôn cấu hình timeout, retry hợp lý và log đủ context.

## Lỗi hay gặp

- Học thuộc API nhưng không hiểu vấn đề mà công nghệ đó giải quyết.
- Copy code mẫu nhưng không hiểu dependency, import, version và lifecycle.
- Dùng công nghệ vì thấy trong roadmap, không kiểm tra dự án có thật sự cần không.
- Bỏ qua failure mode: timeout, null, duplicate request, retry, partial failure, dữ liệu cũ.
- Không viết test nên refactor hoặc nâng version rất rủi ro.

## Checklist tự học

1. Giải thích chủ đề này trong 5 câu bằng lời của bạn.
2. Gõ lại ví dụ trong file này, không copy paste.
3. Sửa ví dụ sang bài toán sinh viên, khóa học, đăng ký môn hoặc đơn hàng.
4. Tạo ít nhất một lỗi cố ý rồi đọc lỗi compile/runtime.
5. Viết một test hoặc một script kiểm tra hành vi chính.
6. Ghi lại khi nào nên dùng và khi nào không nên dùng chủ đề này.

## Từ khóa tra cứu thêm

- `Basic SQL Syntax Java official documentation`
- `Basic SQL Syntax best practices Java`
- `Basic SQL Syntax production pitfalls`
- `Basic SQL Syntax Spring Boot integration`


[Quay lại roadmap](../README.md)
