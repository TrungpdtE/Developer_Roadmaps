# Behavior Testing

> Nhóm: Testing

## Mục tiêu

- Hiểu BDD kiểm tra hành vi theo ngôn ngữ nghiệp vụ.
- Biết Given-When-Then.
- Biết dùng khi cần stakeholder đọc được scenario.

## Lý thuyết dễ hiểu

Behavior testing tập trung vào hành vi người dùng/hệ thống thay vì implementation. Nó giúp team thống nhất requirement.

## Facts cần nhớ

- BDD không bắt buộc dùng tool.
- Cucumber là tool phổ biến cho BDD.
- Scenario quá chi tiết kỹ thuật sẽ mất lợi ích.

## Code mẫu

```gherkin
Feature: Student enrollment

  Scenario: Student enrolls in an open course
    Given an open course "JAVA-101"
    And a student "S001"
    When the student enrolls in the course
    Then the enrollment should be created
```

## Cách triển khai thực tế

- Viết scenario bằng ngôn ngữ domain.
- Giữ số scenario vừa đủ cho flow quan trọng.
- Map step xuống code test rõ ràng.

## Lỗi hay gặp

- BDD thành test UI chậm cho mọi thứ.
- Scenario mô tả click từng nút quá chi tiết.
- Step definition dùng lại quá mức thành khó hiểu.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
