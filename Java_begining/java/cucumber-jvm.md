# Cucumber-JVM

> Nhóm: Testing

## Mục tiêu

- Biết Cucumber chạy Gherkin trên JVM.
- Viết step definition Java.
- Kết hợp JUnit.

## Lý thuyết dễ hiểu

Cucumber-JVM cho phép viết scenario `.feature`, rồi implement từng step bằng Java. Nó phù hợp acceptance test khi requirement cần đọc được bởi cả non-dev.

## Facts cần nhớ

- Feature file dùng Given/When/Then.
- Step regex/expression map text sang Java method.
- Cucumber test thường chậm hơn unit test.

## Code mẫu

```java
import io.cucumber.java.en.Given;
import io.cucumber.java.en.Then;
import io.cucumber.java.en.When;

import static org.junit.jupiter.api.Assertions.assertTrue;

public class EnrollmentSteps {
    private boolean enrollmentCreated;

    @Given("an open course {string}")
    public void anOpenCourse(String courseCode) {
        System.out.println("Course: " + courseCode);
    }

    @When("the student enrolls in the course")
    public void theStudentEnrollsInTheCourse() {
        enrollmentCreated = true;
    }

    @Then("the enrollment should be created")
    public void theEnrollmentShouldBeCreated() {
        assertTrue(enrollmentCreated);
    }
}
```

## Cách triển khai thực tế

- Dùng cho acceptance criteria quan trọng.
- Giữ step reusable nhưng không quá generic.
- Tách test data setup sạch.

## Lỗi hay gặp

- Viết quá nhiều scenario trùng.
- Step phụ thuộc state global.
- Dùng Cucumber cho unit test đơn giản.

## Bài tập

1. Chạy lại code mẫu bằng JDK hiện tại của bạn.
2. Đổi tên biến thành tên có nghĩa theo bài toán riêng của bạn.
3. Viết thêm một case lỗi và giải thích vì sao lỗi đó xảy ra.

[Quay lại README](../README.md)
